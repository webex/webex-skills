# Changelog

All notable changes to the `webex-api-knowledge` skill. Entries exist only for stable versions; pre-release changes are included in the next stable entry.

## [1.0.0] - 2026-11-19

### Added
- Ground Webex REST API, OAuth, webhook, meetings, messaging, calling, and contact center work in the Webex Developer AI Assistant knowledge service.
- Sign in to Webex in the browser as a public OAuth client using PKCE; no client secret is shipped.
- Store and refresh tokens securely in macOS Keychain or Windows DPAPI-encrypted local storage.
- Install for Codex, GitHub Copilot in VS Code, and Claude Code at user or project scope.
- Record the installed skill version in the skill metadata.

### Changed
- Use the production Webex OAuth client and identity service.
