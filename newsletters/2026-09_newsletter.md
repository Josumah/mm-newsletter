# James' Curated GitHub Newsletter, September 2026

Hey everyone - this is my monthly roundup of the GitHub updates that matter most for your teams. This September issue covers announcements through **October 19**, with a big focus on safer agent workflows, new application security capabilities, and better enterprise controls. If anything catches your eye or you want to dig into how it fits your environment, just let me know. Feel free to share this with your team, and you can find [past issues in the archive](https://josumah.github.io/mm-newsletter/).

---

# Agents with guardrails

The headline this cycle is pretty simple: as we expand agent capabilities, we can keep governance moving with them. That gives teams more room to use agents without treating controls as an afterthought.

• **Local sandboxing for GitHub Copilot** (`GA`) gives local agent workflows a secure execution boundary across **Copilot CLI**, the **GitHub Copilot app**, and **VS Code** sessions using Agent Host. Teams can restrict filesystem, network, credential, and tool access through developer or enterprise-managed policy. It's included with GitHub Copilot at no additional cost. [Read the announcement](https://github.blog/changelog/2026-10-07-local-sandboxing-for-github-copilot-now-generally-available) | [Review the sandbox documentation](https://docs.github.com/copilot/concepts/security-governance-and-network-settings/about-cloud-and-local-sandboxes)

• **Enterprise managed permissions for agent operations** (`GA`) let administrators set shell commands, file access, and network domains to deny, ask, or allow. Local settings and saved approvals can't weaken those restrictions, and different teams can have different policies. [See the managed permissions update](https://github.blog/changelog/2026-09-09-enterprise-managed-permissions-for-github-copilot-agent-operations) | [Review the policy reference](https://docs.github.com/enterprise-cloud@latest/copilot/reference/enterprise-administrators/enterprise-managed-settings#deny-ask-allow)

• **Managed settings validation and freshness enforcement** help close the loop on policy deployment. GitHub added an in-product validator for malformed settings and team mappings, plus a force-refresh option that can fail closed when a client can't confirm the current policy at startup. [Check the settings validator](https://github.blog/changelog/2026-09-25-enterprise-managed-settings-in-product-validator) | [See the enforcement updates](https://github.blog/changelog/2026-10-13-enterprise-managed-settings-enforcement-updates)

---

# Copilot & AI

• **Copilot code review** now covers more of the review lifecycle, including pull request approvals, API-driven requests, and configurable review effort. Organizations can also choose to bill eligible member review requests to an organization cost center instead of the member entitlement. That organization-billed path requires AI Credits paid usage, and admins can put a budget around it. [See approval support](https://github.blog/changelog/2026-09-01-copilot-code-review-can-now-approve-pull-requests) | [Review the API and effort update](https://github.blog/changelog/2026-10-02-copilot-code-review-api-support-and-new-default-effort-level) | [Check billing controls](https://github.blog/changelog/2026-10-08-copilot-code-review-new-organization-billing-options-and-controls)

• **Copilot model choice** expanded again across OpenAI, Anthropic, Google, and xAI. Since availability and premium request multipliers vary, I'd use the model comparison page as the source of truth when teams choose a default. [Compare available models](https://docs.github.com/en/copilot/reference/ai-models/model-comparison)

• **Copilot measurement and budget workflows** are getting more useful for rollout decisions. The impact dashboard now shows feature engagement, budget increase requests are generally available, and the budgets page can search and filter across products, SKUs, cost centers, organizations, and users. [Explore feature engagement metrics](https://github.blog/changelog/2026-09-17-copilot-impact-dashboard-now-shows-feature-engagement) | [Review budget requests](https://github.blog/changelog/2026-09-16-copilot-budget-increase-requests-are-generally-available) | [See searchable budgets](https://github.blog/changelog/2026-10-13-search-and-filter-for-budgets-now-available)

• **Content exclusions in the Copilot app and CLI** (`GA`) extend repository exclusion rules into two more agent surfaces. That's a useful governance check if teams are moving work out of the editor and into CLI or app-based sessions. [Read the announcement](https://github.blog/changelog/2026-09-02-content-exclusions-generally-available-in-copilot-app-and-cli) | [Review content exclusion setup](https://docs.github.com/en/copilot/how-tos/configure-content-exclusion)

---

# IDE Updates

• **VS Code agent workflows** added scheduled automations and agent merge in preview, plus pull request creation, Dev Container sessions, and direct GitHub issue or pull request context. The overall direction is fewer handoffs between implementation, review, and merge. [Read the September Copilot roundup](https://github.blog/changelog/2026-10-01-github-copilot-in-vs-code-september-2026-releases) | [Browse VS Code release notes](https://code.visualstudio.com/updates/)

• **VS Code 1.142 enterprise controls** can route policy-managed sessions to Copilot Agent Host and let administrators allow Assisted permissions while blocking Allow All. The same release added canvases in preview, which give developers and agents a shared interactive surface beside chat. [Read the VS Code 1.142 notes](https://code.visualstudio.com/updates/v1_142) | [Learn about Agent Host](https://code.visualstudio.com/docs/agents/concepts/agent-host)

• **GitHub Copilot for JetBrains** added managed sandbox policy, policy diagnostics, organization and enterprise skills, managed instructions, persistent MCP tool controls, and managed default models. This is a meaningful step toward closer governance parity for teams that don't standardize on VS Code. [Review managed sandboxing](https://github.blog/changelog/2026-09-08-enterprise-managed-sandbox-in-copilot-for-jetbrains) | [See the 1.18.0 update](https://github.blog/changelog/2026-09-22-new-features-and-improvements-in-copilot-for-jetbrains) | [Browse current plugin versions](https://plugins.jetbrains.com/plugin/17718-github-copilot--your-ai-pair-programmer/versions)

• **Visual Studio 2026 Copilot chat** (`PREVIEW`) now has an opt-in experience built on the same Copilot SDK used by Copilot CLI and the Copilot app. That shared foundation brings more consistent agent behavior across Microsoft development environments. [Read the Visual Studio release notes](https://learn.microsoft.com/en-us/visualstudio/releases/2026/release-notes#github-copilot)

---

# Security & Compliance

• **Agentic autofix for code scanning alerts** (`GA`) can explore relevant files, propose a fix, rerun **CodeQL**, and open a validated draft pull request. It's available to **GitHub Code Security** and **GitHub Advanced Security** customers on GitHub Enterprise Cloud, including data residency. It requires a Copilot billing method and consumes Code Security AI Credits plus GitHub Actions minutes. [Read the GA announcement](https://github.blog/changelog/2026-10-15-agentic-autofix-for-code-scanning-alerts-general-availability) | [Review the documentation](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/code-scanning/autofix-for-code-scanning)

• **AI Scan for pull requests** (`GA`) complements CodeQL across languages and frameworks that don't currently have full CodeQL coverage. Findings are advisory and don't block merges. Private and internal repositories require Code Security or Advanced Security, and scans consume Code Security AI Credits. [Read the GA announcement](https://github.blog/changelog/2026-10-15-ai-scan-for-pull-requests-generally-available) | [Review AI-powered security detections](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/code-scanning/ai-powered-security-detections)

• **Open source license compliance** (`GA`) lets enterprises use rulesets to require dependency license checks before merge. Repositories need **GitHub Code Security**, and the release includes data residency support, audit events, policy APIs, and an API that agents can use to check package compliance. [Read the announcement](https://github.blog/changelog/2026-10-16-open-source-license-compliance-generally-available) | [Review license compliance setup](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/supply-chain-security/open-source-license-compliance)

• **Workflow execution protections for GitHub Actions** (`GA`) can control which actors and events start workflows, with evaluate mode for testing policy impact first. If you maintain public repositories that use `pull_request_target`, review the default protection before enforcement begins on **November 2, 2026**. [Read the GA announcement](https://github.blog/changelog/2026-09-17-workflow-execution-protections-in-github-actions-generally-available) | [Review Actions policies](https://docs.github.com/actions/concepts/about-actions-policies)

• **Secret protection updates** include merge blocking when exposed secrets are detected, a context-aware detection model, and broader provider coverage for keys from Anthropic, Salesforce, and others. [See merge blocking](https://github.blog/changelog/2026-09-09-block-pull-requests-with-exposed-secrets-from-merging) | [Read about the detection model](https://github.blog/changelog/2026-10-07-purpose-built-model-for-leaked-secret-detection) | [Review provider coverage updates](https://github.blog/changelog/2026-10-13-secret-scanning-blocks-anthropic-keys-by-default-adds-salesforce)

---

# Enterprise Administration

• **Enterprise Live Migrations** (`GA`) support near-zero-downtime moves from **GitHub Enterprise Server** to **GitHub Enterprise Cloud with data residency**, including large and highly active repositories. It complements GitHub Enterprise Importer, so teams can choose the right path repository by repository. [Read the announcement](https://github.blog/changelog/2026-09-01-enterprise-live-migrations-from-ghes-to-ghe-com-generally-available) | [Review migration guidance](https://docs.github.com/migrations/elm/about-live-migrations)

• **GitHub Enterprise Server 3.22** (`GA`) added enterprise teams, required reviewer rules, individual ruleset bypass users, and a technical preview of Copilot CLI for disconnected environments. If you're on 3.22, the **3.22.1** and **3.22.2** security patches are the more urgent part of this update. [Read the 3.22 announcement](https://github.blog/changelog/2026-09-08-github-enterprise-server-3-22-is-now-generally-available) | [Review the 3.22 release notes](https://docs.github.com/enterprise-server@3.22/admin/release-notes)

• **External custom properties** (`PREVIEW`) can sync repository ownership, service tier, lifecycle stage, and compliance status from a CMDB, internal developer portal, or another system of record. Those values can then drive repository views, filters, and rulesets while the external system stays authoritative. [Read the announcement](https://github.blog/changelog/2026-09-29-bring-business-context-with-external-custom-properties) | [Review integration guidance](https://docs.github.com/organizations/managing-organization-settings/sync-external-custom-properties)

• **GitHub App least-privilege permissions** separate repository creation and installation management from broad repository administration. That gives platform teams a cleaner path to automate app and repository management without handing out more access than the workflow needs. [Review the GitHub App updates](https://github.blog/changelog/2026-10-13-github-app-improvements-for-least-privilege-and-management)

---

# Platform & DevEx

• **Stacked pull requests** (`GA`) are now available for teams that want to break work into smaller, dependent changes and review them in sequence. [Read the announcement](https://github.blog/changelog/2026-10-06-stacked-pull-requests-generally-available)

• **GitHub Actions workflow lockfiles** (`PREVIEW`) help teams pin and review resolved Actions dependencies. This is worth a look for platform teams tightening supply-chain controls and build reproducibility. [Read the preview announcement](https://github.blog/changelog/2026-10-14-github-actions-workflow-lockfiles-in-public-preview)

• **Actions runner image updates** include **Ubuntu 26** availability and general availability of the **Xcode 27** image. CI owners should check image pins and compatibility before the next scheduled workflow update. [Review Ubuntu 26](https://github.blog/changelog/2026-09-17-ubuntu-26-generally-available-and-latest-migration) | [See Xcode 27 availability](https://github.blog/changelog/2026-10-15-xcode-27-runner-image-generally-available)

---

# Resources & Training

• **GitHub Copilot Agents learning plan** is a useful starting point for technical decision makers planning broader agent adoption. [Start the Microsoft Learn plan](https://learn.microsoft.com/en-us/plans/j2j1fzzymrmqgw)

• **Microsoft AI Tour 2026 resources** include recordings, code, workshops, and demos for GitHub Copilot agent workflows, code migration, MCP, and enterprise-ready AI. [Open the AI Tour resource center](https://github.com/microsoft/aitour26-resource-center)

---

# Events

## Virtual and Hybrid

| Date | Event | Why it may be useful |
|------|-------|----------------------|
| **October 28-29, 2026** | [GitHub Universe 2026](https://githubuniverse.com/) | Product launches, Copilot and agent sessions, security updates, and a free virtual option |
| **November 17-20, 2026** | [Microsoft Ignite 2026](https://ignite.microsoft.com/) | Copilot, agent platforms, cloud and AI, security, and digital attendance |

## In Person

| Date | Event | Location |
|------|-------|----------|
| **October 22, 2026** | [Microsoft AI Tour: Philadelphia](https://aitour.microsoft.com/flow/microsoft/philadelphia27/citylanding/page/cityhome) | Philadelphia, Pennsylvania |
| **November 17-December 10, 2026** | [Universe on the Road](https://githubuniverse.com/on-the-road) | Sydney, Toronto, Paris, São Paulo, Madrid, London, and Munich |

---

# Deprecations & Migration Notices

• **Copilot model retirements:** Another group of models is scheduled for retirement in mid-November. Admins should review managed defaults, pinned agents, and model-specific automation now. [Review the retirement notice](https://github.blog/changelog/2026-10-15-upcoming-deprecation-of-selected-github-copilot-models-in-mid-november)

• **JetBrains IDE support:** GitHub Copilot now requires **JetBrains IDE 2025.2** or later. [Review the support update](https://github.blog/changelog/2026-10-10-new-controls-and-chat-improvements-in-copilot-for-jetbrains)

• **Node 20 in GitHub Actions:** Node 20 is no longer available, so check older actions and custom JavaScript actions for runtime dependencies. [Read the deprecation update](https://github.blog/changelog/2026-09-23-node-20-is-no-longer-available-in-github-actions)

• **macOS 14 runner image:** Workflows still pinned to the macOS 14 hosted image need to move to a supported image. [Review the retirement notice](https://github.blog/changelog/2026-10-01-github-actions-macos-14-runner-image-retirement)

---

That's the roundup for this month. If you want to talk through any of these updates or how we can apply them to what your team is doing, I'm always happy to jump on a call. Just let me know.
