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
	classDef role fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#e0f2fe;
	classDef cohort fill:#0f172a,stroke:#84cc16,stroke-width:2px,color:#ecfccb;
	classDef channel fill:#020617,stroke:#facc15,stroke-width:2px,color:#fffbeb;

	subgraph Management_Channel[Management]
		direction LR
		CH_MAN([Management]):::channel
		OWN_MAN[Owners]:::role
		CM_MAN[Community Managers]:::cohort
		PM_MAN[Product Managers]:::cohort
		SM_MAN[Server Managers]:::cohort
		AMB_MAN[Ambassadors]:::cohort

		OWN_MAN --> CH_MAN
		CM_MAN --> CH_MAN
		PM_MAN --> CH_MAN
		SM_MAN --> CH_MAN
		AMB_MAN --> CH_MAN
	end

	subgraph Staff_Channel[Staff]
		direction LR
		CH_STF([Staff]):::channel
		OWN_STF[Owners]:::role
		STF_STF[Staff]:::role
		CM_STF[Community Managers]:::cohort
		PM_STF[Product Managers]:::cohort
		SM_STF[Server Managers]:::cohort
		AMB_STF[Ambassadors]:::cohort

		OWN_STF --> CH_STF
		STF_STF --> CH_STF
		CM_STF --> CH_STF
		PM_STF --> CH_STF
		SM_STF --> CH_STF
		AMB_STF --> CH_STF
	end

	subgraph Developers_Channel[Developers]
		direction LR
		CH_DEV([Developers]):::channel
		OWN_DEV[Owners]:::role
		DEV_DEV[Developers]:::role
		CM_DEV[Community Managers]:::cohort
		PM_DEV[Product Managers]:::cohort
		SM_DEV[Server Managers]:::cohort
		AMB_DEV[Ambassadors]:::cohort

		OWN_DEV --> CH_DEV
		DEV_DEV --> CH_DEV
		CM_DEV --> CH_DEV
		PM_DEV --> CH_DEV
		SM_DEV --> CH_DEV
		AMB_DEV --> CH_DEV
	end

	subgraph Production_Channel[Production]
		direction LR
		CH_PROD([Production]):::channel
		OWN_PROD[Owners]:::role
		STF_PROD[Staff]:::role
		DEV_PROD[Developers]:::role
		CM_PROD[Community Managers]:::cohort
		PM_PROD[Product Managers]:::cohort
		SM_PROD[Server Managers]:::cohort
		MAP_PROD[Mappers]:::role
		AMB_PROD[Ambassadors]:::cohort

		OWN_PROD --> CH_PROD
		STF_PROD --> CH_PROD
		DEV_PROD --> CH_PROD
		CM_PROD --> CH_PROD
		PM_PROD --> CH_PROD
		SM_PROD --> CH_PROD
		MAP_PROD --> CH_PROD
		AMB_PROD --> CH_PROD
	end

	subgraph Development_Channel[Development]
		direction LR
		CH_DEVT([Development]):::channel
		OWN_DEVT[Owners]:::role
		DEV_DEVT[Developers]:::role
		CM_DEVT[Community Managers]:::cohort
		PM_DEVT[Product Managers]:::cohort
		SM_DEVT[Server Managers]:::cohort
		MAP_DEVT[Mappers]:::role
		AMB_DEVT[Ambassadors]:::cohort

		OWN_DEVT --> CH_DEVT
		DEV_DEVT --> CH_DEVT
		CM_DEVT --> CH_DEVT
		PM_DEVT --> CH_DEVT
		SM_DEVT --> CH_DEVT
		MAP_DEVT --> CH_DEVT
		AMB_DEVT --> CH_DEVT
	end

	%% Channel-colored connections for readability
	linkStyle 0 stroke:#fb923c,stroke-width:2px;
	linkStyle 1 stroke:#fb923c,stroke-width:2px;
	linkStyle 2 stroke:#fb923c,stroke-width:2px;
	linkStyle 3 stroke:#fb923c,stroke-width:2px;
	linkStyle 4 stroke:#fb923c,stroke-width:2px;

	linkStyle 5 stroke:#c084fc,stroke-width:2px;
	linkStyle 6 stroke:#c084fc,stroke-width:2px;
	linkStyle 7 stroke:#c084fc,stroke-width:2px;
	linkStyle 8 stroke:#c084fc,stroke-width:2px;
	linkStyle 9 stroke:#c084fc,stroke-width:2px;
	linkStyle 10 stroke:#c084fc,stroke-width:2px;

	linkStyle 11 stroke:#38bdf8,stroke-width:2px;
	linkStyle 12 stroke:#38bdf8,stroke-width:2px;
	linkStyle 13 stroke:#38bdf8,stroke-width:2px;
	linkStyle 14 stroke:#38bdf8,stroke-width:2px;
	linkStyle 15 stroke:#38bdf8,stroke-width:2px;
	linkStyle 16 stroke:#38bdf8,stroke-width:2px;

	linkStyle 17 stroke:#34d399,stroke-width:2px;
	linkStyle 18 stroke:#34d399,stroke-width:2px;
	linkStyle 19 stroke:#34d399,stroke-width:2px;
	linkStyle 20 stroke:#34d399,stroke-width:2px;
	linkStyle 21 stroke:#34d399,stroke-width:2px;
	linkStyle 22 stroke:#34d399,stroke-width:2px;
	linkStyle 23 stroke:#34d399,stroke-width:2px;
	linkStyle 24 stroke:#34d399,stroke-width:2px;

	linkStyle 25 stroke:#fb7185,stroke-width:2px;
	linkStyle 26 stroke:#fb7185,stroke-width:2px;
	linkStyle 27 stroke:#fb7185,stroke-width:2px;
	linkStyle 28 stroke:#fb7185,stroke-width:2px;
	linkStyle 29 stroke:#fb7185,stroke-width:2px;
	linkStyle 30 stroke:#fb7185,stroke-width:2px;
	linkStyle 31 stroke:#fb7185,stroke-width:2px;

	linkStyle default stroke:#94a3b8,curve:basis;
```

Roles are intentionally repeated within each channel subgraph so every row stays compact and edges never cross.

## Quick Reference Rules

1. Management visibility is guaranteed in every channel listed here.
2. Staff gain access to the Staff and Production channels, aligning them with daily operations and release readiness.
3. Developers collaborate in three rooms: their dedicated channel, Production, and Development.
4. Mappers join Production (for ship-ready work) and Development (for iterative work), ensuring they stay paired with Developers and Management.
5. Ambassadors mirror management access until a formal role document is added.
