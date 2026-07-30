# James' Curated GitHub Newsletter, April 2026

Hey everyone, this is my monthly roundup of the GitHub updates that actually matter for your team. April was a big one. Three things really stood out:

- **Copilot data residency and FedRAMP-authorized models are now `GA`**, so the data-sovereignty conversations that have been sitting open can finally get answered.
- **Copilot cloud agent grew up.** It can now research, plan, and code without forcing a pull request, and you can steer it from issues, projects, mobile, or the web.
- **Heads up for billing folks**: Copilot moves to usage-based billing on June 1, 2026, and Copilot code review starts consuming GitHub Actions minutes the same day. There's time to plan, but the time is now.

If anything in here catches your eye, send it back to me and we'll dig in. Feel free to share with your team.

# 🤖 Copilot & AI

## Data residency (US + EU) and FedRAMP-authorized models are `GA`

This is the launch a lot of you have been waiting on. As of **April 13**, every paid Copilot feature (agent mode, inline suggestions, chat, cloud agent, code review, PR summaries, and Copilot CLI) can run exclusively through data-resident model endpoints. EU coverage matches Microsoft's EU Data Boundary, so EU member states plus EFTA (Iceland, Liechtenstein, Norway, Switzerland) starting **May 1, 2026**. For US public sector customers, the underlying model hosts and infrastructure are FedRAMP Moderate authorized.

A few things worth knowing:

- **Models at launch**: GPT-5.4, Claude Sonnet 4.6, Claude Opus 4.6, and more. Gemini isn't in scope yet.
- **Pricing**: data-resident and FedRAMP requests carry a 10% increase in the model multiplier. So a request that normally costs 1 premium request unit costs 1.1.
- **Off by default**. Your enterprise or org admins have to opt in from Copilot settings.
- **Roadmap**: Australia and Japan are coming later in 2026.

Read more in the [data residency announcement](https://github.blog/changelog/2026-04-13-copilot-data-residency-in-us-eu-and-fedramp-compliance-now-available).

## Copilot cloud agent: research, plan, and code (not just open PRs)

`GA`, **April 1.** The cloud agent (formerly Copilot coding agent) is no longer locked to a pull-request workflow. Three new modes that change how you'd use it:

- **Branch-only work**. The agent generates code on a branch and you decide when to open the PR.
- **Implementation plans**. Ask for a plan first, review and approve the approach, then the agent codes against it.
- **Deep research**. Kick off a research session for thorough investigation of an unfamiliar part of the codebase.

Available with all paid Copilot plans. Business and Enterprise admins enable cloud agent before users see it. [Read the changelog](https://github.blog/changelog/2026-04-01-research-plan-and-code-with-copilot-cloud-agent).

## Copilot SDK is in public preview

`PREVIEW`, **April 2.** The SDK exposes the same agent runtime that powers cloud agent and Copilot CLI, so you get tool invocation, streaming, file operations, and multi-turn sessions out of the box. Available in Node.js/TypeScript, Python, Go, .NET, and Java. Highlights: custom tools and agents, fine-grained system prompt customization (replace, append, prepend, transform), blob attachments, OpenTelemetry distributed tracing, a permission framework, and BYOK for OpenAI, Microsoft Foundry, and Anthropic. Each prompt counts toward your premium request quota. [Changelog](https://github.blog/changelog/2026-04-02-copilot-sdk-in-public-preview) and the [SDK repo](https://github.com/github/copilot-sdk).

## Copilot organization custom instructions are `GA`

**April 2.** Org admins can now set default instructions that guide Copilot's behavior across every repo in the org. Instructions apply to Copilot Chat on github.com, Copilot code review, and Copilot cloud agent. Configure at Org settings, then Copilot, then Custom instructions. This is a great low-cost lever if your team has standards (style, frameworks, security patterns) you want Copilot to respect by default. [Changelog](https://github.blog/changelog/2026-04-02-copilot-organization-custom-instructions-are-generally-available).

## Two new models: GPT-5.5 and Claude Opus 4.7

Both `GA`, both shipped this month, both available across VS Code, Visual Studio, Copilot CLI, cloud agent, github.com, GitHub Mobile, JetBrains, Xcode, and Eclipse.

- **GPT-5.5** (April 24). OpenAI's latest. Strongest performance on complex multi-step agentic coding tasks. Launching with a **7.5x premium request multiplier** as promotional pricing, so worth modeling against your usage before turning it on broadly. [Changelog](https://github.blog/changelog/2026-04-24-gpt-5-5-is-generally-available-for-github-copilot).
- **Claude Opus 4.7** (April 16). Anthropic's latest Opus. Stronger multi-step task performance, more reliable agentic execution. Over the next few weeks Opus 4.7 replaces Opus 4.5 and 4.6 in the picker. Same **7.5x promotional multiplier** through April 30. [Changelog](https://github.blog/changelog/2026-04-16-claude-opus-4-7-is-generally-available).

For both, your Business or Enterprise admin has to enable the model in policy before users see it.

## BYOK (Bring Your Own Language Model Key) in VS Code is `GA`

**April 22.** Copilot Business and Enterprise users can now use their own API keys in VS Code. It supports Anthropic, Gemini, OpenAI, OpenRouter, and Azure, plus locally running models through Ollama and Foundry Local. BYOK works everywhere in VS Code Chat, including the built-in plan agent and custom agents. It does NOT apply to code completions. Usage is billed directly by your provider and doesn't count against Copilot quotas. The policy is enabled by default; admins can disable it per org from Copilot policy settings. [Changelog](https://github.blog/changelog/2026-04-22-bring-your-own-language-model-key-in-vs-code-now-available).

## Copilot CLI: BYOK, local models, and air-gapped mode

`GA`, **April 7.** Copilot CLI now supports BYOK alongside fully local providers (Ollama, vLLM, Foundry Local). Two big enterprise wins:

- `COPILOT_OFFLINE=true` enables fully air-gapped operation. Telemetry is disabled and the CLI only contacts your configured provider.
- GitHub authentication becomes optional when using your own provider. Sign in if you want `/delegate`, GitHub Code Search, and GitHub MCP server access on top.

Models need tool calling, streaming, and at least a 128k token context window. [Changelog](https://github.blog/changelog/2026-04-07-copilot-cli-now-supports-byok-and-local-models).

## Remote control for Copilot CLI sessions on web and mobile

`PREVIEW`, **April 13.** Run `copilot --remote` and you can monitor and steer a running CLI session from GitHub on the web or in the GitHub Mobile apps. The CLI shows a link and QR code, and activity stays in sync. Send mid-session steering messages, switch between plan, interactive, and autopilot modes, approve or deny permissions, respond to prompts. Mobile is available via Google Play beta and iOS TestFlight. Business and Enterprise admins must enable the remote control and CLI policies. [Changelog](https://github.blog/changelog/2026-04-13-remote-control-cli-sessions-on-web-and-mobile-in-public-preview).

## View and manage agent sessions from Issues and Projects

`GA`, **April 23.** Cloud agent sessions are now visible and steerable directly from GitHub Issues and Projects. A header pill on issues shows all active and completed agent sessions. Click any session to open a side panel with progress, logs, and steering. "Show agent sessions" is enabled by default in projects, and you can open a session straight from a project card without leaving the board. [Changelog](https://github.blog/changelog/2026-04-23-view-and-manage-agent-sessions-from-issues-and-projects).

## Model selection for Claude and Codex agents on github.com

**April 14.** When you start a Claude or Codex third-party agent session on github.com, you can now pick the specific model. Claude options today: Sonnet 4.6, Opus 4.6, Sonnet 4.5, Opus 4.5. Codex options: GPT-5.2-Codex, GPT-5.3-Codex, GPT-5.4. Access is included with Copilot subscriptions; Business and Enterprise admins enable the relevant Anthropic or Codex policy. [Changelog](https://github.blog/changelog/2026-04-14-model-selection-for-claude-and-codex-agents-on-github-com).

## JetBrains gets inline agent mode

`PREVIEW`, **April 24.** Inline agent mode landed in preview for JetBrains IDEs alongside other improvements. If you've been holding back a JetBrains rollout because of feature parity with VS Code, this is worth another look. [Changelog](https://github.blog/changelog/2026-04-24-inline-agent-mode-in-preview-and-more-in-github-copilot-for-jetbrains-ides).

## VS Code 1.118 (April 29): agent improvements and token efficiency

This release leans into two themes.

**Agent experience.** The VS Code Agents app for Insiders adds a Claude agent option, a web client at `insiders.vscode.dev/agents` over Dev Tunnel, and one-click switching to and from VS Code Insiders. Copilot is now added as a Git co-author by default on commits it changes. Semantic indexing of non-GitHub repositories rolled out to all users. A new `githubTextSearch` agent tool runs grep-style searches across a GitHub repo or an entire org.

**Token efficiency.** This is a direct response to the June 1 billing change. Prompt caching now reuses 93%+ of each request from cache. The new tool search tool defers most tools and loads them on demand for up to 20% token savings (default for Anthropic, opt-in for GPT-5.4 and GPT-5.5 via the `github.copilot.chat.responsesApi.toolSearchTool.enabled` setting). WebSocket mode for OpenAI models cuts latency by about 12%. There's also a new `ChatApprovedAccountOrganizations` enterprise device policy that gates AI feature activation on approved GitHub org membership.

[Full release notes](https://code.visualstudio.com/updates/).

## Other Copilot updates worth knowing

- **Cloud agent commits are signed**, so you'll see verified signatures in Git history. ([April 3](https://github.blog/changelog/2026-04-03-copilot-cloud-agent-signs-its-commits))
- **Org-level controls for cloud agent**: configure runner labels, sizes, and groups ([April 3](https://github.blog/changelog/2026-04-03-organization-runner-controls-for-copilot-cloud-agent)); set firewall allowed and blocked outbound hosts ([April 3](https://github.blog/changelog/2026-04-03-organization-firewall-settings-for-copilot-cloud-agent)); enable cloud agent at scale via repository custom properties ([April 15](https://github.blog/changelog/2026-04-15-enable-copilot-cloud-agent-via-custom-properties)).
- **Cloud agent runs faster**: 20% faster validation tools ([April 10](https://github.blog/changelog/2026-04-10-copilot-cloud-agents-validation-tools-are-now-20-faster)) and 20% faster startup with Actions custom images ([April 27](https://github.blog/changelog/2026-04-27-copilot-cloud-agent-starts-20-faster-with-actions-custom-images)).
- **Three-click merge conflict resolution** with cloud agent. ([April 13](https://github.blog/changelog/2026-04-13-fix-merge-conflicts-in-three-clicks-with-copilot-cloud-agent))
- **Copilot CLI**: auto model selection ([April 17](https://github.blog/changelog/2026-04-17-github-copilot-cli-now-supports-copilot-auto-model-selection)); custom registry MCP allowlists ([April 16](https://github.blog/changelog/2026-04-16-copilot-cli-supports-custom-registry-based-mcp-allowlists)); manage agent skills with `gh` CLI ([April 16](https://github.blog/changelog/2026-04-16-manage-agent-skills-with-github-cli)); C++ code intelligence in preview ([April 22](https://github.blog/changelog/2026-04-22-c-code-intelligence-for-github-copilot-cli-in-public-preview)).
- **Copilot Chat**: improved PR experience ([April 23](https://github.blog/changelog/2026-04-23-copilot-chat-improvements-for-pull-requests)); better debugging on the web ([April 23](https://github.blog/changelog/2026-04-23-better-debugging-with-github-copilot-on-the-web)).
- **Usage metrics keep maturing**: cloud agent active users, code review active vs passive users, Copilot CLI per-user activity, and merge metrics for Copilot-reviewed PRs are all now first-class fields in the report and API. Heads up that report download URLs are changing soon. ([April 22 notice](https://github.blog/changelog/2026-04-22-upcoming-change-to-copilot-usage-metrics-report-download-urls))
- **Deprecation**: GPT-5.1, 5.1 Codex, Codex-Max, and Codex-Mini have been removed from the model picker. If your team has any pinned configurations, swap them out. ([April 3](https://github.blog/changelog/2026-04-03-gpt-5-1-codex-gpt-5-1-codex-max-and-gpt-5-1-codex-mini-deprecated))

# 🛡️ Security & Compliance

## Code Security risk assessment is `GA` for organizations

**April 8.** Org admins and security managers can now run a free Code Security risk assessment that reviews vulnerabilities across the org. The report summarizes findings by severity, rule type, and programming language. It includes remediation guidance and highlights where Copilot Autofix can suggest fixes automatically. The point: identify the high-impact repos to prioritize and get a clean baseline. Run it from your org's Security tab, then Assessments. Available on GitHub Enterprise Cloud and GitHub Team today, ships in GHES 3.22. [Changelog](https://github.blog/changelog/2026-04-08-code-security-risk-assessment-available-for-organizations) and the [docs](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/code-scanning/code-security-risk-assessment).

## Dependabot alerts are now assignable to AI agents for remediation

`GA`, **April 7.** Some dependency vulnerabilities need more than a version bump. From the Dependabot alert detail page, you can now select **Assign to Agent** and pick Copilot, Claude, or Codex. The agent analyzes the alert and your repo's usage of the dependency, opens a draft PR with a proposed fix, and tries to resolve any test failures the update introduces. You can assign multiple agents to the same alert in parallel and compare their PRs. Useful for breaking-change major version upgrades, package downgrades when a version is compromised, and complex updates that fall outside Dependabot's rules engine. Requires GitHub Code Security and a Copilot plan with coding agent access. [Changelog](https://github.blog/changelog/2026-04-07-dependabot-alerts-are-now-assignable-to-ai-agents-for-remediation).

## OIDC support for Dependabot and code scanning

`GA` on github.com, **April 14.** Org admins can configure OIDC-based credentials for private registries instead of storing long-lived secrets in repo configs. It's the same federated trust model that GitHub Actions workflows already use. Supported registries at launch: AWS CodeArtifact, Azure DevOps Artifacts, JFrog Artifactory. Cloudsmith and Google Artifact Registry land within four weeks. Ships in GHES 3.22. [Changelog](https://github.blog/changelog/2026-04-14-oidc-support-for-dependabot-and-code-scanning).

## Link code scanning alerts to GitHub Issues

`PREVIEW`, **April 14.** Pull security remediation into your existing planning workflow. Connect alerts to GitHub Issues from either side, see tracking icons in alert lists, and filter by `has:tracking` or `no:tracking`. Available on github.com and on GitHub Enterprise Cloud with data residency. [Changelog](https://github.blog/changelog/2026-04-14-link-code-scanning-alerts-to-github-issues).

## Deployment context in repository properties and alerts

**April 14.** Code scanning alerts now show which environments a vulnerable code path is deployed to (production, staging) for much faster triage. [Changelog](https://github.blog/changelog/2026-04-14-deployment-context-in-repository-properties-and-alerts).

## More security improvements

- **Org-level private registries** for both Dependabot and code scanning. Configure once, instead of per-repo. ([April 14](https://github.blog/changelog/2026-04-14-dependabot-and-code-scanning-org-level-private-registries))
- **Runtime context from Dynatrace** can prioritize alerts by whether the vulnerable code path actually runs in production. ([April 7](https://github.blog/changelog/2026-04-07-prioritize-security-alerts-with-runtime-context-from-dynatrace))
- **Batch apply Copilot Autofix suggestions on PRs** instead of clicking through one-by-one. ([April 7](https://github.blog/changelog/2026-04-07-code-scanning-batch-apply-security-alert-suggestions-on-pull-requests))
- **Ask Copilot in security assessments** is embedded in the Code Security risk assessment view for direct Q&A on findings. ([April 9](https://github.blog/changelog/2026-04-09-ask-copilot-in-security-assessments-now-available))
- **Secret scanning**: pattern updates and product improvements ([April 14](https://github.blog/changelog/2026-04-14-secret-scanning-pattern-updates-and-product-improvements)); alert API, webhook, and delegated bypass workflow improvements ([April 8](https://github.blog/changelog/2026-04-08-secret-scanning-improvements-to-alert-apis-webhooks-and-delegated-workflows)).
- **CodeQL**: 2.25.2 adds Kotlin 2.3.20 support ([April 15](https://github.blog/changelog/2026-04-15-codeql-2-25-2-adds-kotlin-2-3-20-support-and-other-updates)); models-as-data now supports sanitizers and validators ([April 21](https://github.blog/changelog/2026-04-21-codeql-now-supports-sanitizers-and-validators-in-models-as-data)).
- **SBOM exports** are now computed asynchronously, so large repo exports stop timing out. ([April 14](https://github.blog/changelog/2026-04-14-sbom-exports-are-now-computed-asynchronously))
- **Dependabot**: Python dependency graphs are now Dependabot-based ([April 23](https://github.blog/changelog/2026-04-23-dependabot-graphs-for-python)); Nix ecosystem is now supported for version updates ([April 7](https://github.blog/changelog/2026-04-07-dependabot-version-updates-now-support-the-nix-ecosystem)).
- **Repository "Security" tab is now "Security & quality"** to reflect the Code Quality preview integration. ([April 2](https://github.blog/changelog/2026-04-02-the-security-tab-is-now-security-quality))
- **Heads up, SHA-1 sunset on HTTPS**. Very old HTTPS clients or proxies should be checked for compatibility. ([April 20](https://github.blog/changelog/2026-04-20-sunsetting-sha-1-in-https-on-github))
- **API deprecation**: several security-related organization API fields are being deprecated. If you automate with the Org REST/GraphQL APIs, give them a review. ([April 21](https://github.blog/changelog/2026-04-21-deprecation-of-security-related-organization-api-fields))

## GHES 3.20.1 is out (April 21)

This is a serious patch release. Multiple HIGH-severity CVE fixes including:

- A token scope fallback that could let revoked GitHub App `ghu_` tokens reach private repos (CVE-2026-5845).
- A notebook viewer SSRF plus timing side channel that could leak environment variables (CVE-2026-5921).
- A Management Console shell injection that allowed RCE as the admin OS user (CVE-2026-4821).
- An OAuth callback URL bypass (CVE-2026-4296).
- An `enable_auto_merge` auth bypass on branches without protection rules (CVE-2026-1999).

The instance also stops advertising `ssh-rsa` (SHA-1) signatures on ports 22 and 122, so clients should support `rsa-sha2-256` or `rsa-sha2-512`. If you run GHES 3.20.x, prioritize this upgrade. [Release notes](https://docs.github.com/en/enterprise-server/admin/release-notes).

# 🛠️ Platform & DevEx

## Improved search for GitHub Issues is `GA`

**April 2.** The faster, more accurate Issues search experience is now available across github.com. [Changelog](https://github.blog/changelog/2026-04-02-improved-search-for-github-issues-is-now-generally-available).

## Global pull requests dashboard moves to opt-out public preview

**April 23.** The cross-repo PR dashboard moved from opt-in to opt-out, so it shows up by default. Useful single pane for engineering managers tracking team-wide PR flow. [Changelog](https://github.blog/changelog/2026-04-23-global-pull-requests-dashboard-moves-to-opt-out-public-preview).

## Rule insights dashboard and unified filter bar

**April 16.** Repository ruleset insights gets a new dashboard and unified filtering. Easier to spot policy violations and bypass patterns at a glance. [Changelog](https://github.blog/changelog/2026-04-16-rule-insights-dashboard-and-unified-filter-bar).

## More platform updates

- **Disable commit comments across your organization** is a new org-level governance setting. ([April 23](https://github.blog/changelog/2026-04-23-disable-commit-comments-across-your-organization))
- **GitHub Mobile**: refreshed Copilot tab and native session logs ([April 1](https://github.blog/changelog/2026-04-01-github-mobile-stay-in-flow-with-a-refreshed-copilot-tab-and-native-session-logs)); faster, more flexible agent assignment from issues ([April 1](https://github.blog/changelog/2026-04-01-github-mobile-faster-more-flexible-agent-assignment-from-issues)); research and code with cloud agent anywhere ([April 8](https://github.blog/changelog/2026-04-08-github-mobile-research-and-code-with-copilot-cloud-agent-anywhere)).
- **Issues and Projects**: release info in issue sidebar and default values for project fields ([April 9](https://github.blog/changelog/2026-04-09-release-info-in-issue-sidebar-and-project-defaults)); repo member role labels in PR list view ([April 9](https://github.blog/changelog/2026-04-09-repository-member-role-labels-now-in-pull-request-list-view)).
- **Notifications** has a new Sort by control. ([April 9](https://github.blog/changelog/2026-04-09-new-sort-by-control-added-to-notifications))
- **GitHub Actions**: early-April updates bundle ([April 2](https://github.blog/changelog/2026-04-02-github-actions-early-april-2026-updates)); workflows are now capped at **50 reruns per run**, so check any high-rerun automation ([April 10](https://github.blog/changelog/2026-04-10-actions-workflows-are-limited-to-50-reruns)); a new format for GitHub App installation tokens (`ghs_`) is coming, so review any token validators ([April 24](https://github.blog/changelog/2026-04-24-notice-about-upcoming-new-format-for-github-app-installation-tokens)); npm trusted publishing now supports CircleCI ([April 6](https://github.blog/changelog/2026-04-06-npm-trusted-publishing-now-supports-circleci)).
- **GitHub CLI**: opt-out usage telemetry ([April 22](https://github.blog/changelog/2026-04-22-github-cli-opt-out-usage-telemetry)) and a new PGP signing key for Linux packages ([April 8](https://github.blog/changelog/2026-04-08-new-pgp-signing-key-for-github-cli-linux-packages)).
- **GitHub Copilot for Jira**: latest enhancements. ([April 22](https://github.blog/changelog/2026-04-22-github-copilot-for-jira-our-latest-enhancements))
- **Visual Studio**: monthly Copilot in Visual Studio update for March 2026. ([April 2](https://github.blog/changelog/2026-04-02-github-copilot-in-visual-studio-march-update))

# 🏢 Enterprise Administration

## Codespaces is `GA` for GitHub Enterprise Cloud with data residency

**April 1.** Codespaces is now generally available on GitHub Enterprise Cloud with data residency, with full feature parity. Available regions: Australia, EU, Japan, US. To maintain strict data residency, enterprise- or org-owned codespaces are required (user-owned codespaces aren't supported in this configuration). [Changelog](https://github.blog/changelog/2026-04-01-codespaces-is-now-generally-available-for-github-enterprise-with-data-residency), [Codespaces docs](https://docs.github.com/codespaces), and [data residency docs](https://docs.github.com/enterprise-cloud@latest/admin/data-residency/about-github-enterprise-cloud-with-data-residency).

## Heads up: Copilot moves to usage-based billing on June 1, 2026

`ANNOUNCEMENT`, **April 27.** This is the one to share with your billing managers and engineering leads. GitHub announced that Copilot is moving to usage-based billing on **June 1, 2026**. As part of that, **Copilot code review will start consuming GitHub Actions minutes** the same day. Two billing dimensions for each code review on private repos:

1. All Copilot usage (including code reviews) is billed as **AI Credits** under the new model.
2. **GitHub Actions minutes** will be consumed from your existing plan entitlement for each review. Usage beyond included minutes is billed at standard Actions rates.

Public repos remain free. This applies to all paid Copilot plans (Business and Enterprise included).

What we'd recommend doing in the next four weeks:

- Pull your current Actions usage and entitlements from billing settings.
- Set or confirm Actions budgets at org or enterprise level.
- Monitor Copilot and Actions metrics together so spikes don't surprise anyone.
- Loop your billing administrators and engineering leads in early.

If you already have GitHub-hosted runners enabled, no additional setup is required. [Full announcement](https://github.blog/changelog/2026-04-27-github-copilot-code-review-will-start-consuming-github-actions-minutes-on-june-1-2026).

## New self-serve signups for Copilot Business are paused

**April 22.** GitHub paused new self-serve signups for the Business plan. Existing Business customers aren't affected. For new Copilot rollouts, this confirms Enterprise as the strategic path going forward. If you've been weighing the two, that's a useful signal. [Changelog](https://github.blog/changelog/2026-04-22-pausing-new-self-serve-signups-for-github-copilot-business).

# 📅 Events & Training (May–June 2026)

## Microsoft Build 2026 (May 19–22)

Microsoft's flagship developer conference, free livestream plus in-person Seattle. Expect the biggest Copilot, agents, GitHub, and Azure announcements of the quarter. If your team is planning roadmap work for the second half of the year, this is the one to block calendars for. [Register and learn more](https://aka.ms/MSBuild_FY26_BN_Reactor_Reg).

## Before You Build: A Microsoft Build Preview (May 12, 8:00 AM PT)

A short orientation session with DevRel and GitHub voices on the biggest Build themes, must-watch sessions, and how to plan your Build experience. Worth an hour for anyone trying to figure out what to actually focus on across four days of content. [Register](https://developer.microsoft.com/en-us/reactor/events/27028/).

## GitHub Agentic Workflows: Automation That Actually Reads the Room (May 7, 9:00 AM PT)

Live demo: a markdown file plus one command launches an AI agent on GitHub Actions to triage issues, fix CI failures, update docs, and improve tests. From minimal workflow file to a sandboxed pipeline that delivers a ready-to-review PR. Worth an hour for any platform engineering lead. [Register](https://developer.microsoft.com/en-us/reactor/events/26943/).

## GitHub: From Workflows to Orchestration (Series, kicks off May 7)

Two-part hands-on series going deep on GitHub's agentic features, from workflows that automate your repo to orchestrated agents that think, plan, and execute like a team. [Register](https://developer.microsoft.com/en-us/reactor/series/S-1659/).

## Building an AI Agent Platform in .NET 10 with GitHub Copilot (Series, kicks off May 6)

Four-session hands-on series building a production-grade AI agent platform from scratch, using GitHub Copilot as your coding partner. .NET 10 plus Blazor and Aspire, with optional Azure OpenAI / Foundry integration. [Register](https://developer.microsoft.com/en-us/reactor/series/S-1652/).

## Agent Academy Live (May 12, 8:00 AM–3:00 PM PT)

One-day virtual conference on agent patterns, governance, ALM and compliance, MCP and Agent 365 integration, and multi-agent systems for real business scenarios. Includes a hackathon kickoff. Good for builders and architects who've prototyped an agent and need a path to production. [Register](https://developer.microsoft.com/en-us/reactor/events/27042/).

# Wrapping up

That's the roundup for April. The headline is that Copilot is finally enterprise-ready in the ways a lot of you have been asking about: data residency, FedRAMP, org-wide instructions, BYOK, an SDK, and an agent that can plan and research, not just open PRs. The other headline is June 1, when usage-based billing kicks in and Copilot code review starts pulling Actions minutes. There's a real opportunity over the next few weeks to look at your numbers, set budgets, and make sure the change isn't a surprise.

If you want to talk through any of these, especially data residency, the new billing model, or what a cloud agent rollout could look like for your team, just let me know and we'll grab time. Happy to jump on a call.

Talk soon,
James
