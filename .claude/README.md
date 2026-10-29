# Claude Code API configuration

This setup is scoped to this project folder. Claude Code loads `.claude/settings.local.json` when launched for this project; it does not change your global Claude settings or other projects.

## Change the endpoint or model

Edit `settings.local.json` and update `ANTHROPIC_BASE_URL` and `ANTHROPIC_MODEL` to the values provided by your API provider. The default endpoint is Anthropic's API.

## Set the API key

Set `ANTHROPIC_API_KEY` directly in `.claude/settings.local.json`. Replace the empty string with your API key:

```json
"ANTHROPIC_API_KEY": "your-api-key"
```

The key is stored as plaintext in this local settings file. `.claude/.gitignore` excludes this file from Git to help prevent accidental commits, but it is not encrypted. Do not share the file or copy the key into a shared `settings.json`.

The endpoint must support Anthropic's API. If your provider requires a different authentication variable or API protocol, follow that provider's Claude Code instructions.

## Troubleshooting startup warnings

- If Claude Code reports that both `ANTHROPIC_AUTH_TOKEN` and `ANTHROPIC_API_KEY` are set, this project is configured to use `ANTHROPIC_API_KEY`. Remove `ANTHROPIC_AUTH_TOKEN` from the environment that launches Claude Code. In a PowerShell terminal, run `Remove-Item Env:ANTHROPIC_AUTH_TOKEN -ErrorAction SilentlyContinue` before starting Claude Code. If you launch it from VS Code, restart the terminal after changing the environment.
- A custom model ID such as `omni-combo` may be reported as unrecognized because Claude Code cannot determine its context window; it assumes 200k tokens. Keep the provider's model ID if the endpoint requires it. To remove that warning, use a model ID recognized by Claude Code and supported by the endpoint.
