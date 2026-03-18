<p align="center">
  <img src="assets/logo.jpg" alt="MCP Server Monitor" width="200" />
</p>

# mcp-server-monitor

> Real-time system monitoring through Claude Code. CPU, memory, disk, network, Docker, and process insights — right in your AI workflow.

<p align="center">
  <img src="https://img.shields.io/badge/MCP-Server-blue" alt="MCP Server" />
  <img src="https://img.shields.io/badge/TypeScript-5.7-blue" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Node.js-18%2B-green" alt="Node.js" />
  <img src="https://img.shields.io/badge/License-MIT-yellow" alt="MIT License" />
</p>

<p align="center">
  <img src="assets/banner.jpg" alt="MCP Server Monitor Banner" width="100%" />
</p>

## Why?

DevOps in your IDE. No more switching to terminals, dashboards, or Grafana just to check if your server is healthy. Ask Claude directly:

- *"Is the server overloaded?"*
- *"Which process is eating all the CPU?"*
- *"How much disk space is left?"*
- *"Are my Docker containers running?"*

## Quick Start

### Install globally

```bash
npm install -g mcp-server-monitor
```

### Or use with Claude Code

Add to your Claude Code MCP config (`~/.claude/claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "server-monitor": {
      "command": "npx",
      "args": ["-y", "mcp-server-monitor"]
    }
  }
}
```

### Or build from source

```bash
git clone https://github.com/VisualLock/mcp-server-monitor.git
cd mcp-server-monitor
npm install
npm run build
```

## Tools (22 total)

### System
| Tool | Description |
|------|-------------|
| `system_overview` | Complete system overview: OS, CPU, memory, uptime |
| `system_uptime` | System uptime and boot time |
| `system_users` | Currently logged-in users |

### CPU
| Tool | Description |
|------|-------------|
| `cpu_info` | Detailed CPU hardware info: model, cores, cache |
| `cpu_load` | Current CPU load with per-core breakdown and visual bars |
| `cpu_temperature` | CPU temperature readings |
| `cpu_history` | Monitor CPU load over time (1-60 seconds) |

### Memory
| Tool | Description |
|------|-------------|
| `memory_info` | RAM and swap usage with visual bars |
| `memory_layout` | Physical memory module details |

### Disk
| Tool | Description |
|------|-------------|
| `disk_usage` | All mounted filesystems with usage bars |
| `disk_io` | Disk I/O statistics: read/write speeds |
| `disk_smart` | S.M.A.R.T. health data for physical disks |

### Network
| Tool | Description |
|------|-------------|
| `network_interfaces` | All network interfaces with IPs, MACs, status |
| `network_stats` | Traffic statistics per interface |
| `network_connections` | Active connections with state filtering |
| `network_latency` | Ping any host to measure latency |

### Processes
| Tool | Description |
|------|-------------|
| `process_list` | Top processes by CPU or memory usage |
| `process_find` | Find processes by name |
| `process_detail` | Detailed info for a specific PID |

### Docker
| Tool | Description |
|------|-------------|
| `docker_containers` | List all Docker containers with status |
| `docker_stats` | Container resource usage (CPU, mem, network) |
| `docker_images` | Locally available Docker images |

### Health & Alerts
| Tool | Description |
|------|-------------|
| `health_check` | Comprehensive health check with configurable thresholds |
| `performance_report` | Full performance report combining all metrics |

## Example Output

```
📊  CPU Load
═══════════════════════════════════
Total:   23.5%
User:    18.2%
System:  5.3%
Idle:    76.5%

Per-Core Load:
─────────────────────────────
  Core 0: [████░░░░░░░░░░░░░░░░] 22.1%
  Core 1: [█████░░░░░░░░░░░░░░░] 25.0%
  Core 2: [████░░░░░░░░░░░░░░░░] 19.8%
  Core 3: [██████░░░░░░░░░░░░░░] 27.3%
```

```
✅  Health Check — OK
═══════════════════════════════════════════════════════
✅ CPU Load: 23.5% — CPU load normal
✅ Memory: 62.3% (10.24 GB/16.00 GB) — Memory usage normal
✅ Swap: 5.1% (0.52 GB/10.00 GB) — Swap usage normal
✅ Disk (/): 45.2% (214.50 GB/475.00 GB) — Disk / OK
⚠️ Disk (/data): 82.1% (780.00 GB/950.00 GB) — Disk /data filling up
```

## Supported Platforms

- **Windows** 10/11/Server
- **macOS** (Intel & Apple Silicon)
- **Linux** (all major distros)

## Requirements

- Node.js 18+
- Docker (optional, for container monitoring)

## Contributing

PRs welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

[MIT](LICENSE) — use it however you want.
