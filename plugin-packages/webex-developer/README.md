# Webex Developer

Webex Developer gives your coding agent grounded answers about Webex public
APIs and integrations. Ask about REST APIs, OAuth integrations, webhooks,
meetings, messaging, calling, or contact center, and the agent looks up current
Webex developer documentation before it explains or writes code in your
project. It does not administer a live Webex organization.

## What the plugin runs, sends, and stores

The `webex-api-knowledge` skill runs a bundled Node.js 20+ helper script on
your machine. The helper:

- Signs you in with Webex OAuth (authorization code with PKCE, public client,
  no client secret). It opens your browser to the Webex identity broker
  (`idbroker*.webex.com`) and listens once on `http://localhost:17177` for the
  login callback. Requested scopes: `identity:people_read spark:mcp`.
- Uses your access token to look up the knowledge service address in the
  Webex service catalog at `u2c.wbx2.com`.
- Sends your search questions (up to 8 queries, 500 characters each) with your
  access token to that Webex developer knowledge service (by default
  `webex-developer-ai-assistant-a.wbx2.com`), and returns the documentation
  results to the agent.
- Stores the OAuth token in the macOS Keychain or, on Windows, in a file
  encrypted with Windows DPAPI for the current user. Run the helper's logout
  command to delete it.

The plugin sends no data to any other destination. Linux is not supported for
token storage yet.

## Install

Claude Code:

```sh
/plugin marketplace add webex/webex-skills
/plugin install webex-developer@webex-skills
```

Codex:

```sh
codex plugin marketplace add webex/webex-skills
codex plugin add webex-developer@webex-skills
```

## Source

This folder is generated. Skill source lives in `skills/webex-api-knowledge/`
of [webex/webex-skills](https://github.com/webex/webex-skills), and
`npm run plugin:build` assembles this package. Licensed under MIT.
