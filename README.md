# My OpenClaw Self-Hosted Stack

> This is a personal fork of [OpenClaw](https://github.com/openclaw/openclaw), an open-source personal AI assistant runtime. I did not build OpenClaw. I run it.

## What I run on this

A 24/7 agent operations stack on a Mac mini M4 (24 GB), anchored by OpenClaw as the agent runtime and gateway:

- OpenClaw gateway: always-on, single-user, Telegram and WhatsApp delivery, a Claude Opus-class model wired through an Azure AI Foundry provider
- n8n workflows: an automation layer for lead enrichment, content pipelines, and scheduled jobs, connected to the gateway over webhooks
- ORB trading bot: a Python MNQ micro-futures bot on Rithmic and Apex, running as a daemon with Telegram alerts
- Cloudflare Tunnel: exposes the local gateway and n8n securely, with no static IP or open ports
- A second OpenClaw profile for a separate user, with its own identity and skills

Everything runs persistently via launchd user services.

## Why this repo exists

I forked upstream to pin a known-good snapshot of the OpenClaw daemon for the stack. Day to day I install from npm (`openclaw@latest`); the fork is a reference point.

## Upstream

All OpenClaw source and docs: [github.com/openclaw/openclaw](https://github.com/openclaw/openclaw)
