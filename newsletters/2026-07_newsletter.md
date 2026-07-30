# James' Curated GitHub Newsletter, July 2026

*[Read this issue online](https://josumah.github.io/mm-newsletter/issues/2026-07.html) or [browse every past issue in the archive](https://josumah.github.io/mm-newsletter/).*

Hey everyone, this is my monthly roundup of the GitHub updates that actually matter for your team. June and July were dense, so I stretched this one across both. Three things really stood out:

- **The GitHub Copilot app is `GA`.** There's now an agent-native desktop home for macOS, Windows, and Linux, and it's the clearest signal yet that the agentic workflow is the default, not the experiment.
- **GitHub Code Quality is `GA`** (as of **July 20**), and there's a license-estimate preview so we can size the cost before it ever hits a bill.
- **Billing controls grew up for usage-based billing.** Cost center AI credit pools, per-user budgets, and a new usage-metrics impact dashboard all landed, so the June 1 shift to usage-based billing is a lot easier to plan around.

If anything in here catches your eye, send it back to me and we'll dig in. Feel free to share with your team.

# 🤖 Copilot & AI

## The GitHub Copilot app is `GA`

`GA`, **June 17**, and rolled out to everyone by **July 7**. The **GitHub Copilot app** is the agent-native desktop experience, built natively on GitHub, for macOS, Windows, and Linux. It's the home base for agent-driven development: start projects, work with agents, and explore canvases without living in a browser tab. Business and Enterprise governance still applies, so your admins keep the same controls they already set. [Changelog](https://github.blog/changelog/2026-06-17-github-copilot-app-generally-available), [available to all](https://github.blog/changelog/2026-07-07-github-copilot-app-available-to-all), and the [launch blog](https://github.blog/news-insights/product-news/github-copilot-app-the-agent-native-desktop-experience/).

## Copilot SDK is `GA`

`GA`, **June 2.** The **Copilot SDK** lets you embed Copilot's agentic engine into your own apps, services, and internal tools with a stable, production-ready API. If your platform team has been building homegrown automation around Copilot, this is the supported way to do it. [Changelog](https://github.blog/changelog/2026-06-02-copilot-sdk-is-now-generally-available).

## GitHub Agentic Workflows is in public preview

`PREVIEW`, **June 11.** **GitHub Agentic Workflows** lets you automate reasoning-based tasks like issue triage, CI failure analysis, and documentation updates by running coding agents inside GitHub Actions. A markdown file plus a command is enough to kick one off, and it no longer needs a personal access token, since it runs with the built-in `GITHUB_TOKEN`. [Changelog](https://github.blog/changelog/2026-06-11-github-agentic-workflows-is-now-in-public-preview), [no PAT required](https://github.blog/changelog/2026-06-11-agentic-workflows-no-longer-need-a-personal-access-token), and a real-world [cross-repo docs example](https://github.blog/ai-and-ml/github-copilot/automating-cross-repo-documentation-with-github-agentic-workflows/).

## Copilot cloud agent lands in Linear and Jira

The background agent now works where your teams already track work. **Copilot cloud agent for Linear** is `GA` (**July 23**), so you can assign a Linear issue and let the agent analyze and implement it asynchronously. **GitHub Copilot for Jira** is also `GA` (**June 25**) after its March preview, with model selection and other enhancements. [Linear changelog](https://github.blog/changelog/2026-07-23-copilot-cloud-agent-for-linear-is-now-generally-available) and [Jira changelog](https://github.blog/changelog/2026-06-25-github-copilot-for-jira-is-now-generally-available).

## Copilot code review: customization, AGENTS.md, and cheaper reviews

Code review got more configurable and more efficient this window. It now supports a firewall, custom setup steps, and independent runner configurations, and it reads custom instructions from the head branch so we can test changes before merging. Repository-level `AGENTS.md` support is `GA`, and a move to shared file-exploration tools cut review cost with no workflow change. [Customization](https://github.blog/changelog/2026-07-17-copilot-code-review-customization-and-configurability-improvements), [AGENTS.md support](https://github.blog/changelog/2026-06-18-copilot-code-review-agents-md-support-and-ui-improvements), and the [efficiency deep-dive](https://github.blog/ai-and-ml/github-copilot/better-tools-made-copilot-code-review-worse-heres-how-we-actually-improved-it/).

## Copilot CLI: new terminal interface is `GA`

`GA`, **June 23.** The redesigned **Copilot CLI** terminal interface we saw at Microsoft Build 2026 is now generally available, with a tabbed layout for working with GitHub from the terminal. Two more wins for platform teams: the CLI now runs in **GitHub Actions using the built-in `GITHUB_TOKEN`** (no PAT to create or store), and auto model selection routes to the best model for each task. [Terminal GA](https://github.blog/changelog/2026-06-23-copilot-cli-new-terminal-interface-is-generally-available), [no PAT in Actions](https://github.blog/changelog/2026-07-02-copilot-cli-no-longer-needs-a-personal-access-token-in-github-actions), and [auto model routing](https://github.blog/changelog/2026-07-01-copilot-cli-auto-model-selection-routes-based-on-task).

## Copilot vision, bigger context, and auto model selection

A few capability upgrades worth knowing:

- **Copilot vision** is `GA` (**July 1**). Attach images and PDFs to your chat prompts so Copilot can reason about them alongside your code. [Changelog](https://github.blog/changelog/2026-07-01-copilot-vision-is-generally-available).
- **Larger context windows and configurable reasoning** (**June 4**). One-million-token context windows plus reasoning levels you can dial up for deeper, more complex work. [Changelog](https://github.blog/changelog/2026-06-04-larger-context-windows-and-configurable-reasoning-levels-for-github-copilot).
- **Auto model selection** is `GA` in Copilot Chat (**June 17**), and enterprises can now make **auto** the default for new conversations through managed settings. That's a nice way to keep costs sane without asking every developer to pick a model. [Chat GA](https://github.blog/changelog/2026-06-17-auto-mode-in-copilot-chat-available-for-all-users) and [enterprise default](https://github.blog/changelog/2026-07-01-enterprises-can-default-to-auto-model-selection).

## New models in the picker

It was a busy stretch for models. All of these are enabled by your Business or Enterprise admin in policy before your team sees them:

- **Claude Opus 5** is `GA` (**July 24**), built for complex, long-running coding tasks. [Changelog](https://github.blog/changelog/2026-07-24-claude-opus-5-is-now-available-in-github-copilot).
- **Claude Sonnet 5** is `GA` (**June 30**), a strong everyday and agentic option. [Changelog](https://github.blog/changelog/2026-06-30-claude-sonnet-5-is-generally-available-for-github-copilot).
- **OpenAI GPT-5.6** ships in three variants, Sol, Terra, and Luna, so you can match the model to the job (**July 9**). [Changelog](https://github.blog/changelog/2026-07-09-openais-gpt-5-6-sol-terra-and-luna-are-now-available-in-github-copilot).
- **Gemini 3.6 Flash** is rolling out in preview (**July 21**), tuned for web and app development and longer agentic tasks. [Changelog](https://github.blog/changelog/2026-07-21-gemini-3-6-flash-is-now-available-in-github-copilot).
- **Kimi K2.7 Code** is `GA` and available for **Copilot Business and Copilot Enterprise** (**July 1** and **July 7**). It's the first open-weight model in the Copilot picker. [GA changelog](https://github.blog/changelog/2026-07-01-kimi-k2-7-is-now-available-in-github-copilot) and [Business and Enterprise](https://github.blog/changelog/2026-07-07-kimi-k2-7-now-available-for-copilot-business-and-enterprise).
- **MAI-Code-1-Flash**, Microsoft AI's purpose-built coding model, is `GA` for **Copilot Business and Copilot Enterprise** (**June 26**). [Changelog](https://github.blog/changelog/2026-06-26-mai-code-1-flash-for-copilot-business-and-copilot-enterprise).

## Other Copilot updates worth knowing

- **Cloud and local sandboxes** for Copilot are in public preview, so tool execution runs in an isolated environment on your machine or in the cloud. ([June 2](https://github.blog/changelog/2026-06-02-cloud-and-local-sandboxes-for-github-copilot-now-in-public-preview))
- **Agent finder** picks the right MCP servers, skills, agents, and tools for you instead of hand-wiring them into your context window. ([June 17](https://github.blog/changelog/2026-06-17-agent-finder-for-github-copilot-now-available))
- **Ask Copilot for a repository overview** gives you a high-level tour of any repo you're seeing for the first time. ([July 9](https://github.blog/changelog/2026-07-09-ask-copilot-for-a-repository-overview))
- **Browser tools for Copilot in VS Code** are `GA`, with your permission and network-domain controls preserved. ([July 1](https://github.blog/changelog/2026-07-01-browser-tools-for-github-copilot-in-vs-code-are-generally-available))
- Two good reads on making your spend go further: [getting more from each token](https://github.blog/ai-and-ml/github-copilot/getting-more-from-each-token-how-copilot-improves-context-handling-and-model-routing/) and [Copilot vs. raw API access](https://github.blog/ai-and-ml/github-copilot/copilot-vs-raw-api-access-what-are-you-actually-paying-for/).

# 💻 IDE Updates

If you're running a multi-IDE shop, here's where feature parity moved this window.

- **VS Code** shipped its May and June 2026 Copilot releases (v1.120 through v1.127), maturing the Agents experience across weekly stable builds. [June releases](https://github.blog/changelog/2026-07-08-github-copilot-in-visual-studio-code-june-2026-releases) and [May releases](https://github.blog/changelog/2026-06-03-github-copilot-in-visual-studio-code-may-releases).
- **Visual Studio** added a clearer view of Copilot usage, a new trust layer for MCP servers, and the first C++ scenarios in its June update, building on May's sharper planning and review tooling. [June update](https://github.blog/changelog/2026-07-14-github-copilot-in-visual-studio-june-update) and [May update](https://github.blog/changelog/2026-06-04-github-copilot-in-visual-studio-may-update).
- **JetBrains** expanded BYOK and model-provider flexibility, and added **Codex and Claude as agent providers** in preview along with Hooks and richer MCP management. Copilot Agent is also available inside JetBrains AI Assistant now. [BYOK](https://github.blog/changelog/2026-07-14-github-copilot-for-jetbrains-expands-byok-capabilities), [Codex provider](https://github.blog/changelog/2026-07-07-codex-as-agent-provider-and-agentic-enhancements-in-jetbrains-ides), and [AI Assistant integration](https://github.blog/changelog/2026-06-30-copilot-agent-is-now-available-in-jetbrains-ai-assistant).
- **GitHub Desktop 3.6** brings Copilot into commit authoring and merge conflict resolution and adds Git worktree support. [Changelog](https://github.blog/changelog/2026-06-26-github-desktop-3-6-worktrees-and-deeper-copilot-integration).

# 🛡️ Security & Compliance

## GitHub Code Quality is `GA`

`GA`, **July 20**, on GitHub Enterprise Cloud and GitHub Team. **GitHub Code Quality** tackles a problem a lot of you are feeling: AI accelerates code output, and quality has to keep up. It detects maintainability and reliability issues, enforces quality gates, and tracks coverage, and more than 10,000 enterprises put it through the preview. Two things that make adoption easier: a **license-estimate preview** that shows active committers so we can size the cost before it bills, and org-level enablement and targeting so you don't have to configure every repo. There's also a REST API for findings in preview. [GA changelog](https://github.blog/changelog/2026-07-20-github-code-quality-is-now-generally-available), [license estimate](https://github.blog/changelog/2026-07-13-github-code-quality-license-estimate-in-public-preview), [org-level targeting](https://github.blog/changelog/2026-07-09-organization-level-targeting-for-github-code-quality), and the [findings API](https://github.blog/changelog/2026-06-23-fetch-code-quality-findings-via-rest-api).

## Code scanning gets AI detections and agentic autofix

Two moves that widen coverage and cut remediation time. **Code scanning now surfaces AI-powered security detections on pull requests**, extending coverage to languages and frameworks CodeQL doesn't support yet (**July 14**). And **agentic autofix** is in public preview for all code scanning alerts, remediating both CodeQL and third-party findings by working across your codebase the way a developer would (**July 10**). [AI detections](https://github.blog/changelog/2026-07-14-code-scanning-shows-ai-security-detections-on-pull-requests) and [agentic autofix](https://github.blog/changelog/2026-07-10-agentic-autofix-for-code-scanning-alerts-in-public-preview).

## Secret scanning: public monitoring for enterprises

`July 1.` **Secret scanning public monitoring for enterprises** means your team can know the moment a secret leaks in public, wherever it happens. Alongside it, managing **custom patterns via REST API** is `GA`, extended metadata helps you understand the ownership and impact of a leaked credential, and there are new validators (Asana, IBM, MessageBird, Resend, Replicate) plus clearer detector-type names. [Public monitoring](https://github.blog/changelog/2026-07-01-secret-scanning-public-monitoring-for-enterprises), [custom patterns API](https://github.blog/changelog/2026-07-13-create-and-manage-secret-scanning-custom-patterns-via-rest-api), and [extended metadata](https://github.blog/changelog/2026-07-07-secret-scanning-extended-metadata-and-multipart-validation). If you want the playbook, GitHub wrote up [how it reached secret-scanning inbox zero](https://github.blog/security/application-security/how-github-used-secret-scanning-to-reach-inbox-zero/).

## CodeQL 2.26.0 adds Kotlin and AI prompt injection detection

**July 10.** **CodeQL 2.26.0** adds Kotlin 2.4.0 support and, notably, detection of **AI prompt injection** patterns, which is timely as more of your apps wire in LLM calls. Earlier in the window, 2.25.6 added Swift 6.3.2 support and incremental analysis came to Go and C/C++ for faster PR scans. [2.26.0](https://github.blog/changelog/2026-07-10-codeql-2-26-0-adds-kotlin-2-4-0-support-and-ai-prompt-injection-detection), [2.25.6](https://github.blog/changelog/2026-06-05-codeql-2-25-6-adds-swift-6-3-2-support-and-improves-c-coverage), and [incremental analysis](https://github.blog/changelog/2026-06-10-incremental-analysis-for-go-c-c-and-codeql-cli).

## More security improvements

- **Innersource security advisories** are `GA` for GitHub Advanced Security enterprise customers, so you can publish internal advisories restricted to your own repos. ([July 8](https://github.blog/changelog/2026-07-08-innersource-security-advisories-are-generally-available))
- **Self-service credential revocation** gives enterprise owners a break-glass button to instantly revoke all credentials for a compromised account. ([June 24](https://github.blog/changelog/2026-06-24-self-service-credential-revocation-for-incident-response))
- **Security validation for third-party coding agents** is `GA`, covering agents like Claude and OpenAI Codex that work directly in your repos. ([June 9](https://github.blog/changelog/2026-06-09-security-validation-for-third-party-coding-agents))
- **Dependabot** now waits a default **three-day cooldown** before opening a version-update PR, giving maintainers and researchers time to catch a bad release first. ([July 14](https://github.blog/changelog/2026-07-14-dependabot-version-updates-introduce-default-package-cooldown))
- **Open source license compliance** is in public preview, with ruleset-based checks that enforce a centralized policy and block noncompliant dependencies. ([June 30](https://github.blog/changelog/2026-06-30-open-source-license-compliance-is-in-public-preview))
- **npm v12** is `GA` and turns on install-time security defaults, plus npm added preventive protection for high-impact accounts. ([npm v12](https://github.blog/changelog/2026-07-08-npm-install-time-security-and-gat-bypass2fa-deprecation), [account protection](https://github.blog/changelog/2026-06-25-npm-adds-preventive-account-protection-for-high-impact-accounts))
- **IP allow list coverage for EMU namespaces** is `GA`, so you can enforce native IP allow lists across your managed-user namespaces. ([June 8](https://github.blog/changelog/2026-06-08-ip-allow-list-coverage-for-emu-namespaces-in-general-availability))
- A practical read for your teams: [6 security settings every maintainer should enable this week](https://github.blog/security/6-security-settings-every-github-maintainer-should-enable-this-week/).

# 🛠️ Platform & DevEx

## The new pull requests dashboard is `GA`

**July 9.** The refreshed pull requests dashboard at github.com/pulls is `GA`, giving you a single home to track, prioritize, and act on the PRs that need attention. Good one to point your engineering managers at. [Changelog](https://github.blog/changelog/2026-07-09-new-pull-requests-dashboard-is-now-generally-available).

## Projects and Issues keep getting sharper

Several updates make planning easier: **advanced search for Projects** is `GA` with logical AND/OR filtering, **issue fields** are `GA` (and ship in GHES 3.23), **multi-select fields** for Projects and Issues are in preview, and **agent automation controls** in Issues let you review agent-driven label, type, and assignment changes before they apply. [Advanced search](https://github.blog/changelog/2026-07-16-advanced-search-for-projects-is-generally-available), [issue fields](https://github.blog/changelog/2026-07-02-issue-fields-are-now-generally-available), [multi-select fields](https://github.blog/changelog/2026-07-23-multi-select-fields-for-projects-and-issues-in-public-preview), and [agent automation controls](https://github.blog/changelog/2026-07-23-agent-automation-controls-in-github-issues-in-public-preview).

## More platform updates

- **Rulesets** can now restrict who can dismiss pull request reviews (`GA`), and you can block merges when test coverage drops below your thresholds. ([dismiss reviews](https://github.blog/changelog/2026-07-07-restrict-who-can-dismiss-reviews-in-rulesets), [coverage protection](https://github.blog/changelog/2026-06-30-github-code-coverage-merge-protection-for-pull-requests))
- **GitHub Actions**: steps can now run in parallel with `background`, hosted-runner cache tokens are read-only for untrusted triggers, admins get more control over who can use hosted runners, RHEL 9 and 10 larger-runner images are in preview, and workflow execution protections let you allow-list who can trigger workflows. ([parallel steps](https://github.blog/changelog/2026-06-25-actions-steps-can-now-be-run-in-parallel), [read-only cache](https://github.blog/changelog/2026-06-26-read-only-actions-cache-for-untrusted-triggers), [runner controls](https://github.blog/changelog/2026-06-25-more-control-over-your-github-hosted-runners), [RHEL runners](https://github.blog/changelog/2026-06-25-red-hat-enterprise-linux-runner-images-are-now-in-public-preview), [workflow protections](https://github.blog/changelog/2026-06-18-control-who-and-what-triggers-github-actions-workflows))
- **GitHub MCP Server** now supports the next, stateless MCP specification ahead of the **July 28** protocol change, so plan any MCP integrations around it. ([July 23](https://github.blog/changelog/2026-07-23-github-mcp-server-supports-the-next-mcp-specification))
- **GitHub CLI**: read remote repo files without cloning, manage discussions, and work with sub-issues, types, and dependencies straight from the terminal. ([read files](https://github.blog/changelog/2026-06-17-read-remote-repository-content-with-github-cli), [discussions](https://github.blog/changelog/2026-06-10-list-view-and-create-discussions-in-github-cli), [sub-issues](https://github.blog/changelog/2026-06-10-manage-sub-issues-types-and-dependencies-from-github-cli))
- Repository admins can now **archive pull requests** to take them out of public view without deleting them. ([July 16](https://github.blog/changelog/2026-07-16-repository-admins-can-archive-pull-requests))

# 🏢 Enterprise Administration

## Enterprise managed-settings.json is `GA`

`GA`, **July 1.** This is the control plane for a lot of what's in this newsletter. **Enterprise managed-settings.json** lets you define AI governance through a single file in a `.github-private` repo: set the default model to **auto**, restrict which plugin marketplaces users can install (`strictKnownMarketplaces`, in preview), and turn off bypass-permissions mode. [Managed settings GA](https://github.blog/changelog/2026-07-01-enterprise-managed-settings-json-is-generally-available), [auto default](https://github.blog/changelog/2026-07-01-enterprises-can-default-to-auto-model-selection), and [bypass controls](https://github.blog/changelog/2026-06-17-enterprise-managed-settings-now-support-bypass-permission-controls).

## Deliver Copilot settings by MDM and control telemetry

Two governance wins for regulated teams. Admins can now **deploy managed Copilot settings via MDM** and file-based config in VS Code and the CLI, and can **mandate an approved OpenTelemetry collector** so Copilot telemetry flows to one place without each developer setting environment variables. [MDM delivery](https://github.blog/changelog/2026-07-08-deploy-managed-copilot-settings-via-mdm-in-vs-code-and-cli) and [OpenTelemetry export](https://github.blog/changelog/2026-07-08-enterprise-managed-opentelemetry-export-for-vs-code-and-cli).

## Enterprise Teams is `GA`

**June 4.** **Enterprise Teams** lets admins define a group of users once at the enterprise level and reuse it, which cleans up access and cost attribution across a lot of orgs. It first previewed last September. [Changelog](https://github.blog/changelog/2026-06-04-enterprise-teams-is-now-generally-available). Copilot agent session streaming for EMU customers is also in preview, giving you session data across all clients including data-resident deployments. [Session streaming](https://github.blog/changelog/2026-07-02-copilot-agent-session-streaming-is-now-in-public-preview).

## Billing and usage visibility, built for usage-based billing

If you're planning around the usage-based billing model, this is the section to share with your billing folks. Cost management got a lot more granular:

- **Cost center AI credit pools and per-user budgets** can now be managed directly in the billing UI, and you can cap how much of your monthly included AI credits a cost center consumes. ([AI credit pools](https://github.blog/changelog/2026-07-20-ai-credit-pools-for-cost-centers-in-the-billing-ui), [per-user budgets](https://github.blog/changelog/2026-07-07-per-user-budgets-for-cost-centers-in-the-billing-ui))
- **Cost centers now support enterprise teams**, and the per-enterprise limit doubled to **500 cost centers**. ([enterprise teams](https://github.blog/changelog/2026-06-25-assign-enterprise-teams-to-cost-centers), [500 cost centers](https://github.blog/changelog/2026-06-10-enterprises-can-now-create-up-to-500-cost-centers))
- A **new Copilot usage-metrics impact dashboard** helps admins and org owners tell the impact story, and **repository-level usage metrics** are `GA` through the REST API. ([impact dashboard](https://github.blog/changelog/2026-07-22-new-copilot-usage-metrics-impact-dashboard), [repo-level metrics](https://github.blog/changelog/2026-07-17-repository-level-github-copilot-usage-metrics-generally-available))
- Individual developers can now see **AI credits used per billing cycle** even without a personal budget, which helps teams self-regulate. ([July 20](https://github.blog/changelog/2026-07-20-copilot-users-can-now-see-ai-credits-used-per-billing-cycle))
- Budget, usage-management, and billing-report APIs are all `GA` if you'd rather automate this. ([budget APIs](https://github.blog/changelog/2026-06-04-budget-and-usage-management-apis-now-generally-available), [report API](https://github.blog/changelog/2026-06-04-api-access-to-billing-usage-reports-now-generally-available))

## GitHub Enterprise Server 3.21 is `GA`

**June 11.** For our GHES customers, **3.21** improves deployment efficiency, monitoring, code security, and policy management, and makes organization custom properties `GA`. [Changelog](https://github.blog/changelog/2026-06-11-github-enterprise-server-3-21-is-now-generally-available). Two admin conveniences also shipped: a REST API to manage Visual Studio Subscription assignments, and separate SSO and Organizations pages in settings. [VSS API](https://github.blog/changelog/2026-07-16-rest-api-endpoints-for-visual-studio-subscription-management) and [SSO pages](https://github.blog/changelog/2026-07-13-separate-sso-and-organizations-pages-in-settings).

# 📅 Events & Training

A few things worth putting on the calendar.

## GitHub Universe 2026 (October 28-29)

GitHub's flagship is back at the Fort Mason Center in San Francisco on **October 28-29, 2026**, and it's squarely focused on the agentic era. If your team is planning second-half roadmap work, this is the one to block calendars for. [Register and learn more](https://githubuniverse.com/).

## Microsoft Ignite 2026 (November 16-20)

Microsoft's flagship for IT and platform leaders, in San Francisco and online. Expect major Copilot, GitHub, and Azure governance content. [Learn more](https://ignite.microsoft.com/).

## Ongoing training

- **Microsoft Reactor** runs free, recurring GitHub and Copilot sessions. [Browse the catalog](https://developer.microsoft.com/en-us/reactor/?search=github).
- **Microsoft Learn** has GitHub training paths from beginner to advanced. [Start here](https://learn.microsoft.com/en-us/training/github/).
- Two easy enablement links for your teams: the [GitHub essentials roadmap](https://github.blog/developer-skills/github/github-for-beginners-your-roadmap-to-mastering-the-github-essentials/) and a [Copilot CLI slash-command primer](https://github.blog/ai-and-ml/github-copilot/github-copilot-cli-for-beginners-overview-of-common-slash-commands/).

# 🗓️ Deprecations & Migration Notices

A few dates to get ahead of:

- **GitHub Models is fully retired on July 30, 2026.** If your team touched it, migrate now. ([changelog](https://github.blog/changelog/2026-07-01-github-models-is-being-fully-retired-on-july-30-2026))
- **Gemini 2.5 Pro and Gemini 3 Flash** are deprecated across Copilot on **July 31, 2026**. Swap any pinned configs. ([changelog](https://github.blog/changelog/2026-07-02-upcoming-deprecation-of-gemini-2-5-pro-and-gemini-3-flash))
- **The Copilot Billing Preview app retires on August 3, 2026.** Spend visibility moves into the native billing experience. ([changelog](https://github.blog/changelog/2026-07-07-copilot-billing-preview-app-will-be-retired-on-august-3))
- **A GHES support-bundle upload change takes effect August 18, 2026.** GHES admins should read this ahead of time. ([changelog](https://github.blog/changelog/2026-07-22-upcoming-ghes-change-impacting-uploading-support-bundles))
- **A cloud data-retention policy for closed Dependabot alerts starts August 25, 2026.** ([changelog](https://github.blog/changelog/2026-06-30-cloud-data-retention-policy-for-closed-security-alerts))
- **npm v12** turns on breaking install-time security defaults and begins the GAT bypass2fa deprecation. ([changelog](https://github.blog/changelog/2026-07-08-npm-install-time-security-and-gat-bypass2fa-deprecation))
- **Actions minimum-version enforcement** for self-hosted runners is resuming on github.com and GHEC with Data Residency, so update older runners. ([changelog](https://github.blog/changelog/2026-06-12-github-actions-minimum-version-enforcement-timeline-for-self-hosted-runners))

# Wrapping up

That's the roundup for June and July. The through-line is pretty clear: the agentic workflow is now the default, with the **Copilot app**, **SDK**, and **CLI** all at `GA`, a wave of new models, and **agentic workflows** automating the busywork. Just as important, the guardrails caught up, so managed settings, cost center budgets, and the usage-metrics dashboard give us real levers to govern and pay for all of it, which matters a lot now that we're in the usage-based billing world.

If you want to talk through any of these, especially Code Quality, the new billing controls, or what an agent rollout could look like for your team, just let me know and we'll grab time. Happy to jump on a call.

Talk soon,
James
