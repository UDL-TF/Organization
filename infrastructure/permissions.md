# Communication Channel Permissions

This document establishes a clear permission hierarchy for the organization-wide chat channels so every team member knows where to collaborate. Each channel targets a specific workflow slice while keeping management visibility consistent.

## Management Cohort

The "management" umbrella referenced throughout the channels includes the following roles:

- Owners
- Server Managers
- Community Managers
- Product Managers
- Ambassadors (community-facing leadership role)

> Ambassadors do not yet have a dedicated role page, but they participate in management discussions and should be granted the same channel access as the other management roles.

## Channel Directory

| Channel     | Primary Purpose                                                                                  |
| ----------- | ------------------------------------------------------------------------------------------------ |
| Management  | Strategic coordination space reserved for management cohort members.                             |
| Staff       | Day-to-day operational space that keeps staff aligned with management.                           |
| Developers  | Engineering hub for Developers that still gives management visibility.                           |
| Production  | Cross-functional room for shipping-ready work across Developers, Staff, Mappers, and Management. |
| Development | Iteration space for Developers and Mappers with management oversight.                            |

## Access Matrix

| Channel     | Owners | Staff | Developers | Community Managers | Product Managers | Server Managers | Mappers | Ambassadors |
| ----------- | ------ | ----- | ---------- | ------------------ | ---------------- | --------------- | ------- | ----------- |
| Management  | ✅     |       |            | ✅                 | ✅               | ✅              |         | ✅          |
| Staff       | ✅     | ✅    |            | ✅                 | ✅               | ✅              |         | ✅          |
| Developers  | ✅     |       | ✅         | ✅                 | ✅               | ✅              |         | ✅          |
| Production  | ✅     | ✅    | ✅         | ✅                 | ✅               | ✅              | ✅      | ✅          |
| Development | ✅     |       | ✅         | ✅                 | ✅               | ✅              | ✅      | ✅          |

✅ indicates that members of the role have access to the channel.

## Access Diagram

```mermaid
flowchart TB
	subgraph Roles
		direction TB
		OWN[Owners]
		STF[Staff]
		DEV[Developers]
		CM[Community Managers]
		PM[Product Managers]
		SM[Server Managers]
		MAP[Mappers]
		AMB[Ambassadors]
	end

	subgraph Channels
		direction TB
		CH_MAN[Management]
		CH_STF[Staff]
		CH_DEV[Developers]
		CH_PROD[Production]
		CH_DEVT[Development]
	end

	%% Management cohort visibility (Owners also covered below)
	CM ---> CH_MAN
	PM ---> CH_MAN
	SM ---> CH_MAN
	AMB ---> CH_MAN
	OWN ---> CH_MAN

	STF ---> CH_STF
	CM ---> CH_STF
	PM ---> CH_STF
	SM ---> CH_STF
	AMB ---> CH_STF
	OWN ---> CH_STF

	DEV ---> CH_DEV
	CM ---> CH_DEV
	PM ---> CH_DEV
	SM ---> CH_DEV
	AMB ---> CH_DEV
	OWN ---> CH_DEV

	STF ---> CH_PROD
	DEV ---> CH_PROD
	CM ---> CH_PROD
	PM ---> CH_PROD
	SM ---> CH_PROD
	MAP ---> CH_PROD
	AMB ---> CH_PROD
	OWN ---> CH_PROD

	DEV ---> CH_DEVT
	CM ---> CH_DEVT
	PM ---> CH_DEVT
	SM ---> CH_DEVT
	MAP ---> CH_DEVT
	AMB ---> CH_DEVT
	OWN ---> CH_DEVT

	classDef role fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#e0f2fe;
	classDef channel fill:#0b1120,stroke:#fcd34d,stroke-width:2px,color:#fffbeb;
	classDef cohort fill:#0f172a,stroke:#84cc16,stroke-width:2px,color:#ecfccb;
	class OWN,STF,DEV,MAP role;
	class CM,PM,SM,AMB cohort;
	class CH_MAN,CH_STF,CH_DEV,CH_PROD,CH_DEVT channel;

	%% Channel-colored connections for readability
	linkStyle 0 stroke:#f97316,stroke-width:2px;
	linkStyle 1 stroke:#f97316,stroke-width:2px;
	linkStyle 2 stroke:#f97316,stroke-width:2px;
	linkStyle 3 stroke:#f97316,stroke-width:2px;
	linkStyle 4 stroke:#f97316,stroke-width:2px;

	linkStyle 5 stroke:#a855f7,stroke-width:2px;
	linkStyle 6 stroke:#a855f7,stroke-width:2px;
	linkStyle 7 stroke:#a855f7,stroke-width:2px;
	linkStyle 8 stroke:#a855f7,stroke-width:2px;
	linkStyle 9 stroke:#a855f7,stroke-width:2px;
	linkStyle 10 stroke:#a855f7,stroke-width:2px;

	linkStyle 11 stroke:#0ea5e9,stroke-width:2px;
	linkStyle 12 stroke:#0ea5e9,stroke-width:2px;
	linkStyle 13 stroke:#0ea5e9,stroke-width:2px;
	linkStyle 14 stroke:#0ea5e9,stroke-width:2px;
	linkStyle 15 stroke:#0ea5e9,stroke-width:2px;
	linkStyle 16 stroke:#0ea5e9,stroke-width:2px;

	linkStyle 17 stroke:#22c55e,stroke-width:2px;
	linkStyle 18 stroke:#22c55e,stroke-width:2px;
	linkStyle 19 stroke:#22c55e,stroke-width:2px;
	linkStyle 20 stroke:#22c55e,stroke-width:2px;
	linkStyle 21 stroke:#22c55e,stroke-width:2px;
	linkStyle 22 stroke:#22c55e,stroke-width:2px;
	linkStyle 23 stroke:#22c55e,stroke-width:2px;
	linkStyle 24 stroke:#22c55e,stroke-width:2px;

	linkStyle 25 stroke:#e11d48,stroke-width:2px;
	linkStyle 26 stroke:#e11d48,stroke-width:2px;
	linkStyle 27 stroke:#e11d48,stroke-width:2px;
	linkStyle 28 stroke:#e11d48,stroke-width:2px;
	linkStyle 29 stroke:#e11d48,stroke-width:2px;
	linkStyle 30 stroke:#e11d48,stroke-width:2px;
	linkStyle 31 stroke:#e11d48,stroke-width:2px;
```

## Quick Reference Rules

1. Management visibility is guaranteed in every channel listed here.
2. Staff gain access to the Staff and Production channels, aligning them with daily operations and release readiness.
3. Developers collaborate in three rooms: their dedicated channel, Production, and Development.
4. Mappers join Production (for ship-ready work) and Development (for iterative work), ensuring they stay paired with Developers and Management.
5. Ambassadors mirror management access until a formal role document is added.
