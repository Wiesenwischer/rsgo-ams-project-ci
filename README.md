# ams.project Stacks for ReadyStackGo — CI Channel

Stack definitions for [ams.project](https://www.ams-erp.com/) by [ams.Solution AG](https://www.ams-erp.com/) — an enterprise project management system built on microservices.

> **CI channel.** This repository tracks the latest continuous-integration manifests
> (`*-ci` versions, images tagged `linux-latest-ci`). It is intended for test and
> evaluation environments. For pinned, promoted manifests use the
> [RC channel](https://github.com/Wiesenwischer/rsgo-ams-project-rc) (`*-rc`) or the
> stable channel.

## Usage

This repository is available as a stack source in [ReadyStackGo](https://github.com/Wiesenwischer/ReadyStackGo).
Add it during the setup wizard (**Stack Sources** step) or later under
**Settings → Stack Sources → Add → Git Repository**, using this repository's URL.

## Products

| Product | Description | Version | Stacks |
|---------|-------------|---------|--------|
| [ams.project](ams-project/) | Enterprise Project Management System | 4.0.0-ci | 16 |
| [IdentityAccess](ams-identityaccess/) | Standalone Identity Provider | 3.0.2 | 1 |

### ams.project

Multi-stack product with Infrastructure, Platform, IdentityAccess and Business Services organized by bounded context:

- **Infrastructure** — EventStore, EventStoreDB, Redis
- **Platform** — Web BFF, Desktop Gateways, ClientHub, Admin Portal
- **Business Services** — ProjectManagement, Discussions, Memo, SalesOrders, Export, ERP Integration, Capacity Planning, Production Planning, Reporting, Project Exporting, Project Import, Public API, Analytics, TaskContext

### ams.identityaccess

Standalone identity provider (IdentityServer / AdminPortal / ClientHub / EmailSender) that can be deployed independently of ams.project.

## Stack Format

Each product is a directory containing a `stack.yaml` file in the [RSGO Manifest Format](https://github.com/Wiesenwischer/ReadyStackGo). Multi-stack products use `include` references to organize sub-stacks.
