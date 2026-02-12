---
name: campaign-orchestrator
description: Multi-channel follow-up campaign orchestrator for ShapeScale sales. Schedules and executes SMS + Email sequences with CRM logging and auto-termination on replies. Use when following up with demo leads or managing outreach campaigns.
homepage: https://github.com/kesslerio/shapescale-moltbot-skills
metadata: {"moltbot":{"emoji":"📋","requires":{"env":["DIALPAD_API_KEY","ATTIO_API_KEY","GOG_KEYRING_PASSWORD"]},"primaryEnv":"DIALPAD_API_KEY"}}
---

# Campaign Orchestrator

Multi-channel follow-up campaign orchestrator for ShapeScale sales. Executes scheduled SMS + Email sequences with CRM integration and auto-termination on replies.

## Quick Start

```bash
# Start a campaign
python3 campaign.py start "primary" --lead "Apex Fitness"

# Check status
python3 campaign.py status "Apex Fitness"

# List all active
python3 campaign.py list

# Stop a campaign
python3 campaign.py stop "Apex Fitness" --reason "replied_interested"
```

## Key Rules

1. **NEVER campaign to existing customers** unless explicitly requested for upsell
2. **Pre-campaign checklist is MANDATORY**: verify customer status, email formatting, tone
3. **Auto-termination**: campaigns stop when lead replies to any message
4. **All actions logged to Attio CRM**

## Campaign Templates

| Template | Timing | Channel | Purpose |
|----------|--------|---------|---------|
| `primary` | +4 hours | SMS | Recap demo, share recording |
| `secondary` | +1 day | Email | Pricing, detailed ROI |
| `tertiary` | +4 days | SMS | Quick check-in |
| `quaternary` | +7 days | Email | Final follow-up, case study |
| `post-demo` | +0 hours | SMS | Immediate thank you |

## Reference Documentation

- **`references/campaign-guide.md`** — Full reference: setup, all CLI commands, pre-campaign checklist, template variables, architecture, state management, cron integration, webhook handling, integration points, examples, action logging, and troubleshooting
