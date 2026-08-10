# Changelog

All notable changes to RevampKey will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [2.1.0] - 2026-08-10

### Added
- **Live plan usage is now visible and updates after each completed request** — see how much of your plan capacity you have used, including public-rate plans.
- **Earlier summary records can be opened to recover conversation context** — find the details you need when returning to long-running work.
- **Notebook edits now show a structured preview before changes are applied** — review source changes and cleared outputs before opening the notebook.
- **Notebook and individual cell contents now appear directly in chat** — inspect notebook results without leaving the conversation.
- **The Agent navigation rail can be resized** — give active work more room while keeping the workspace comfortable to scan.
- **MCP-aware workflows now explain configured-but-disabled servers and available connector options** — understand what needs credentials or activation before continuing.
- **Code subagents can safely inspect shell and runtime behavior** — investigate projects that need more than static file discovery.
- **MCP operations now use scoped delegation, provider-specific guidance, and current tool schemas** — work with connected services more reliably.

### Changed
- **Related tool activity and recovered conversation history are grouped more clearly** — compact reports and replies are easier to scan.
- **Approval and prompt cards now wait for your explicit choice** — they no longer select a default after a timeout.
- **Conversation compaction preserves more of your work across restarts and checkpoint reverts** — user decisions, complete turns, reasoning, tool results, tracker context, revisions, and subagent edits remain recoverable.
- **Search and environment discovery cover more workspace paths, project types, and local tools** — repository investigation is broader while remaining bounded.
- **Git workflows preserve structured targets and ranges, support bounded retries, and keep oversized terminal output recoverable** — important context is less likely to be lost during operations.
- **Delegated research now carries the current request, reuses reports already available, and limits automatic handoffs to the active reflection** — follow-up work stays focused and avoids unnecessary repetition.
- **Planning and delegated work stay aligned with the current project state** — tracker and specification context remains authoritative as work progresses.
- **Billing and request metadata remain available through completion and persistence** — usage-related responses continue to carry the information needed by the app.
- **MCP operation reports are easier to find after delegated work completes** — they are grouped with other operations instead of being misplaced.

### Fixed
- **Failed requests, prompt errors, and unexpected disconnects now remain visibly interrupted and retryable** instead of appearing complete.
- **Plan and tracker updates now route to the root plan correctly after a cold start or child task session**.
- **The Revamp AI layout-control icon is available again in Editor mode**, while maximized auxiliary views hide redundant layout actions.
- **Stale subagent calls from ended sessions are marked abandoned** instead of remaining indefinitely pending.
- **Failed streamed tool calls are no longer dispatched as if they were valid**, and interrupted operations report an unknown outcome instead of a misleading failure or success.
- **Prompt construction and caching no longer hit the identified crash paths**.
- **Completed sibling tool results are retained when another tool in the same batch is slow**.
- **Conversation summaries and checkpoint reverts no longer silently lose content, surviving segments, user decisions, or subagent edits**.
- **Search-and-replace accepts unambiguous partial-line matches and explains the actual mismatch when a replacement cannot be applied**.
- **Stopped subagents retain useful work and handoff context** instead of collapsing to a single interruption notice.
- **Attachments remain scoped to the message that supplied them** instead of leaking into later work.
- **Public-rate billing rejections now explain the server-provided reason and avoid futile retries**.
- **Large repository maps avoid dependency trees and remain bounded on unusually large workspaces**.

## [2.0.1] - 2026-07-31

### Added
- **Artifact search and retrieval results now appear directly in chat** — inspect past work and supporting evidence without leaving the conversation.
- **Past Work Reports settings give you control over artifact search** — choose whether the main agent and subagents search the current conversation, specifications, workspace, or all available reports.
- **Codebase structure sharing can now be configured independently** — keep the context available to the main agent and subagents aligned with the way you work.

### Changed
- **Long-running AI work is easier to resume** — interrupted subagent work retains more of its context and can continue after a restart instead of requiring a fresh run.
- **Research context is easier to carry forward** — earlier reports, repository identity, attachments, and follow-up context remain available when later work builds on them.
- **Queued follow-ups now preserve the original request while applying consistent safety checks** — the message you entered remains the message the assistant processes.
- **Agent navigation spacing is more consistent** — the workspace rail is easier to scan while moving between active work.

### Fixed
- **Queued follow-ups no longer enter the active run too early** — they wait for the correct handoff point before being processed.
- **Queued messages now replay consistently after a restart** — exact model-facing content is preserved instead of being regenerated differently.
- **Inline follow-ups resume with the correct conversation context** — continuing work no longer loses the connector-owned handoff state.
- **Artifact search and retrieval results render safely and clearly** — tool responses no longer show redundant metadata or fail to display usable results.
- **Main-agent and subagent context stays separated correctly** — codebase structure and artifact scope no longer leak across agent boundaries.
- **Attachments and summaries preserve the right order and context** — longer multi-step work is less likely to lose evidence or continue from stale state.

## [2.0.0] - 2026-07-22

### Added
- **A new agent-first workspace makes active work easier to follow** — projects, conversations, and tasks are organized in a dedicated navigation rail with nested conversations, processing indicators, timestamps, and quick new-task actions.
- **Plans now have a dedicated workspace** — review modules, live file changes, and specifications in separate tabs, open changed files in the editor, and resize or collapse the plan pane to fit your workflow.
- **Settings now have a redesigned home** — Account, Usage & Plan, Models, Code Structure, Git Workflow, and MCP Servers are organized in a clearer, responsive layout.
- **The workspace now remembers more of your layout** — expanded projects and the last active conversation are restored when you return.

### Changed
- **Agent and Editor mode feel more consistent** — the composer, landing screen, navigation, and surrounding controls now share the same polished visual language.
- **The new workspace is optimized for focused AI work** — wide layouts use a calmer hero/composer experience, clearer context controls, and less distracting chrome.
- **Tool activity is easier to scan** — low-attention tool calls are grouped into concise summaries, while important file changes and results remain easy to expand.
- **The default dark theme has a refreshed Graphite and Violet palette** — navigation, cards, controls, and focus states have clearer hierarchy and contrast.

### Fixed
- **Changed files and diffs are more reliable** — staged, unstaged, untracked, empty, and large diff states now open and display with the correct scope.
- **Plan-pane navigation is more dependable** — selecting a tool result or changed file opens the right destination, including falling back to the editor when no plan view is available.
- **Sidebar and plan-pane interactions work consistently across layouts** — project rows, conversation selections, collapsed pane tabs, and wide-mode clicks now respond as expected.
- **The chat workspace no longer reloads unnecessarily on startup** — cold starts avoid duplicate initialization and preserve the active context more reliably.
- **Composer states and uploaded images render correctly** — working indicators, image thumbnails, focus borders, and spacing no longer get stuck or drift between modes.

## [1.5.5] - 2026-07-16

### Added
- **Background AI work is now visible in your conversation list** — active conversations show a live indicator even when you are viewing another conversation.
- **Multi-repository workspaces now provide repository-level Git status** — RevampKey can distinguish the status of each repository instead of treating the workspace as one undifferentiated folder.
- **Searches can include or exclude hidden and gitignored files independently** — file discovery gives you more control while preserving which results come from ignored files.

### Changed
- **AI responses are easier to read** — source lookup markers, file paths, and line-range tags are no longer shown in chat, while the referenced code and formatting remain intact.
- **Progress indicators now reflect live activity** — progress and stop-button animations appear only while the assistant is actively processing.
- **Model changes now create a clean conversation boundary** — switching models during a conversation preserves the conversation state more reliably, and notices use the model’s display name.
- **Workspace context is carried through more reliably** — AI requests retain the relevant workspace folders, repository scope, Git context, and shared prompt context across multi-root workspaces and recursive planning.
- **Terminal results can include more output** — longer command output is available before it is truncated.
- **Conversation summarization is more reliable** — summaries avoid repeated processing, preserve workspace scope, and retain memory across the appropriate project context.
- **Large-context subagent work is more resilient** — oversized requests are handled more safely instead of failing because the input is too large.
- **The desktop layout is easier to navigate** — persistent sidebar controls now appear in the title bar, title-bar spacing is improved across platforms, and default sidebar widths adapt better to the window size.
- **New launches go directly to the workspace** — the startup editor is disabled by default.
- **Dark mode has clearer controls and hierarchy** — checkbox borders are visible and sidebar titles use a quieter contrast.

### Fixed
- **Extension browsing is available again** — the built-in extension marketplace configuration has been restored.
- **Explicit auxiliary-sidebar visibility settings are now respected** — RevampKey no longer overrides a user’s chosen visibility.
- **Workspace storage and conversation checkpoints now use the correct location** — AI operations are less likely to lose the workspace context needed to restore or continue work.

## [1.5.4] - 2026-07-09

### Added
- **Queued messages now show clearly while the assistant is busy** — sending a message while the assistant is still replying shows it as queued and picks it up automatically once its turn starts.
- **Multi-step assistant responses are now saved as individual steps** — so your conversation history accurately reflects each action taken, instead of merging everything into one message.

### Changed
- **Follow-up messages are picked up sooner** — a message sent during an active response is now picked up as soon as the assistant reaches a natural pause, instead of waiting for the entire response to finish.

### Fixed
- **Queued messages no longer look stuck or out of order** — fixed queued messages sometimes appearing out of order, showing a stuck highlight, or losing their status indicator once picked up.
- **Fixed a rare conversation-corrupting race condition** — sending a new message while the assistant was still replying could occasionally corrupt or crash the conversation; this no longer happens.
- **AI sessions start up more reliably** — fixed slow or failed AI session startup when GitHub was unreachable.
- **Clearer error when a firewall or VPN blocks the connection** — SSL/TLS connectivity failures now show a plain Retry/Cancel dialog instead of failing silently after a long retry delay.
- **Clearer error on full network loss** — when your connection drops completely, RevampKey now shows a Retry/Cancel dialog instead of appearing to hang.
- **Friendlier error when the AI provider has an outage** — a mid-response provider failure now shows a plain-language message instead of a raw error, and the conversation stays usable.
- **Fixed new conversations failing on the very first message** — an unavailable model no longer gets auto-selected behind the scenes, which was blocking some fresh workspaces from sending their first message.
- **Fixed the assistant losing context partway through multi-step actions** — tool results and reasoning no longer get dropped between steps of a longer task.
- **Fixed an unexpected sign-in browser window appearing when using OpenRouter** — the packaged app no longer tries to open an interactive OAuth flow it can't complete.

## [1.5.3] - 2026-07-01

### Added
- **You can now mention files directly in chat** — type to search your workspace and attach files as context, with recently used files surfacing first.

### Changed
- **File mention and attachment chips look cleaner** — the picker and chip layout have been refined for a more polished feel.

### Fixed
- **Model selection and attachments now survive sidebar toggling** — switching the sidebar in and out no longer resets your chosen model or in-progress attachments.
- **Image attachments stay stable when maximizing or minimizing the window** — thumbnails no longer resize incorrectly during window state changes.
- **Fullscreen/maximized view is restored correctly after toggling window mode** — returning from a mode switch keeps you on the tab you were viewing.
- **Model changes now reach active conversations reliably** — switching models mid-conversation no longer leaves a stale model applied to ongoing requests.

## [1.5.2-beta] - 2026-06-29

### Changed
- **Model selection now stays aligned more consistently across RevampKey** — Auto and Manual mode behavior now follows the same active setting across the app, runtime-backed requests, and follow-up AI work.

### Fixed
- **Manual model selection no longer loses state while responses are in progress** — the toolbar selector now stays stable instead of dropping or resetting your choice during active processing.
- **Workspace model preferences now persist more reliably between sessions** — RevampKey is less likely to drift back to stale model settings after reopening a workspace.
- **Windows releases now include the expected RevampKey app icons** — installers and shortcuts now show the branded icon set more consistently across supported sizes.
- **AI configuration updates now reach the bridge more reliably** — background configuration messages are less likely to fail while RevampKey is syncing AI settings.

## [1.5.1-beta] - 2026-06-28

### Changed
- **RevampKey Icons are now the default product icon theme** — the editor now uses the updated RevampKey icon set by default, making product branding more consistent across the interface.
- **RevampKey branding assets have been refreshed** — updated logo and icon assets give the app a cleaner and more consistent branded look.

### Fixed
- **AI bridge startup is more reliable** — the bridge now uses a standardized ready signal and a longer startup timeout, reducing failed launches during startup.
- **Built-in registration no longer uses the wrong marketplace-style flow** — bundled product integrations now register using the correct built-in behavior instead of an incorrect marketplace-style path.

## [1.5.0-beta] - 2026-06-27

### Changed
- **A new titlebar mode toggle is now built into the custom titlebar** — you can switch modes directly from the editor chrome without leaving your current workspace.
- **Dark mode looks more polished and consistent** — the refreshed dark theme colors improve the app’s overall visual clarity.
- **RevampKey sign-in is now integrated into the app** — authentication flows are more seamless and feel more native inside the editor.

### Fixed
- **AI bridge startup is more resilient** — RevampKey now falls back to a free local port automatically if the preferred port is already in use.
- **Sign-in and session recovery are more reliable** — callback handling, token refresh, and profile updates are less likely to stall or get lost during authentication.
- **Error reporting is more dependable when something goes wrong** — sidebar diagnostics and console failures are captured more consistently, helping problems surface sooner instead of failing silently.

## [1.4.1-beta] - 2026-06-25

### Fixed
- **Model dropdown deadlock is gone** — The chat toolbar model selector no longer freezes when opened.
- **AI bridge startup is more resilient** — RevampKey now falls back to any free local port if the preferred AI bridge port is already in use.
- **Orphan dialog cards now render consistently** — Conversations now show a placeholder AI message when a dialog card arrives without its original assistant message, so the chat no longer appears blank or broken.

## [1.4.0] - 2026-06-23

### Changed
- **RevampAI now starts in Auto model mode by default for new installs** — New users start with backend-managed model selection automatically, while manual mode remains available whenever you want to take control.
- **Model controls are simpler and more compact** — The chat toolbar now includes a compact Auto/Manual switch, and settings focus on the primary model instead of exposing internal weak/architect selectors.

### Fixed
- **Auto/manual model selection now persists reliably across restart** — Choosing Auto no longer flips back to Manual after restarting RevampKey.
- **Backend-owned model defaults refresh more reliably for Auto mode** — Auto-routed requests now follow the backend’s latest main, weak, and architect model defaults without needing stale local selections.
- **Manual toolbar model dropdown is visible again** — The compact toolbar selector no longer gets clipped when opening the model menu.

## [1.3.1] - 2026-06-20

### Changed
- **Strengthened protection of RevampKey's underlying AI engine** — Hardened the app's internals to make them harder to extract or tamper with, with no change to how you use RevampKey.

## [1.3.0] - 2026-06-19

### Added
- **Required updates can now block outdated app versions** — When your installed build is no longer supported, RevampKey now shows a dedicated update prompt and guides you to install a newer version before continuing.

### Fixed
- **Required update notices now show the right minimum version** — Update prompts now display the supported version details correctly instead of leaving them blank.
- **Version checks now identify your installed RevampKey build more reliably** — Compatibility checks now use the app's actual release version consistently, so supported builds are recognized more accurately.

## [1.2.2] - 2026-06-19

### Changed
- **Chat prompts now start with clearer guidance** — The main prompt box now uses more helpful starter copy, making it easier to describe what you want RevampKey to do.
- **Tool approval cards are easier to understand** — Confirmation prompts now hide raw CLI plumbing and show cleaner action wording instead.

## [1.2.1] - 2026-06-17

### Changed
- **Figma help links open more smoothly during MCP setup** — RevampKey now recognizes Figma's help center as a trusted destination during protected link flows.

### Fixed
- **Always Allow now actually sticks for approval prompts** — Choosing Always Allow or Don't ask again now prevents repeated approval interruptions for the same action flow.
- **Model defaults stay in sync more reliably** — Model selection and fallback behavior now update more consistently instead of drifting back to stale defaults.

## [1.2.0] - 2026-06-17

### Added
- **Custom MCP server secrets are easier to configure** — You can now define secret environment variables for your own MCP servers and start from clearer setup examples.

### Changed
- **Figma connections work with more setups** — Design workflows now support Framelink-based MCP configurations more smoothly across platforms.
- **Slash-triggered command handling is more predictable** — Typing a slash now behaves like normal prompt input unless you actually intend to use a command.

### Fixed
- **Separate AI conversations no longer mix their state** — Planning activity, processing state, restored prompts, and interactive cards now stay with the conversation where they belong.
- **Reply threading is more stable during AI updates** — Assistant messages now preserve the correct IDs and stay attached more reliably during streaming and follow-up actions.

## [1.1.2] - 2026-06-15

### Added
- **New MCP connectors for Filesystem and PostgreSQL** — You can now connect to these services directly from RevampKey.
- **More reliable local connector startup** — Local connections now show clearer progress and stay responsive while they launch.
- **New browser, search, and productivity connectors** — Browser automation, web search, and additional workspace connectors are now available in the assistant.

### Changed
- **Connector setup and sign-in flows are more consistent** — Several integration flows now complete with clearer handoff and more dependable account linking.
- **Connector status is easier to follow** — The assistant now shows clearer activity and success feedback while connections are running.

### Fixed
- **Interrupted or pending connection flows recover more reliably** — Stopped or delayed actions now leave the assistant in a better state for retrying.
- **Tool and response rendering is more stable** — Chat output now stays readable more consistently in compact layouts and mixed-content responses.
- **OAuth and connector handoff issues are more reliable** — A number of connection and authorization flows now complete more consistently.

## [1.1.1] - 2026-06-13

### Added
- **Live request timing while AI is working** — The status area now shows elapsed time during each response, so long-running requests are easier to track.
- **Current subagent tool activity in collapsed view** — Even with a subagent card collapsed, you can now see which tool is actively running.

### Changed
- **Stopped prompts return to the input box** — If you interrupt a request, your prompt is restored so you can quickly edit and retry.
- **Diff output is clearer in narrow sidebars** — Multi-file and multi-hunk tool changes are grouped and rendered more cleanly in compact layouts.
- **Tool labels are more consistent across chat cards** — Tool actions now use clearer, unified naming throughout the chat UI.

### Fixed
- **Processing state and stop controls stay aligned** — Status indicators now track active processing more reliably while requests are running.
- **Mixed markdown and HTML responses render more reliably** — Structured responses now display correctly without breaking surrounding layout.
- **Compact chat layouts avoid overflow more consistently** — Long content now stays contained in narrow panels.

## [1.1.0] - 2026-06-11

### Added
- **Subagents are more aware of your machine and repository context** — Runtime-backed workflows now receive clearer platform details and git identity information during tool-driven tasks.

### Changed
- **Tool-heavy AI workflows are more environment-aware** — Runtime context now carries stronger platform and repository details, helping multi-step automation stay aligned with your active setup.

### Fixed
- **Reflected replies land more reliably in the intended conversation** — Follow-up responses after reflection now route more consistently.
- **Runtime-backed replies respect your language more consistently** — AI responses now adhere more reliably to the language you used.
- **Requests for extra information are better timed** — The assistant is clearer about when it genuinely needs more input before continuing.

## [1.0.1] - 2026-06-11

### Changed
- **Configurable child tool visibility** — Child tools can now be shown or hidden with a configuration option.
- **More consistent chat UI and reply handling** — Chat presentation and reply behavior have been tightened up for a steadier experience.

### Fixed
- **Reply routing is more reliable** — Replies now route to the intended thread more consistently.
- **Message ordering is more stable** — Chat messages now appear in a steadier, more predictable order.
- **External markdown links open correctly** — Links in markdown content now open as expected.
- **Sidebar streaming autoscroll is smoother** — Streaming updates in the sidebar now keep the view following along more naturally.
- **Narrow chat layouts avoid overflow** — Fixed overflow issues in compact chat layouts.

## [1.0.0] - 2026-05-19

### Added
- **Improved planning workflow visibility** — You can now follow active planning work in a dedicated sidebar while continuing the conversation.
- **More flexible chat layout** — The chat and planning areas now support a responsive two-panel experience for better use of screen space.
- **Built-in codebase context controls** — New settings make it easier to tune how codebase context is generated for AI responses.

### Changed
- **Settings are easier to understand** — Labels and descriptions were rewritten in plain language with a clearer configuration flow.
- **Large pasted content is easier to manage** — Big snippets now collapse into lightweight reference items so the composer stays readable.
- **Conversation and plan state restores more reliably** — Returning to RevampAI after hiding or showing the panel better preserves where you left off.
- **Release handoff is more reliable** — Finished planning work now leaves clearer save points, so completed progress is easier to keep and review.
- **Tool-heavy workflows are more dependable** — Subagent-driven work now keeps its steps in better order, making longer execution chains feel steadier.
- **Release checks are stricter** — Extra guardrails help catch out-of-date release states before publishing, reducing avoidable release mistakes.

### Fixed
- **Draft text is more reliable** — Fixed cases where in-progress draft content could be lost during UI transitions.
- **Planning controls appear correctly in narrow layouts** — Fixed visibility issues so tracker controls show as expected in compact panel sizes.
- **Runtime and packaging behavior is more stable** — Updated core integration and build flow for a smoother release experience.

## [0.4.0-beta] - 2026-04-24

### Added
- **New plan tracker sidebar for AI planning work** — You can now view and follow implementation modules/tasks in a dedicated panel while continuing the conversation.
- **More flexible RevampAI layout** — The chat and plan areas now support a responsive two-panel experience with a draggable sidebar for better use of screen space.
- **Built-in codebase structure controls in settings** — New options make it easier to tune how codebase-structure context is generated for AI responses.

### Changed
- **RevampAI settings are easier to understand and configure** — Labels and descriptions were rewritten in plain language, with clearer model naming and an improved settings flow.
- **Chat input is smoother for large content** — Large pasted snippets now collapse into lightweight reference pills so the composer stays readable.
- **Conversation and plan state now restores more reliably** — Returning to RevampAI after hiding/showing the panel better preserves where you left off.

### Fixed
- **Draft text in chat is more reliable** — Fixed cases where in-progress draft content could be lost during UI transitions.
- **Narrow layouts now surface planning controls correctly** — Fixed visibility issues so tracker controls appear as expected in compact panel sizes.
- **General runtime and packaging reliability improvements** — Updated core runtime integration and build/signing flow for a more stable release experience.

## [0.3.2-beta] - 2026-04-13

### Changed
- **Search is now more reliable when looking through code** — Improved fallback behavior reduces missed matches when an initial lookup path fails, so search results are more dependable during everyday work.
- **Search feels faster and more consistent** — File discovery and lookup-heavy workflows now return results with better responsiveness and steadier behavior.

### Fixed
- **Tool status is now shown correctly after recovery** — Fixed an issue where search-and-replace status details could appear incorrect after automatic recovery.

## [0.3.1-beta] - 2026-04-07

### Fixed
- **RevampAI sidebar now loads every time** — Fixed an issue where the RevampAI panel would show a blank screen or fail silently on roughly 2 out of 3 cold starts. It now loads correctly and consistently on every launch.
- **Model picker remembers your selection** — The AI model dropdown was occasionally resetting to the first available model (about 2 in 10 reloads) instead of showing the one you last selected. Your choice is now preserved reliably across sessions.

## [0.3.0-beta] - 2026-04-07

### Added
- **RevampKey Dark theme** — A new built-in dark theme with a refined charcoal palette is now included and set as the default dark theme. No extra installation needed; it applies automatically on first launch.
- **Open Folder shortcut in sidebar** — When RevampKey is launched without a workspace, the sidebar now shows a direct "Open Folder" button so you can get started without hunting through the menus.

### Changed
- **Faster sign-in experience** — The login screen now appears instantly on first install or after signing out, instead of sitting through a loading animation before being redirected.
- **AI model display auto-syncs** — The selected AI model name in the toolbar now correctly reflects your account's available models right away, without requiring a manual re-selection after sign-in.
- **Cleaner editor UI** — Removed third-party AI assistant icons and suggestions from the title bar, command center, status bar, and Help menu to keep the interface focused and uncluttered.
- **Smoother extension installs** — Extension installation no longer shows signature verification dialogs, resulting in a faster and less noisy install flow.

### Fixed
- **Sign-in retry now works correctly** — Dismissing the browser sign-in window and clicking "Sign In" again now reliably reopens the browser. Previously, cancelling could leave the login flow in a stuck state.
- **Cold start "Open a folder" prompt** — Fixed an issue where launching RevampKey with no workspace open would show "Initializing Revamp AI…" indefinitely instead of the expected "Open a folder to get started" prompt.


## [v0.2.3-beta] - 2026-04-06

### Added
- Expanded observability in the integrated RevampKey Runtime with analytics sampling controls, richer message/repo telemetry, and version-aware request metadata.
- Added public observability documentation coverage for Loki logging and PostHog event flow to improve operational clarity.

### Changed
- Updated integrated runtime from `revampkey-runtime-v0.1.19` to `revampkey-runtime-v0.1.23`.
- Improved runtime traceability and analytics identity handling with stronger user/context propagation and extension/runtime build metadata alignment.
- Advanced bridge-level and model-request observability context so diagnostics are more actionable across extension and runtime boundaries.

### Fixed
- Applied cumulative runtime fixes from `v0.1.20` to `v0.1.23`, including cross-platform compatibility hardening and repo-map crash prevention for empty graph scenarios.

### Security
- Continued local-first and privacy-focused defaults with telemetry/analytics disabled by default unless explicitly configured.

### Runtime Stability Note
- **RevampKey Runtime is the main engine behind RevampKey.**
- This release carries cumulative runtime hardening and observability maturation through `v0.1.20` to `v0.1.23`, improving reliability, debuggability, and release confidence.

## [v0.2.2-beta] - 2026-03-30

### Added
- Introduced a smoother checkpoint revert experience in RevampAI so users can confidently roll conversations back and continue from a cleaner state.
- Expanded release quality coverage with new automated checks around complex chat/stream flows.

### Changed
- Updated the integrated RevampKey Runtime to `v0.1.20`, bringing broad quality and reliability improvements to day-to-day AI-assisted workflows.
- Refined chat readability by replacing aggressive message truncation with better word wrapping in question cards.
- Improved release packaging flow to make distribution output more consistent across builds.

### Fixed
- Improved streaming and checkpoint handling stability in RevampAI to reduce interrupted responses during longer interactions.
- Resolved edge-case save/order issues around checkpoint operations for more predictable conversation state.

### Removed
- 

---

## [0.2.1-beta] - 2026-03-26

### Added
- RevampKey Runtime evolution summary integrated into the product changelog to improve transparency around core engine maturity.
- Runtime capabilities added since `revampkey-runtime-v0.1.3` include:
  - Turn-based conversation summarization and improved tool result management.
  - File memory management/status tracking and stronger context-handling workflows.
  - Safety checks and cleanup for orphaned/incomplete tool results before API submission.
  - RevampKey Model Info API integration with local caching, diagnostics, and environment metadata merge support.
  - Multi-conversation plan architecture with shared tracker/spec resources and restoration/self-healing flows.
  - Context-management, error-recovery, and design-document prompt systems for more resilient operation.
  - Prompt compression analysis/utilities and repo map regeneration documentation.

### Changed
- Updated integrated runtime from `revampkey-runtime-v0.1.3` to `revampkey-runtime-v0.1.17`.
- Runtime and engine-level improvements delivered across `v0.1.4` to `v0.1.17`:
  - Prompt, cache, and context optimization to reduce token usage and improve responsiveness.
  - Improved model/provider handling, metadata processing, and API settings behavior.
  - Repo map generation, timeout behavior, and cache handling refinements.
  - Dependency and compatibility updates (including tree-sitter/litellm-related updates).
  - Logging, storage, and conversation lifecycle refinements for better reliability and traceability.

### Fixed
- Core runtime fixes delivered across the upgraded range include:
  - Removal/cleanup of orphaned and incomplete tool-result sequences to prevent malformed message flows.
  - Cache-key and cache-control reliability issues affecting consistency/performance.
  - Model/provider routing and metadata edge cases.
  - Repo map and signature-related reliability issues.
  - Tracker patch update behavior improvements to preserve existing task/module titles during partial updates.

### Removed
- Runtime cleanup and maintenance in the upgraded range removed obsolete/unused references and outdated documentation where applicable to keep the engine lean and maintainable.

### Security
- Continued local-first and privacy-focused operation with telemetry/analytics disabled by default.

### Runtime Stability Note
- **RevampKey Runtime is the main engine behind RevampKey.**
- This release includes cumulative runtime hardening from `v0.1.4` through `v0.1.17`, with focused work on resiliency, context integrity, cache stability, and tracker correctness.

## [0.2.0-beta] - 2025-01-20

### Added
- Initial beta release of RevampKey
- AI-powered code refactoring capabilities
- Modern code editor based on Visual Studio Code (v1.108.0)
- Open VSX extension marketplace integration
- Privacy-first architecture - all processing on local machine
- Cross-platform support (Windows (Coming Soon), macOS, Linux)
- Automatic update system with GitHub releases integration
- Custom branding and user interface
- RevampAI auxiliary bar with enhanced UI/UX
- Linux package support: `.deb`, `.rpm`, `.tar.gz`
- macOS: Universal binary (Intel + Apple Silicon)
- Support for x64, ARM64, and ARMv7 architectures

### Changed
- Updated to VSCode upstream version 1.108.0
- Enhanced webview activation logic for RevampAI
- Improved build configuration for all platforms
- Updated license and copyright information
- Privacy-focused documentation and URLs

### Security
- Disabled telemetry by default
- Removed analytics and tracking
- Local-first data processing


## [0.1.0-beta] - 2025-01-19

### Added
- Initial beta release of RevampKey
- AI-powered code refactoring capabilities
- Modern code editor based on Visual Studio Code (v1.108.0)
- Open VSX extension marketplace integration
- Privacy-first architecture - all processing on local machine
- Cross-platform support (Windows, macOS, Linux)
- Automatic update system with GitHub releases integration
- Custom branding and user interface
- RevampAI auxiliary bar with enhanced UI/UX

### Changed
- Updated to VSCode upstream version 1.108.0
- Enhanced webview activation logic for RevampAI
- Improved build configuration for all platforms
- Updated license and copyright information
- Privacy-focused documentation and URLs

### Technical
- Linux package support: `.deb`, `.rpm`, `.tar.gz`
- Windows installers: x64 and ARM64
- macOS: Universal binary (Intel + Apple Silicon)
- Support for x64, ARM64, and ARMv7 architectures

### Security
- Disabled telemetry by default
- Removed analytics and tracking
- Local-first data processing

## Version History

### Beta Releases
- **0.3.1-beta** (2026-04-07) - Startup reliability and model picker fix release.
- **0.3.0-beta** (2026-04-07) - Dark theme, UI polish, and stability improvements.
- **v0.2.2-beta** (2026-03-30) - Streaming/checkpoint stability and runtime upgrade release.
- **0.2.1-beta** (2026-03-26) - Runtime maturity and reliability expansion release.
- **0.2.0-beta** (2025-01-20) - Initial feature-complete beta milestone.
- **0.1.0-beta** (2025-01-19) - Initial public beta release.

---

## How to Update

### Automatic Updates (Recommended)
RevampKey will notify you when updates are available:
1. Click the notification or go to **Help > Check for Updates**
2. Download and install the update
3. Restart RevampKey

### Manual Updates
1. Visit the [Releases page](https://github.com/revampai/revampkey/releases)
2. Download the latest version for your platform
3. Install following the platform-specific instructions

### Linux Package Managers
```bash
# Debian/Ubuntu
sudo apt update
sudo apt upgrade revampkey

# Fedora/RHEL
sudo dnf upgrade revampkey
```

---

## Reporting Issues

Found a bug or have a feature request? Please report it on our [GitHub Issues](https://github.com/revampai/revampkey/issues) page.

---

## Links
- **Website**: [revampkey.com](https://revampkey.com)
- **GitHub**: [github.com/revampai/revampkey](https://github.com/revampai/revampkey)
- **Releases**: [github.com/revampai/revampkey/releases](https://github.com/revampai/revampkey/releases)
