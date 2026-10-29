# Security Policy

## Reporting a vulnerability

Please **do not** open a public issue for security problems. Email **support@valueztech.com** with the subject "Valueztech Maximo Developer security" and include steps to reproduce. You will get an acknowledgement within 3 business days (AEST/AEDT).

## How the extension handles credentials

- API keys are stored in the operating system keychain through VS Code SecretStorage, or read from an environment variable named in the config. They are never written to `.maximo-sync.json`, and a config file containing an `apiKey` field is rejected.
- The API key is sent only in the `apikey` header to the configured `server.url`. It is dropped if Maximo redirects to a different host.
- `allowSelfSigned` disables TLS certificate checks for that server only. Use it only for non-production environments.
- The extension only reads from Maximo. It never writes to the server.
- Paths from server data are validated so files cannot be written outside the project folder.

## Supported versions

Security fixes are released for the latest minor version.
