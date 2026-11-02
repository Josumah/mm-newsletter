# James' Curated GitHub Newsletter, October 2026

*[Read this issue online](https://josumah.github.io/mm-newsletter/issues/2026-10.html) or [browse every past issue in the archive](https://josumah.github.io/mm-newsletter/).*

Hey everyone, here's my roundup of the GitHub updates that mattered most from October 1 through November 2. This one is mostly about GitHub Universe, which wrapped up October 28-29, and it was a big one. If you only skim one section, make it the first one. The commercial model for Copilot changed, and that's worth a conversation with each of you. Feel free to share this with your team, and if anything catches your eye, let me know and we can dig in.

• **GitHub Enterprise now includes Copilot access**, with AI usage billed against your enterprise budget instead of per-seat Copilot licenses.
• **Copilot Fusion is `GA`**, so Copilot picks and combines models for you at the effort level you choose, inside the model policies you already set.
• **GHAS leaned hard into AI**: AI Scan for pull requests and agentic autofix are `GA`, with AI secret detection, a package firewall, and reachability analysis in `PREVIEW`.

---

# Universe 2026: Copilot is now part of the platform

The theme this year was pretty clear. Copilot is no longer just a separate add-on. It's becoming part of how GitHub Enterprise works, from licensing to where agents run to how code gets reviewed and approved.

## **GitHub Enterprise now includes Copilot access**

Enterprises working with a GitHub or Microsoft account team can now get Copilot included with GitHub Enterprise for every licensed user. Instead of managing Copilot seat counts and usage separately, AI usage is metered from the first request against your enterprise budget, using the policies, alerts, and cost centers you already have. Code completion and next edit suggestions keep working even with no budget, while Copilot Chat, code review, and cloud agents need available budget, and an exhausted budget never removes access. Users without a GitHub Enterprise license can get the same access through **Copilot Standalone at $10 per user per month**, and Copilot Business and Copilot Enterprise are still available if your current setup works for you. This is available now for GitHub Enterprise Cloud through your account team (self-serve comes later in stages), so this is one we should walk through together. [Changelog](https://github.blog/changelog/2026-10-28-github-enterprise-now-includes-access-to-github-copilot) | [What's changing](https://docs.github.com/copilot/get-started/whats-changing-with-github-enterprise-and-copilot) | [Billing docs](https://docs.github.com/copilot/concepts/billing-and-usage/organizations-and-enterprises/billing) | [Keynote recap](https://github.blog/news-insights/company-news/github-universe-2026-evolving-every-layer-of-the-stack/)

## **Copilot Fusion** (`GA`)

Instead of picking a model for every task, developers pick **Copilot Fusion** and an effort level (Standard, High, or Max). Fusion decides whether one model handles the task or whether models work together, either by escalating from a cheaper draft to a stronger model or by having one model critique another's work. Fusion only uses models enabled in your enterprise and organization policies, admins can exclude a model from Fusion without disabling it for everyone, and Fusion can be set as the default through enterprise-managed settings. Billing is per model at each model's standard rate, with a limited-time 30% discount on Fusion usage (the VS Code release notes list it through November 30). It's available in VS Code, the Copilot app, Copilot CLI, and JetBrains, and intelligent routing to on-device models is in experimental preview. [Changelog](https://github.blog/changelog/2026-10-28-route-and-orchestrate-models-with-github-copilot-fusion) | [Fusion docs](https://docs.github.com/copilot/concepts/models/copilot-fusion) | [Admin model controls](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-availability-of-default-models) | [Local model routing](https://github.blog/changelog/2026-10-28-github-copilot-fusion-now-supports-selection-of-local-models)

## **One connected Copilot cloud experience** (`GA`)

A Copilot task can now start on github.com, GitHub Mobile, the Copilot app, Copilot CLI, VS Code, Slack, or Teams, and pick back up from any of the others. Sessions run in secure cloud sandboxes that resume where they left off. The cost piece matters here: **billing for cloud sandbox usage begins in November 2026** and draws from your included Actions entitlement, which is now one flexible pool for builds, cloud sandboxes, and (on Enterprise Cloud) larger hosted runners. Usage beyond the entitlement follows your existing rates and budgets, so we should take a quick look at your Actions consumption before agent usage ramps. [Changelog](https://github.blog/changelog/2026-10-28-work-from-anywhere-with-a-new-connected-copilot-cloud-experience) | [Docs](https://docs.github.com/en/copilot/concepts/copilot-surfaces/copilot-on-github)

## **Copilot code review: Max effort and approvals**

Copilot code review added a **Max** effort level (`PREVIEW`) that runs several review agents across models from different providers, then reconciles their findings into one review. It takes longer and uses more AI credits than Lite or Balanced, and admins can cap the maximum effort at the enterprise, organization, or repository level. **Copilot approvals** are now `GA`: when turned on, Copilot's approval counts toward required approvals, gets dismissed when new commits land, and can be limited to specific file paths. Approvals are off by default. Earlier in October, review also picked up REST and GraphQL API support, Balanced became the default effort level, and org owners can now bill reviews to the organization's cost center instead of individual members' quotas. [Max and approvals](https://github.blog/changelog/2026-10-28-copilot-code-review-merge-with-confidence-with-max-and-approvals) | [API support](https://github.blog/changelog/2026-10-02-copilot-code-review-api-support-and-new-default-effort-level) | [Billing options](https://github.blog/changelog/2026-10-08-copilot-code-review-new-organization-billing-options-and-controls) | [Configure docs](https://docs.github.com/copilot/how-tos/copilot-on-github/set-up-copilot/configure-code-review)

---

# Everything that shipped at Universe

Here's the full list, pulled from the [Universe recap](https://github.com/events/universe/recap) and GitHub's Universe changelog posts. The bigger items get more detail in the sections below.

| Area | Ship | Status | Link |
|---|---|---|---|
| Copilot | GitHub Enterprise includes Copilot access | Available via account team | [Changelog](https://github.blog/changelog/2026-10-28-github-enterprise-now-includes-access-to-github-copilot) |
| Copilot | Copilot Fusion (Standard, High, Max) | `GA` | [Changelog](https://github.blog/changelog/2026-10-28-route-and-orchestrate-models-with-github-copilot-fusion) |
| Copilot | Fusion routing to local models | Experimental | [Changelog](https://github.blog/changelog/2026-10-28-github-copilot-fusion-now-supports-selection-of-local-models) |
| Copilot | Connected cloud experience and cloud sandboxes | `GA` | [Changelog](https://github.blog/changelog/2026-10-28-work-from-anywhere-with-a-new-connected-copilot-cloud-experience) |
| Copilot | Copilot Projects in the Copilot app | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-github-copilot-app-universe-releases) |
| Copilot | Shared Copilot Automations | Rolling out | [Changelog](https://github.blog/changelog/2026-10-28-build-shared-workflows-for-your-team-with-copilot-automations) |
| Copilot | Automations triggers, tools, and AI credit limits | Rolling out | [Changelog](https://github.blog/changelog/2026-10-28-new-tools-triggers-and-cost-controls-for-copilot-automations) |
| Copilot | Self-improving Automations | Rolling out | [Changelog](https://github.blog/changelog/2026-10-28-copilot-automations-now-learn-from-outcomes-and-self-improve) |
| Copilot | Cloud Automations in VS Code | New | [Changelog](https://github.blog/changelog/2026-10-28-create-and-manage-copilot-automations-in-visual-studio-code) |
| Copilot | Connectors (GitHub-verified MCP servers) | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-connect-your-tools-to-copilot-without-all-the-setup) |
| Copilot | Copilot code review Max effort | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-copilot-code-review-merge-with-confidence-with-max-and-approvals) |
| Copilot | Copilot code review approvals | `GA` | [Changelog](https://github.blog/changelog/2026-10-28-copilot-code-review-merge-with-confidence-with-max-and-approvals) |
| Copilot | Agent Merge on github.com pull requests | New | [Changelog](https://github.blog/changelog/2026-10-28-agent-merge-watches-and-fixes-pull-requests-in-the-cloud) |
| Copilot | GitHub Agentic Workflows | `GA` | [Changelog](https://github.blog/changelog/2026-10-28-github-agentic-workflows-generally-available) |
| Copilot | GitHub intelligence and Copilot Memory | New | [Changelog](https://github.blog/changelog/2026-10-28-github-intelligence-puts-your-code-context-and-history-to-work) |
| Copilot | Image generation in Copilot | New | [Changelog](https://github.blog/changelog/2026-10-28-generate-and-edit-images-directly-in-copilot) |
| Copilot | Repository plugin defaults and enterprise plugin controls | `GA` | [Changelog](https://github.blog/changelog/2026-10-28-repository-plugin-defaults-and-enterprise-plugin-controls-generally-available) |
| Copilot | Copilot in VS Code, Universe releases | New | [Changelog](https://github.blog/changelog/2026-10-28-github-copilot-in-vs-code-universe-releases) |
| Copilot | Copilot in JetBrains, Universe releases | New | [Changelog](https://github.blog/changelog/2026-10-28-github-copilot-in-jetbrains-universe-releases) |
| Copilot | GitHub Copilot SDK becoming Microsoft Copilot SDK | Transition | [Changelog](https://github.blog/changelog/2026-10-28-github-copilot-sdk-is-becoming-microsoft-copilot-sdk) |
| Copilot | Replica, open-source AI prototyping tool | Open source | [Changelog](https://github.blog/changelog/2026-10-28-introducing-replica-an-open-source-ai-prototyping-tool) |
| Security | Security extension for the Copilot app | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-security-extension-for-the-github-copilot-app) |
| Security | AI Scan for repositories | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-ai-scan-for-repositories-in-public-preview) |
| Security | AI Scan for pull requests | `GA` | [Changelog](https://github.blog/changelog/2026-10-15-ai-scan-for-pull-requests-generally-available) |
| Security | Agentic autofix for code scanning alerts | `GA` | [Changelog](https://github.blog/changelog/2026-10-15-agentic-autofix-for-code-scanning-alerts-general-availability) |
| Security | Code scanning for AI applications | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-code-scanning-for-ai-applications-in-public-preview) |
| Security | Push protection for AI-detected secrets | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-push-protection-beyond-predefined-secret-patterns) |
| Security | Public monitoring for enterprises | `GA` | [Changelog](https://github.blog/changelog/2026-10-28-public-monitoring-for-enterprises-generally-available) |
| Security | Package firewall (npm) | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-20-github-package-firewall-in-public-preview) |
| Security | Dependabot reachability analysis (JS/TS) | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-prioritize-dependabot-alerts-with-reachability-analysis) |
| Security | Open source license compliance | `GA` | [Changelog](https://github.blog/changelog/2026-10-16-open-source-license-compliance-generally-available) |
| Platform | Stacked pull requests | `GA` | [Changelog](https://github.blog/changelog/2026-10-06-stacked-pull-requests-generally-available) |
| Platform | Issue artifacts, plus `gh --attach` for images and video | `PREVIEW` | [Changelog](https://github.blog/changelog/2026-10-28-issue-artifacts-are-now-in-public-preview) |
| Platform | Repository pull requests view ("find the pull requests that need you") | Announced | [Recap](https://github.com/events/universe/recap) |
| Platform | Actions multi-cloud compute | Opt-in on Enterprise Cloud | [Changelog](https://github.blog/changelog/2026-10-28-github-actions-adds-multi-cloud-compute-to-improve-reliability) |
| Platform | Pull request limit exemptions | New | [Changelog](https://github.blog/changelog/2026-10-28-pull-request-limits-exempt-contributors-by-age-or-history) |
| Platform | Moderate role for Issues | Coming in the next few weeks | [Changelog](https://github.blog/changelog/2026-10-28-moderate-role-for-github-issues-generally-available) |
| Trends | 2026 Octoverse report | Published | [Octoverse](https://github.blog/news-insights/octoverse/octoverse-commits-pushes-reach-new-highs-in-2026-as-developers-build-with-agents/) |

---

# Copilot & AI

• **Copilot Automations grew up.** Automations can now be shared across a team instead of running under one person's identity, fire on 24 new events (including code scanning, secret scanning, and Dependabot alerts), chain into multi-step workflows, and use tools from custom MCP servers. The part I'd point every admin to is the new **AI credit limits** per run, day, week, or month, so a runaway automation can't quietly burn budget. They can also propose improvements to their own prompts based on outcomes, and VS Code can now run them in the cloud when your laptop is closed. [Shared automations](https://github.blog/changelog/2026-10-28-build-shared-workflows-for-your-team-with-copilot-automations) | [Triggers and cost controls](https://github.blog/changelog/2026-10-28-new-tools-triggers-and-cost-controls-for-copilot-automations) | [Self-improvement](https://github.blog/changelog/2026-10-28-copilot-automations-now-learn-from-outcomes-and-self-improve) | [Docs](https://docs.github.com/copilot/concepts/agent-capabilities/agent-powered-workflows-and-operations/about-automations)

• **GitHub Agentic Workflows** (`GA`): Write automation in plain Markdown (issue triage, CI failure analysis, docs updates, test writing) and it compiles into standard Actions YAML. Since these are just GitHub Actions, they reuse your runner groups and policies, and you can power them with Copilot or another coding agent. [Changelog](https://github.blog/changelog/2026-10-28-github-agentic-workflows-generally-available) | [Project docs](https://github.github.com/gh-aw/)

• **Agent Merge on pull requests:** Select **Watch and fix** in a pull request's merge box and Copilot fixes failing Actions workflows, merge conflicts, or both in a cloud environment. Pair it with auto-merge and the pull request lands once it's green. [Changelog](https://github.blog/changelog/2026-10-28-agent-merge-watches-and-fixes-pull-requests-in-the-cloud) | [Docs](https://docs.github.com/copilot/how-tos/copilot-on-github/use-copilot-agents/get-pull-requests-ready-to-merge)

• **Connectors** (`PREVIEW`): Developers sign in once to services like Slack, Figma, Notion, and Sentry (26 at launch) and that connection works across the Copilot app, CLI, VS Code, Copilot in the cloud, and Mobile. Admins control which connectors are allowed through the existing MCP allowlist. [Changelog](https://github.blog/changelog/2026-10-28-connect-your-tools-to-copilot-without-all-the-setup) | [Docs](https://docs.github.com/copilot/concepts/customizations/copilot-connectors) | [Enterprise allowlist](https://docs.github.com/copilot/how-tos/administer-copilot/manage-mcp-usage/configure-enterprise-allowlist)

• **The Copilot app got Projects, computer use, and image generation.** **Copilot Projects** (`PREVIEW`) give a multi-repo goal one home, with its context, parallel agents, and results together. Computer use (`PREVIEW`) lets Copilot work through GUI-only desktop apps that have no API, and image generation can be turned off by policy if that's not something you want in your environment. [Copilot app releases](https://github.blog/changelog/2026-10-28-github-copilot-app-universe-releases) | [Projects docs](https://docs.github.com/copilot/how-tos/github-copilot-app/working-with-projects) | [Computer use](https://github.blog/changelog/2026-10-01-github-copilot-can-now-interact-with-desktop-apps) | [Image generation](https://github.blog/changelog/2026-10-28-generate-and-edit-images-directly-in-copilot)

• **Context that sticks around:** **GitHub intelligence** brings Copilot Memory, repository conventions, and related code history into agent sessions so they don't start from scratch every time. **Issue artifacts** (`PREVIEW`) attach plans, research, and HTML diagrams directly to an issue. [GitHub intelligence](https://github.blog/changelog/2026-10-28-github-intelligence-puts-your-code-context-and-history-to-work) | [Memory admin docs](https://docs.github.com/copilot/how-tos/use-copilot-agents/copilot-memory/manage-as-administrator) | [Issue artifacts](https://github.blog/changelog/2026-10-28-issue-artifacts-are-now-in-public-preview)

• **New models** (`GA`): **Claude Haiku 5.5** (fast, high-volume work), **Gemini 4 Argon** (complex agentic tasks), **GPT-6.1 Terra** (everyday agentic coding at lower cost than Sol), plus **Claude Sonnet 5.5** and **GPT-6.1 Sol** from the September 28 weekly release. Haiku 5.5, Gemini 4 Argon, and GPT-6.1 Terra are billed at provider list pricing under usage-based billing, so we should check new models against your model policy before turning them on. [Haiku 5.5](https://github.blog/changelog/2026-10-07-claude-haiku-5-5-in-github-copilot) | [Gemini 4 Argon](https://github.blog/changelog/2026-10-13-gemini-4-argon-in-github-copilot) | [GPT-6.1 Terra](https://github.blog/changelog/2026-10-26-gpt-6-1-terra-in-github-copilot) | [Models and pricing](https://docs.github.com/copilot/reference/copilot-billing/models-and-pricing)

• **For platform teams building on Copilot:** **Dynamic workflows** let you define multi-agent orchestration in code across the CLI, app, and SDK. The **GitHub Copilot SDK is becoming the Microsoft Copilot SDK**, with package names changing in phases, and **server-to-server authentication** (`PREVIEW`) lets SDK-based services act on behalf of an org without a signed-in user. [Dynamic workflows](https://github.blog/changelog/2026-10-01-dynamic-workflows-in-copilot-cli-and-the-copilot-app) | [SDK transition](https://github.blog/changelog/2026-10-28-github-copilot-sdk-is-becoming-microsoft-copilot-sdk) | [Server-to-server auth](https://github.blog/changelog/2026-10-27-github-copilot-supports-server-to-server-authentication)

• **GitHub in Slack and Teams:** @GitHub can now work across multiple repositories in one conversation, and the new Teams app turns notifications into fixes and pull requests without leaving the channel. [Slack and Teams](https://github.blog/changelog/2026-10-15-copilot-in-slack-and-teams-adds-model-and-repository-updates) | [Copilot in Teams](https://github.blog/changelog/2026-10-23-turn-notifications-into-code-with-github-copilot-in-teams)

---

# IDE Updates

• **VS Code** (1.141 through 1.144): The new **Agent Host** keeps sessions running after you close a window, supports remote agents over SSH and dev tunnels, and lets you continue the same session from the Copilot app, Mobile, github.com, or the CLI. The Copilot harness is now the default for new sessions, and admins got managed-settings controls for sandboxing, permissions, default model, and Fusion tier. [Universe releases](https://github.blog/changelog/2026-10-28-github-copilot-in-vs-code-universe-releases) | [VS Code 1.144 notes](https://code.visualstudio.com/updates/v1_144) | [September releases](https://github.blog/changelog/2026-10-01-github-copilot-in-vs-code-september-2026-releases)

• **JetBrains** (plugin 1.19 and 1.20): Fusion replaces the Auto model option, local sandboxes and next edit suggestions landed, and enterprise admins can now set the default agent model and lock down sandbox host rules through managed settings. [Universe releases](https://github.blog/changelog/2026-10-28-github-copilot-in-jetbrains-universe-releases) | [Enterprise controls](https://github.blog/changelog/2026-10-10-new-controls-and-chat-improvements-in-copilot-for-jetbrains) | [Plugin versions](https://plugins.jetbrains.com/plugin/17718-github-copilot/versions/stable)

• **Visual Studio:** The September update added pull request exploration through the Git agent, bring-your-own model, and a fixer action that hands NuGet vulnerability warnings to Copilot agent mode. Version 18.11 (October 13) also added an opt-in new Copilot chat built on the same SDK as the CLI and Copilot app. [September update](https://github.blog/changelog/2026-10-22-github-copilot-in-visual-studio-september-update-2) | [Release notes](https://learn.microsoft.com/visualstudio/releases/2026/release-notes)

• **Copilot CLI** (v1.0.92 through v1.0.105): Enterprise network domain limits, managed control over assisted permissions, Fusion support, a flag to turn off client telemetry, and local model discovery from Ollama. [Release notes](https://github.com/github/copilot-cli/releases/tag/v1.0.104) | [Local models](https://github.blog/changelog/2026-10-07-discover-local-models-in-github-copilot-cli)

---

# Security & Compliance (GHAS)

Security had its biggest month in a while. The common thread is AI doing more of the finding and fixing, with clear billing lines so you can decide where to turn it on.

• **AI Scan for pull requests** (`GA`) **and repositories** (`PREVIEW`): AI Scan finds vulnerabilities in languages CodeQL doesn't cover (PHP, Shell, Terraform, Dockerfiles, JSP, Blazor, and more), and the new repository mode scans a whole repo on demand so you can assign the backlog to Copilot. Pull request findings are advisory and won't block merges. Both consume **Code Security AI credits** (no Copilot license required), with SKU-level budgets available, and security overview now shows AI Scan enablement and remediation metrics. [PR scanning GA](https://github.blog/changelog/2026-10-15-ai-scan-for-pull-requests-generally-available) | [Repository scanning](https://github.blog/changelog/2026-10-28-ai-scan-for-repositories-in-public-preview) | [Docs](https://docs.github.com/code-security/concepts/code-scanning/ai-scan-for-repositories) | [Metrics](https://github.blog/changelog/2026-10-13-code-scanning-ai-scan-metrics-in-security-overview)

• **Agentic autofix for code scanning alerts** (`GA`): Assign an alert to Copilot and it explores the codebase, proposes a fix, reruns CodeQL to confirm the alert closes, and opens a draft pull request. Heads up on cost: it uses Code Security AI credits plus Actions minutes, and once enabled it **replaces the free Generate Fix button** on alerts, so we'll want to pick where it's turned on before rolling it out broadly. [Changelog](https://github.blog/changelog/2026-10-15-agentic-autofix-for-code-scanning-alerts-general-availability) | [Docs](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/code-scanning/autofix-for-code-scanning)

• **AI secret detection:** Push protection (`PREVIEW`) can now block secrets that don't match a known pattern, like plain passwords, using a classifier that reads the surrounding code. AI-detected secret alerts remain included in Secret Protection and GHAS at no additional charge, while the new push protection check and the Copilot `/security-review` secret check will consume AI credits. [Push protection](https://github.blog/changelog/2026-10-28-push-protection-beyond-predefined-secret-patterns) | [Detection model and billing](https://github.blog/changelog/2026-10-07-purpose-built-model-for-leaked-secret-detection) | [Docs](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/secret-security/push-protection)

• **Public monitoring for enterprises** (`GA`): GitHub watches all of public github.com for your secrets, including leaks from personal forks and public issues, and attributes them back to your enterprise. It's included with Secret Protection at **no additional cost**, and it now has triage, validity checks, an API, and webhooks. A data residency version is in `PREVIEW`. [GA announcement](https://github.blog/changelog/2026-10-28-public-monitoring-for-enterprises-generally-available) | [Triage and API](https://github.blog/changelog/2026-10-23-public-monitoring-adds-triage-validity-api-and-webhooks) | [Docs](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/secret-security/public-monitoring)

• **Package firewall** (`PREVIEW`): Blocks malicious and risky npm packages before agents, runners, or IDEs install them, with an exception workflow for false positives. It's free during the preview and will move to metered billing (similar to Actions) at GA. [Changelog](https://github.blog/changelog/2026-10-20-github-package-firewall-in-public-preview) | [Docs](https://docs.github.com/enterprise-cloud@latest/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/protecting-endpoints-with-package-firewall)

• **Dependabot reachability analysis** (`PREVIEW`): For JavaScript and TypeScript, Dependabot now shows whether your code actually calls the vulnerable function, so teams can fix what's reachable first. It runs in a managed Actions workflow with nothing to install. [Changelog](https://github.blog/changelog/2026-10-28-prioritize-dependabot-alerts-with-reachability-analysis) | [Docs](https://docs.github.com/code-security/concepts/supply-chain-security/about-reachability-analysis-for-dependabot-alerts)

• **Code scanning for AI applications** (`PREVIEW`) **and the Copilot app security extension** (`PREVIEW`): Code scanning now flags agent-specific risks like indirect prompt injection and excessive agency on pull requests. The new security extension puts code scanning alerts inside the Copilot app so developers can explain and fix them in one place. [AI applications](https://github.blog/changelog/2026-10-28-code-scanning-for-ai-applications-in-public-preview) | [Security extension](https://github.blog/changelog/2026-10-28-security-extension-for-the-github-copilot-app) | [Docs](https://docs.github.com/code-security/concepts/code-scanning/ai-applications-scanning-for-pull-requests)

• **Open source license compliance** (`GA`): Set one enterprise-wide license policy and enforce it on pull requests through a ruleset condition. Available on Enterprise Cloud for repos with Code Security enabled. [Changelog](https://github.blog/changelog/2026-10-16-open-source-license-compliance-generally-available) | [Docs](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/supply-chain-security/open-source-license-compliance)

• **Smaller security updates worth knowing:** Anthropic keys are now blocked by push protection by default, with new Salesforce, Supabase, and Lovable detectors. Push attribution (limited `PREVIEW`) records who actually pushed each commit, risk assessments now show protected vs. unprotected repos, and CodeQL 2.27.2 improved C++, Go, Rust, and JavaScript analysis. [Secret detectors](https://github.blog/changelog/2026-10-13-secret-scanning-blocks-anthropic-keys-by-default-adds-salesforce) | [Push attribution](https://github.blog/changelog/2026-10-12-push-attribution-public-preview) | [Risk assessments](https://github.blog/changelog/2026-11-02-security-risk-assessments-include-repository-protection-status) | [CodeQL 2.27.2](https://github.blog/changelog/2026-10-09-codeql-2-27-2-improves-c-go-rust-and-javascript-analysis)

## **GitHub Code Quality**

There wasn't a new Code Quality launch at Universe, but October filled in some useful admin gaps after the July GA. You can now **download Code Quality license usage as a CSV** showing every active committer and which repos they touched, which makes it easy for us to spot where turning Code Quality off would free licenses next cycle (it's billed per active committer). Dismissals and reopenings of findings now show up in the **audit log**, coverage uploads no longer fail CI on branches without a pull request, and weekly scheduled scans now wait for a real push or pull request, so dormant repos stop scanning every week. If your team is thinking about AI-generated code quality more broadly, the "AI Code Hygiene" webinar in the Events section below is a good fit. [License CSV](https://github.blog/changelog/2026-10-15-download-github-code-quality-license-usage-as-a-csv) | [Audit log](https://github.blog/changelog/2026-10-13-audit-github-code-quality-finding-dismissals-and-reopenings) | [Coverage fix](https://github.blog/changelog/2026-10-01-code-coverage-uploads-no-longer-fail-ci-for-new-branches) | [Inactive repos](https://github.blog/changelog/2026-10-01-scheduled-code-scanning-skips-inactive-repositories) | [Cost docs](https://docs.github.com/enterprise-cloud@latest/code-security/how-tos/maintain-quality-code/view-and-manage-cost)

---

# Enterprise Administration (GHE)

• **GHES security patches:** If you run GitHub Enterprise Server 3.18 through 3.22, the October 6 patch releases fix a high-severity issue in secret scanning validity checks that could lead to remote code execution (CVE-2026-96890), plus a medium-severity default-branch bypass. I'd prioritize this one. [GHES 3.22 release notes](https://docs.github.com/en/enterprise-server@3.22/admin/release-notes)

• **Plugin governance** (`GA`): Enterprises can now require plugins, block plugins, and restrict installs to approved marketplaces through managed settings, across VS Code, Copilot CLI, and the Copilot app. Required plugins install automatically and users can't turn them off. [Changelog](https://github.blog/changelog/2026-10-28-repository-plugin-defaults-and-enterprise-plugin-controls-generally-available) | [Docs](https://docs.github.com/copilot/concepts/customizations/plugins)

• **Assisted permissions and local sandboxing** (`GA`): Copilot now uses a model to auto-approve clearly safe commands and ask about everything else, and local sandboxes restrict agent access to the filesystem, network, and credentials based on your policies. Together they cut approval fatigue without giving agents free rein. [Assisted permissions](https://github.blog/changelog/2026-10-26-github-copilot-assisted-permissions-generally-available) | [Local sandboxing](https://github.blog/changelog/2026-10-07-local-sandboxing-for-github-copilot-now-generally-available) | [Sandbox docs](https://docs.github.com/copilot/concepts/security-governance-and-network-settings/about-cloud-and-local-sandboxes)

• **Tighter managed settings:** Admins can force clients to pull fresh policy at startup, require minimum client versions for governance keys, and (opt-in) attribute Copilot telemetry to a user without capturing prompts. The **Copilot model policy REST API** (`GA`) also lets you manage model policies for enterprises, teams, agent apps, and orgs as code, and the global default policy for Copilot features finished rolling out on October 26. [Managed settings](https://github.blog/changelog/2026-10-13-enterprise-managed-settings-enforcement-updates) | [Telemetry attribution](https://github.blog/changelog/2026-10-12-client-telemetry-user-attribution-and-configurable-capture) | [Model policy API](https://github.blog/changelog/2026-10-19-copilot-model-policy-api-for-enterprise-orgs-and-teams) | [Global default](https://github.blog/changelog/2026-10-22-global-default-for-copilot-features-generally-available)

• **Better usage reporting:** The usage metrics API now breaks out usage by client (including OpenCode, Claude Code, Codex, and Zed) and names your custom skills, agents, and MCP servers instead of lumping them into "other". If agent activity looked like it dropped recently, updating the IDE fixes it. The impact dashboard also added an opt-in **industry comparison**, and budgets are now searchable by scope, product, SKU, or user. [By client](https://github.blog/changelog/2026-10-23-usage-metrics-api-adds-usage-from-tools-like-opencode) | [Named customizations](https://github.blog/changelog/2026-10-22-custom-skills-agents-and-mcp-servers-in-usage-metrics-api) | [IDE fix](https://github.blog/changelog/2026-10-06-update-your-ide-to-restore-agent-activity-in-copilot-usage-metrics) | [Industry comparison](https://github.blog/changelog/2026-10-22-industry-comparisons-in-the-copilot-impact-dashboard) | [Budgets](https://github.blog/changelog/2026-10-13-search-and-filter-for-budgets-now-available)

• **GitHub Apps at the enterprise level** (`GA`): You can install GitHub Apps on the enterprise and use them in place of classic PATs for enterprise governance, security, and admin automation, with new least-privilege permissions. [Enterprise installations](https://github.blog/changelog/2026-10-23-enterprise-installations-for-github-apps-generally-available) | [Least privilege](https://github.blog/changelog/2026-10-13-github-app-improvements-for-least-privilege-and-management)

• **EMU deprovisioning fix:** Between June 1 and June 13, some Enterprise Managed User accounts deprovisioned through SCIM were deleted instead of suspended, so they show up as ghost users. GitHub has published the details and the fix. [Changelog](https://github.blog/changelog/2026-10-23-emu-deletions-fix)

---

# Platform & DevEx

• **Stacked pull requests** (`GA`): Break big changes into smaller pull requests that get reviewed on their own and merge together. GA adds approvals that survive rebases, signed rebase commits, merge queue support for the whole stack, and auto-merge rolling out over the next few weeks. [Changelog](https://github.blog/changelog/2026-10-06-stacked-pull-requests-generally-available) | [Docs](https://gh.io/stacks)

• **Actions multi-cloud compute:** Eligible standard Linux 2-core and 4-core jobs can now run on AWS as well as Azure to cut queue times. On Enterprise Cloud this is opt-in under Enterprise settings, so your network team can review it first. [Changelog](https://github.blog/changelog/2026-10-28-github-actions-adds-multi-cloud-compute-to-improve-reliability) | [Runner IP docs](https://docs.github.com/actions/reference/runners/github-hosted-runners#ip-addresses)

• **Actions workflow lockfiles** (`PREVIEW`): Pin the exact commits behind the action tags you reference, so a moved or compromised tag can't change what runs. [Changelog](https://github.blog/changelog/2026-10-14-github-actions-workflow-lockfiles-in-public-preview) | [Docs](https://docs.github.com/actions/concepts/security/workflow-dependency-lockfiles)

• **Merge and rulesets at scale:** The async merge API is `GA` for merging individual or stacked pull requests from automation, and you can now convert all of a repo's branch protections to rulesets in one step. [Async merge API](https://github.blog/changelog/2026-10-01-github-async-merge-api-generally-available) | [Bulk ruleset migration](https://github.blog/changelog/2026-10-20-bulk-migrate-branch-protections-to-rulesets-for-a-repository)

• **Runners:** The Xcode 27 runner image is `GA`, and Actions Runner Controller 0.15.0 improves in-place upgrades for large self-hosted fleets. [Xcode 27 image](https://github.blog/changelog/2026-10-15-xcode-27-runner-image-generally-available) | [ARC 0.15.0](https://github.blog/changelog/2026-10-01-actions-runner-controller-release-0-15-0)

• **Network allowlist heads-up:** If you maintain static allowlists, GitHub added new webhook IP ranges and Actions blob storage hosts, and GitHub App installation tokens are now about 520 characters long. Make sure anything that stores those tokens can handle the new length. [Webhook IPs](https://github.blog/changelog/2026-10-29-webhook-ip-ranges-added-to-the-meta-api) | [Actions blob hosts](https://github.blog/changelog/2026-10-22-meta-api-endpoints-updated-for-actions-blob-storage) | [Token format](https://github.blog/changelog/2026-10-02-stateless-github-app-installation-tokens-rolled-out)

• **Reliability:** October had several high-impact incidents, including two short write outages on October 7, an Actions, Pages, and webhooks disruption on October 19, and pull request and webhook delays on October 21. GitHub's status history has the details, and the Universe keynote noted the multi-region Azure migration is expected to finish early next year. [Status history](https://www.githubstatus.com/history) | [September availability report](https://github.blog/news-insights/company-news/github-availability-report-september-2026/)

---

# Resources & Training

• **2026 Octoverse:** As of September, more than 40% of pull requests start with an agent (up from 17% in March), and 61% of Copilot users used more than one model. It also has an industry view for the first time, which is handy for benchmarking. [Read the report](https://github.blog/news-insights/octoverse/octoverse-commits-pushes-reach-new-highs-in-2026-as-developers-build-with-agents/)

• **ReviewBench:** GitHub's open benchmark for AI code review, which is the basis for the Copilot code review Max numbers. [Blog post](https://github.blog/ai-and-ml/github-copilot/reviewbench-an-open-benchmark-for-ai-code-review/)

• **Teach Copilot about your codebase:** A practical guide to custom instructions, skills, custom agents, and MCP servers in the Copilot app. [Guide](https://github.blog/ai-and-ml/github-copilot/github-copilot-app-for-beginners-how-to-teach-copilot-about-your-codebase/)

| Learning path | Best for | Link |
|---|---|---|
| GitHub Copilot Fundamentals, Part 1 and 2 | Teams starting an enablement program | [Part 1](https://learn.microsoft.com/en-us/training/paths/copilot/) \| [Part 2](https://learn.microsoft.com/en-us/training/paths/gh-copilot-2/) |
| Perform Code Maintenance Tasks using Copilot Agent | Teams moving into agent workflows | [Microsoft Learn](https://learn.microsoft.com/en-us/training/paths/perform-code-maintenance-tasks-github-copilot-agent/) |
| GitHub Advanced Security, Part 1 and 2 | Security and platform engineering teams | [Part 1](https://learn.microsoft.com/en-us/training/paths/github-advanced-security/) \| [Part 2](https://learn.microsoft.com/en-us/training/paths/github-advanced-security-2/) |
| GitHub Actions, Part 1 and 2 | Developers and CI/CD owners | [Part 1](https://learn.microsoft.com/en-us/training/paths/github-actions/) \| [Part 2](https://learn.microsoft.com/en-us/training/paths/github-actions-2/) |
| GitHub Administration, Part 1 and 2 | Enterprise and org admins | [Part 1](https://learn.microsoft.com/en-us/training/paths/github-administration-products/) \| [Part 2](https://learn.microsoft.com/en-us/training/paths/github-admin-2/github-admin-2/) |
| GitHub Certified: Agentic AI Developer (GH-600) | Engineers formalizing agent skills | [Cert prep](https://learn.microsoft.com/en-us/credentials/certifications/agentic-ai-developer/) |

---

# Events

## Virtual Events

| Date | Event | Topics |
|---|---|---|
| On demand | [GitHub Universe 2026 session recordings](https://reg.githubuniverse.com/flow/github/universe26/attendee-portal/page/sessioncatalog?tab.allsessions=1783449560443001ldrh&search.deliveryformat=1692799009854002CBbz) | Copilot, agents, security, enterprise |
| November 4, 2026 | [What Shipped at GitHub Universe: Put it to Work](https://github.registration.goldcast.io/webinar/de7c0ec8-6715-43f2-9489-486e95b5566a) | Universe, Copilot, product updates |
| November 4, 2026 | [How to Trust the Code You Ship](https://developer.microsoft.com/en-us/reactor/events/27685/) | Security, Code Security, pull requests |
| November 10, 2026 | [From Modernization to Innovation: Building an AI-Ready Foundation](https://developer.microsoft.com/en-us/reactor/events/27686/) | Copilot, app modernization, Azure |
| November 18, 2026 | [AI Code Hygiene: Deslopification](https://github.registration.goldcast.io/webinar/4e7ed375-4217-42ea-8421-439d25bdf161) | Code Quality, Copilot, pull requests |
| November 19, 2026 | [Measuring What Matters: Proving the ROI of AI-Powered Engineering](https://github.registration.goldcast.io/events/4b51851e-0da6-498b-99b7-d35b8a9f6d7e) | Copilot metrics, ROI, enterprise |
| December 15, 2026 | [AI-Assisted Linux Operations on Azure](https://developer.microsoft.com/en-us/reactor/events/27670/) | Copilot, operations, Azure |
| December 17, 2026 | [Building for the Frontier Firm: What's Next for GitHub + AI](https://github.registration.goldcast.io/events/dfdf494e-ecfb-4a87-b8f4-554b3cd8bf3f) | Agents, enterprise, security, roadmap |

## In-Person Events

| Date | Event | Location |
|---|---|---|
| November 9, 2026 | [GitHub Agentic Day: New York City](https://github.registration.goldcast.io/events/950184b8-647b-46cb-ab1f-b535d882374c) | New York, NY |
| November 16, 2026 | [GitHub Agentic Day: Chicago](https://github.registration.goldcast.io/events/54317cf0-c516-426d-a07d-7a17386d414f) | Chicago, IL |
| November 17-20, 2026 | [Microsoft Ignite 2026](https://register.ignite.microsoft.com/) | San Francisco, CA |
| November 18, 2026 | [GitHub Universe on the Road: Toronto](https://github.registration.goldcast.io/events/9a12405d-e612-46e3-aad9-a96329cee2da) (apply to attend) | Toronto, ON |
| November 19, 2026 | [GitHub Agentic Day: Boston](https://github.registration.goldcast.io/events/3eff30af-1473-4e43-abc3-eba041a2b1da) | Burlington, MA |
| November 19, 2026 | [GitHub Agentic Day: Montréal](https://github.registration.goldcast.io/events/679f4f7c-9ef5-4c3d-888b-3599a57d872b) | Montréal, QC |
| December 8, 2026 | [GitHub Agentic Day: Philadelphia](https://github.registration.goldcast.io/events/9977e35e-5b40-42c2-acf5-c3e522296b15) | Malvern, PA |

The Agentic Days are hands-on sessions run by GitHub and Microsoft, covering the Copilot app, CLI, and coding agents announced at Universe. They're a great fit if your team wants to see this stuff working before we talk rollout.

---

# Deprecations & Migration Notices

• **More Copilot models retire on November 16.** **Claude Opus 4.8** and **Claude Opus 5** move to Claude Opus 5.5, and **GPT-5.6 Terra** moves to GPT-6.1 Sol or GPT-6 Luna. This follows the October 2 and October 19 removals (including GPT-5.5, GPT-5.4, Gemini 3.7 Flash, Grok 4.5, and Claude Opus 4.7). If an instruction file, automation, or workflow pins one of these, switch it and confirm the replacement is enabled in your model policy. [November 16 notice](https://github.blog/changelog/2026-10-15-upcoming-deprecation-of-selected-github-copilot-models-in-mid-november) | [October 19 removals](https://github.blog/changelog/2026-10-19-github-copilot-models-deprecated-on-october-19-2026) | [October 2 removals](https://github.blog/changelog/2026-10-02-selected-models-in-github-copilot-deprecated) | [Supported models](https://docs.github.com/copilot/reference/ai-models/supported-models)

• **Secret scanning audit log change on November 12.** The `business` field in secret scanning audit log events switches from the enterprise display name to the enterprise slug. If a SIEM rule filters on the display name, update it to accept both or use `business_id`. [Changelog](https://github.blog/changelog/2026-10-20-updates-to-github-secret-scanning)

• **macOS 14 runner image retired November 2.** Move any remaining jobs to a newer macOS image. [Changelog](https://github.blog/changelog/2026-10-01-github-actions-macos-14-runner-image-retirement)

• **CodeQL and Apple's newest toolchain.** CodeQL can't do traced builds with Xcode 27 or on macOS 27, and doesn't support Swift 6.4 yet. Use build mode `none` where it's supported. [Changelog](https://github.blog/changelog/2026-10-19-codeql-changes-for-macos-27-xcode-27-and-swift-6-4) | [Docs](https://docs.github.com/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/codeql-for-compiled-languages#use-none-build-mode-for-codeql)

• **Actions retention now covers checks, workflow runs, and statuses.** They're cleaned up on the same schedule as artifacts and logs, so check your retention setting if you rely on old run history for audits. [Changelog](https://github.blog/changelog/2026-10-01-actions-retention-now-covers-checks-runs-and-statuses)

• **Push-event email notifications retired October 15.** If anyone relied on them, an Actions workflow on `push` can send the email instead. [Changelog](https://github.blog/changelog/2026-10-15-email-notifications-for-repository-push-events-have-been-retired)

---

That's the roundup. Universe gave us a lot to work with, and the GitHub Enterprise and Copilot change is the one I'd most like to talk through with each of you, since it touches licensing, budgets, and how you roll Copilot out. Send me a few times that work and I'll get something on the calendar. Let me know if you have any questions.
