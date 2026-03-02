# Project Meridian

**The open-source Kubernetes-native control plane and MCP server for Trino.**

No existing open-source tool manages the full Trino cluster lifecycle on Kubernetes. [Trino issue #396](https://github.com/trinodb/trino/issues/396) has been open since 2019. Meridian is the answer.

---

### What Meridian Does

| | |
|---|---|
| **Hot standby pool** | Pre-provisioned Trino clusters reserved instantly — no cold start |
| **Kubernetes operator** | Full lifecycle: `Empty → Pending → Idle → Reserved → Failed` |
| **Pool autoscaler** | Scales replica count based on reservation utilization |
| **MCP server** | 19 tools for AI agents to manage clusters, catalogs, credentials, and queries |

---

### Why It's Different

Every other Trino MCP server executes queries. Meridian **manages clusters** — provision, reserve, scale, rotate credentials, promote configs across environments.

The hot standby pool pattern (pre-provision N clusters, reserve one instantly) is what large data platform enterprises have built internally at significant cost. Meridian open-sources it with a Kubernetes-native operator and MCP-native interface.

Two long-standing community requests, now answered:

- [trinodb/trino #396](https://github.com/trinodb/trino/issues/396) — "Build a Kubernetes Operator for Trino" · open since 2019
- [trinodb/trino #26239](https://github.com/trinodb/trino/issues/26239) — "Add an official MCP Server"

---

### Get Started

```bash
# MCP server — for AI agents, Claude Desktop, CI/CD
brew install meridian-io/tap/meridian-mcp
docker pull ghcr.io/meridian-io/trino-mcp-server:v1.0

# Kubernetes operator — control plane
docker pull ghcr.io/meridian-io/trino-operator:v1.0
```

→ **[meridian-io/meridian](https://github.com/meridian-io/meridian)** — full docs, operator, CRDs, local dev setup
