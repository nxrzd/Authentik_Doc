# Authentik (Identity Provider / SSO)

## Overview
Self-hosted identity provider used to centralize authentication and provide identity-aware (forward-auth) reverse-proxy protection in front of sensitive admin interfaces in the lab.

## Deployment
- Runs on a dedicated Linux VM via Docker Compose (see `docker.md` for the general containerization approach).
- Positioned as a forward-auth layer in front of any admin panel that has any path to being reached from outside the LAN (e.g. the hypervisor management UI), so that such panels are never reachable without first authenticating through Authentik.
- Reached externally only via the same reverse-tunnel/relay pattern used elsewhere (see `network-security-monitoring.md`) — never via a direct inbound port-forward.

## Purpose
- Single sign-on across self-hosted apps where supported.
- Primary hardening control preventing direct, unauthenticated exposure of infrastructure admin interfaces.

## Redacted / intentionally omitted
- Real admin subdomain, internal IP/hostname, and provider/application configuration.

## Planned Inegrations
- Adding friends to servers (SSO integration with MFA) for access to game server controls
- Multi-user access to notes for collaboration
- Obsidian note documentation access guardian
