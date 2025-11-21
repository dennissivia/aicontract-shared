# Security

## Secret Handling — Critical
- NEVER capture sensitive data in terminal output or read secret files into AI context.
- Secrets must not appear in terminal output, file read operations, variables, strings, or anywhere they would enter model context/logs.

Always handle secrets through pipes:
- Allowed: `flyctl tokens create deploy | gh secret set TOKEN_NAME`
- Allowed: `cat .env.production.secrets | grep PASSWORD | sed 's/old/new/' | tee .env.production.secrets`
- Allowed: `echo "NEW_SECRET=value" | tee -a .env.production.secrets`
- Do not: assign secrets to variables and echo them (e.g., `TOKEN=$(flyctl tokens create)` then `echo $TOKEN | gh secret set ...`).
- Do not: read `.env.production.secrets` into model context.

When secrets must be stored or modified:
- Use pipes so values stay in shell memory only.
- Prefer temporary files in `/tmp` that never get read back into the model context.
- Use shell redirects (`>>`, `tee`) without capturing output.
- Example: `command-that-outputs-secret | command-that-consumes-secret`.

Security rationale:
- Terminal output and file reads expose secrets in AI context and logs.
- Pipes prevent accidental leaks during debugging or in conversation history.

## Command Injection Prevention
- NEVER use backticks in shell commands.
- Quote variables properly (use `"$VAR"`).
- Validate or sanitize any user-provided input before using it in shell commands.
- Prefer tool parameters instead of shell interpolation when possible.
