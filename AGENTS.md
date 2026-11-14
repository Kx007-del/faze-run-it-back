# Ownership and integration rules

Only edit your assigned directory. Read shared/contracts.ts. Do not change shared contracts, dependencies, or another agent's files without asking the integration lead. Do not run Git mutations; the lead owns commits and publishing. Do not add secrets or external paid services.

- Gameplay agent: packages/gameplay/\*\*. Exports GameArena.tsx default React component with props config: ChallengeConfig, onComplete: (result: AttemptResult) => void, replay?: AttemptResult, onReplayEnd?: () => void. Own local styles.
- Challenge agent: packages/challenges/\*\*. Exports ChallengeBuilder.tsx default component props config: ChallengeConfig, onChange: (config: ChallengeConfig) => void, proven: boolean, locked?: boolean. Own local styles. No API calls or publication logic.
- Social agent: packages/social/\*\*. Exports registerApi(app: Express) from server.ts and fetch-based client.ts. Own persistence in ignored data/. Validate with shared contracts. No UI or gameplay changes.
- Integration lead: all other files, shared contracts, dependencies, server entry, app shell, brand assets, QA and GitHub.

Shared files are outside agent folders intentionally. Ask lead for contract changes. Record implementation notes and checks in your folder's HANDOFF.md. MVP is one original COD-inspired arena; no proprietary game models/maps, live multiplayer, arbitrary reconstruction, or paid services.
