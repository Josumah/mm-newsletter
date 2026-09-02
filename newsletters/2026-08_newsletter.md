# James' Curated GitHub Newsletter, August 2026

*[Read this issue online](https://josumah.github.io/mm-newsletter/issues/2026-08.html) or [browse every past issue in the archive](https://josumah.github.io/mm-newsletter/).*

Hey everyone, here's my roundup of the GitHub updates that mattered most from July 1 through August 2. The theme this time is pretty clear: agents kept getting more capable, but the controls around cost, policy, quality, and security finally started catching up. That's the shift that makes broader adoption feel practical instead of experimental. If something here lines up with what your team is working through, send it back to me and we'll dig in.

• **Enterprise-managed settings now follow Copilot across more clients**, so the same guardrails can cover VS Code, Copilot CLI, the Copilot app, and cloud agent work.
• **GitHub Code Quality is now `GA`**, with quality gates and AI-assisted findings, plus a new standalone pricing model that needs a quick enablement review.
• **AI spend and adoption reporting got much sharper**, with cost-center credit pools, per-user budgets, repository metrics, and an impact dashboard.

---

# Save the Date: GitHub Universe 2026

**GitHub Universe 2026** is happening **October 28-29** at Fort Mason Center in San Francisco, with virtual attendance available too. This one sits outside my normal two-month event window, but it's GitHub's flagship event and worth getting on the calendar early if your team wants the latest product announcements, technical sessions, and customer stories in one place. [Event details](https://githubuniverse.com/)

---

# More agents, tighter controls

## **Enterprise-managed Copilot settings** (`GA`)

Enterprise-managed settings started the month in VS Code and Copilot CLI, then expanded to the Copilot app and Copilot cloud agent. We can now define approved plugins and marketplaces, control whether users can bypass approval prompts, and set model defaults from one managed configuration. The Copilot app also has its own access policy, so admins can enable it everywhere, turn it off, or let organizations decide without tying that choice to Copilot CLI. [Initial GA](https://github.blog/changelog/2026-07-01-enterprise-managed-settings-json-is-generally-available) | [Client expansion](https://github.blog/changelog/2026-07-27-enterprise-managed-settings-now-apply-to-the-github-copilot-app) | [App policy](https://github.blog/changelog/2026-07-27-manage-github-copilot-app-access-with-a-dedicated-policy) | [Docs](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/configure-enterprise-managed-settings)

## **AI spend controls and adoption reporting**

Usage-based billing is easier to manage when included credits, overage, and adoption are not blended into one number. Cost centers can now cap the included AI-credit pool they draw from, while per-user budgets control metered spend and follow assigned users or enterprise teams as membership changes. On the reporting side, repository-level metrics show where coding agent and code review activity is happening, and the impact dashboard groups users by adoption phase so we can target enablement instead of just counting active seats. [AI credit pools](https://github.blog/changelog/2026-07-02-cost-centers-now-support-included-usage-caps) | [Per-user budgets](https://github.blog/changelog/2026-07-07-per-user-budgets-for-cost-centers-in-the-billing-ui) | [Repository metrics](https://github.blog/changelog/2026-07-17-repository-level-github-copilot-usage-metrics-generally-available) | [Impact dashboard](https://github.blog/changelog/2026-07-22-new-copilot-usage-metrics-impact-dashboard) | [Budget docs](https://docs.github.com/enterprise-cloud@latest/copilot/concepts/billing/budgets-for-usage-based-billing)

## **GitHub Code Quality** (`GA`)

GitHub Code Quality is now generally available on GitHub Enterprise Cloud and GitHub Team. It combines deterministic CodeQL analysis with AI-assisted maintainability and reliability findings, adds code coverage on pull requests, and supports ruleset-based quality gates with an evaluate mode for gradual rollout. This is a standalone paid product at **$10 per active committer per month**, plus usage-based charges for AI-powered work and the Actions compute used for analysis, so it's worth checking where the preview was enabled before the next bill. [GA announcement](https://github.blog/changelog/2026-07-20-github-code-quality-is-now-generally-available) | [Product docs](https://docs.github.com/code-security/concepts/about-code-quality) | [Billing docs](https://docs.github.com/billing/concepts/product-billing/github-code-quality)

---

# Copilot & AI

## **Copilot code review gets skills, MCP, and runtime controls** (`GA`)

Copilot code review can now use repository agent skills and read-only MCP connections to bring team standards, service catalogs, documentation, and other approved context into a review. It also gained a default firewall, independent runner settings, custom setup steps, and the ability to test instruction changes from the pull request's head branch before merging them. GitHub also shared how better review-specific instructions cut average review cost by roughly 20% without reducing review quality, which is a useful reminder that the workflow around an agent matters as much as the model. [Skills and MCP GA](https://github.blog/changelog/2026-07-29-copilot-code-review-agent-skills-and-mcp-now-generally-available) | [Runtime controls](https://github.blog/changelog/2026-07-17-copilot-code-review-customization-and-configurability-improvements) | [Agent skills docs](https://docs.github.com/copilot/concepts/agents/about-agent-skills) | [Engineering deep-dive](https://github.blog/ai-and-ml/github-copilot/better-tools-made-copilot-code-review-worse-heres-how-we-actually-improved-it/)

## **Model choice expanded, and governance changed with it**

July added **Kimi K2.7 Code**, **GPT-5.6 Sol, Terra, and Luna**, **Gemini 3.6 Flash**, **Claude Opus 5**, and **Grok 4.5** to Copilot. The bigger admin change is the new default-enablement policy: beginning August 26, newly GA models that are not explicitly configured follow the enterprise or organization default, so teams that want manual approval for every model should disable that policy. Enterprise-team model targeting also entered `PREVIEW`, letting admins keep a baseline for everyone and grant optional models to role-based or early-adopter groups. [Default enablement](https://github.blog/changelog/2026-07-29-default-model-enablement-for-copilot-business-and-enterprise) | [Team targeting preview](https://github.blog/changelog/2026-07-31-enterprise-teams-model-policy-targeting-in-public-preview) | [Supported models](https://docs.github.com/copilot/reference/ai-models/supported-models)

## **Copilot CLI in Actions no longer needs a PAT**

Copilot CLI can now authenticate in GitHub Actions with the workflow's built-in `GITHUB_TOKEN`, so we can remove a long-lived personal access token from these automations. Organization-owned repositories need the `copilot-requests: write` permission, and the resulting AI credits are billed to the organization. Cost centers and per-session credit limits give us the guardrails to pair with that simpler authentication model. [Changelog](https://github.blog/changelog/2026-07-02-copilot-cli-no-longer-needs-a-personal-access-token-in-github-actions) | [Setup guide](https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli-in-actions)

## **Copilot cloud agent for Linear** (`GA`)

Linear teams can assign an issue to Copilot cloud agent and get progress updates back in the issue while the agent works in an isolated environment and opens a draft pull request. Model selection, custom agents, branch targeting, and steering comments can all be controlled from Linear. [Changelog](https://github.blog/changelog/2026-07-23-copilot-cloud-agent-for-linear-is-now-generally-available) | [Cloud agent docs](https://docs.github.com/copilot/concepts/agents/cloud-agent/about-cloud-agent)

---

# IDE Updates

## **VS Code's July releases focused on multi-agent work**

VS Code 1.127 through 1.131 made the Agents window easier to use for real project work. Teams can review code beside chat, isolate sessions with worktrees across multiple agent harnesses, fork related conversations, track active subagents, and act on failed checks or review comments without leaving the session. Browser tools are also `GA`, with isolated agent tabs, explicit sharing for user-opened pages, and admin controls for browser access and network domains. [July release summary](https://github.blog/changelog/2026-07-30-github-copilot-in-visual-studio-code-july-2026-releases) | [Browser tools](https://github.blog/changelog/2026-07-01-browser-tools-for-github-copilot-in-vs-code-are-generally-available) | [Release notes](https://aka.ms/VSCode/Release)

## **Visual Studio adds a Copilot SDK-based agent** (`PREVIEW`)

Visual Studio's July update added a new agent built on the Copilot SDK, plus built-in .NET and Azure skills, selected-code review, and organization-level custom instructions. That's a strong parity move for teams that live in Visual Studio and want the same reusable agent patterns showing up elsewhere in the Copilot ecosystem. [Changelog](https://github.blog/changelog/2026-07-30-github-copilot-in-visual-studio-july-update) | [Visual Studio blog](https://devblogs.microsoft.com/visualstudio/visual-studio-july-update-meet-the-new-agent-powered-by-copilot-sdk) | [Release notes](https://learn.microsoft.com/visualstudio/releases/2026/release-notes)

## **JetBrains adds stronger agent and model controls**

Copilot for JetBrains added Codex and Claude agent improvements, BYOK support, local sandboxing in `PREVIEW`, MCP management, and agent debug logs. Later in the month it added OpenTelemetry export, token limits for custom endpoints, built-in model enablement controls, and MCP plus custom-agent support in Claude flows. For mixed-IDE enterprises, those governance and observability controls matter more than simple feature-count parity. [Agent update](https://github.blog/changelog/2026-07-07-codex-as-agent-provider-and-agentic-enhancements-in-jetbrains-ides) | [Governance update](https://github.blog/changelog/2026-07-27-github-copilot-for-jetbrains-adds-improvved-opentelemetry-configuration-and-model-management) | [Plugin releases](https://plugins.jetbrains.com/plugin/17718-github-copilot--your-ai-pair-programmer/versions)

---

# Enterprise & Security

## **Agentic security remediation moves into the pull request** (`PREVIEW`)

Agentic autofix can now take a first- or third-party code scanning alert, explore the codebase, propose a fix, rerun the original analysis, and open a validated draft pull request. AI security detections also extend pull request findings to languages and frameworks outside CodeQL's built-in coverage. Both features require GitHub Code Security or GitHub Advanced Security plus Copilot access, and they consume AI credits, while agentic autofix also uses Actions minutes. [Agentic autofix](https://github.blog/changelog/2026-07-10-agentic-autofix-for-code-scanning-alerts-in-public-preview) | [AI security detections](https://github.blog/changelog/2026-07-14-code-scanning-shows-ai-security-detections-on-pull-requests) | [Code scanning docs](https://docs.github.com/code-security/code-scanning/introduction-to-code-scanning/about-code-scanning)

## **Secret scanning public monitoring** (`PREVIEW`)

Public monitoring looks for secrets attributed to your enterprise anywhere in public GitHub content, not just repositories the enterprise owns. Attribution uses enterprise membership and verified domains, which helps security teams catch leaks from personal forks, public issues, or outside open source contributions. It's available at **no additional cost** for GitHub Enterprise Cloud customers with Secret Protection or Advanced Security. [Changelog](https://github.blog/changelog/2026-07-01-secret-scanning-public-monitoring-for-enterprises) | [Secret scanning docs](https://docs.github.com/code-security/secret-scanning/introduction/about-secret-scanning)

## **Supply chain protections got more automatic**

GitHub Actions now holds certain suspicious workflow runs in public repositories until a write-access collaborator approves them, with no setup required. Dependabot malware alerts also gained broader npm, PyPI, and multi-ecosystem coverage through OpenSSF malicious-package advisories. If your teams are getting buried in routine version updates, GitHub also published a practical guide for grouping updates and slowing the cadence without delaying security fixes. [Actions protection](https://github.blog/changelog/2026-07-28-github-actions-holds-potentially-malicious-workflows-for-approval) | [Dependabot malware coverage](https://github.blog/changelog/2026-07-28-dependabot-alerts-on-malicious-packages-across-more-ecosystems) | [Supply chain overview](https://github.blog/security/supply-chain-security/disrupting-supply-chain-attacks-on-npm-and-github-actions/) | [Dependabot guide](https://github.blog/security/supply-chain-security/tame-dependabot-group-your-updates-slow-the-cadence-keep-security-fast/)

• **Worth noting:** Secret scanning custom patterns can now be created and managed through repository, organization, and enterprise REST APIs. Dry runs and final publication still happen in the UI. [Changelog](https://github.blog/changelog/2026-07-13-create-and-manage-secret-scanning-custom-patterns-via-rest-api) | [REST API docs](https://docs.github.com/rest/secret-scanning)

---

# Platform & DevEx

## **Stacked pull requests** (`PREVIEW`)

Stacked pull requests break a large change into smaller, ordered pull requests that can be reviewed in parallel and merged together when ready. Existing branch protections, required checks, and review rules still apply, which makes stacks a practical response to the larger and faster changes agentic development can produce. [Changelog](https://github.blog/changelog/2026-07-30-stacked-pull-requests-are-now-in-public-preview) | [Docs](https://gh.io/stacks)

• **GitHub Actions self-repository syntax:** A `uses:` value beginning with `$/` now resolves an action or reusable workflow from the same repository at the exact running commit. That removes the checkout requirement and works cleanly with enterprise policies that require full-length commit SHA pinning. [Changelog](https://github.blog/changelog/2026-07-30-reference-same-repository-actions-with-self-repository-syntax) | [Docs](https://docs.github.com/actions/how-tos/write-workflows/choose-what-workflows-do/find-and-customize-actions)

---

# Reliability & Incident Learnings

GitHub had a concentrated run of Actions and core-platform incidents in July, and the resolved Statuspage updates include more detail than the usual service-restored notice. The July 24 network incident affected Actions, Issues, Copilot, Git pushes, and authentication, while a separate database migration issue affected **113,930 pull request creation attempts from 50,904 users**. On July 25, two Actions degradation periods tied to Redis maintenance and regional capacity changes peaked with **60% of runs failing with infrastructure errors** during the second period. [Multi-service incident](https://stspg.io/j5c80shxqm53) | [Pull request incident](https://stspg.io/sm1tp7kfm4vj) | [Actions incident](https://www.githubstatus.com/incidents/s65j9gslmfm8)

The follow-up work is the useful part: stronger preflight and deployment validation, safer maintenance recovery checks, better autoscaling and memory alerts, certificate-expiry safeguards, more automated failover, and an accelerated data-center network upgrade. Copilot also had several upstream model-provider disruptions; other models generally stayed available, so selecting **Auto** or another model remained the practical fallback. [GitHub incident history](https://www.githubstatus.com/history)

---

# Resources & Training

• **Cross-repository agentic documentation:** The Aspire team used GitHub Agentic Workflows to open 82 feature-documentation pull requests at a median of 44.8 hours after the product pull request, with guarded write paths and subject-matter review. [Case study](https://github.blog/ai-and-ml/github-copilot/automating-cross-repo-documentation-with-github-agentic-workflows/)

| Learning path | Best for | Link |
|---|---|---|
| GitHub Copilot Fundamentals, Part 1 | Teams starting an enablement program | [Microsoft Learn](https://learn.microsoft.com/en-us/training/paths/copilot/) |
| GitHub Copilot Fundamentals, Part 2 | Teams moving into deeper Copilot workflows | [Microsoft Learn](https://learn.microsoft.com/en-us/training/paths/gh-copilot-2/) |
| GitHub Advanced Security | Security and platform engineering teams | [Microsoft Learn](https://learn.microsoft.com/en-us/training/paths/github-advanced-security/) |
| GitHub Actions | Developers and CI/CD owners | [Microsoft Learn](https://learn.microsoft.com/en-us/training/paths/github-actions/) |

---

# Events

## Virtual Events

| Date | Event | Topics |
|---|---|---|
| September 4, 2026 | [The Story of VS Code](https://developer.microsoft.com/en-us/reactor/events/27557/) | VS Code, AI, developer tools |
| September 8, 2026 | [CoreStory + GitHub Copilot: Turning Plausible Suggestions Into Correct Ones](https://developer.microsoft.com/en-us/reactor/events/27459/) | Copilot, MCP, code context |
| September 8, 2026 | [AI Genius: Code with AI](https://developer.microsoft.com/en-us/reactor/events/27463/) | Copilot app, CLI, agentic workflows |
| September 9, 2026 | [MCP Live!](https://developer.microsoft.com/en-us/reactor/events/27448/) | MCP, GitHub, governance, security |

---

# Deprecations & Migration Notices

• **GitHub Models retired on July 30.** The playground, model catalog, inference API, and BYOK capability are no longer available. Microsoft Foundry is the recommended path for model-catalog access, while GitHub-native agent workflows continue through Copilot. [Retirement notice](https://github.blog/changelog/2026-07-30-github-models-is-now-retired) | [Docs](https://docs.github.com/github-models)

• **Several Copilot models were removed on September 1.** The list included Gemini 3.1 Pro, Claude Opus 4.5 and 4.6, Claude Sonnet 4.5 and most 4.6 access, and Raptor Mini. If an instruction file or workflow still pins one of those models, move it to a supported replacement and confirm the replacement is enabled in enterprise policy. [Deprecation notice](https://github.blog/changelog/2026-07-31-upcoming-august-2026-model-deprecations-in-github-copilot) | [Supported models](https://docs.github.com/copilot/reference/ai-models/supported-models)

• **The Copilot Billing Preview app retired on August 3.** AI usage, exports, cost centers, and budgets now live in GitHub's built-in billing settings and APIs. [Retirement notice](https://github.blog/changelog/2026-07-07-copilot-billing-preview-app-will-be-retired-on-august-3) | [Billing docs](https://docs.github.com/copilot/concepts/billing)

---

That's the roundup. The big question for most teams is no longer whether agentic development is showing up, it's whether the policy, cost, and review model is ready for it. Let me know if you have any questions or want to walk through what these changes mean for your environment.
