<p align="center">
  <img src="assets/logo.jpg" alt="MCP Server Monitor" width="200" />
</p>

<p align="center">
  <a href="README.md">English</a> | <a href="README_RU.md"><b>Русский</b></a>
</p>

# mcp-server-monitor

> Мониторинг сервера в реальном времени прямо из Claude Code. CPU, память, диски, сеть, Docker, процессы — 22 инструмента для DevOps прямо в IDE.

<p align="center">
  <img src="https://img.shields.io/badge/MCP-Server-blue" alt="MCP Server" />
  <img src="https://img.shields.io/badge/TypeScript-5.7-blue" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Node.js-18%2B-green" alt="Node.js" />
  <img src="https://img.shields.io/badge/License-MIT-yellow" alt="MIT License" />
</p>

<p align="center">
  <img src="assets/banner.jpg" alt="MCP Server Monitor Banner" width="100%" />
</p>

## Зачем?

DevOps прямо в IDE. Больше не нужно переключаться на терминалы, дашборды или Grafana, чтобы проверить состояние сервера. Просто спросите Claude:

- *"Сервер перегружен?"*
- *"Какой процесс жрёт весь CPU?"*
- *"Сколько места на диске осталось?"*
- *"Docker контейнеры работают?"*

## Быстрый старт

### Глобальная установка

```bash
npm install -g mcp-server-monitor
```

### Использование с Claude Code

Добавьте в конфиг MCP серверов Claude Code (`~/.claude/claude_desktop_config.json`):

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

### Сборка из исходников

```bash
git clone https://github.com/VisualLock/mcp-server-monitor.git
cd mcp-server-monitor
npm install
npm run build
```

## Инструменты (22 штуки)

### Система
| Инструмент | Описание |
|------------|----------|
| `system_overview` | Полный обзор системы: ОС, CPU, память, аптайм |
| `system_uptime` | Время работы и время загрузки |
| `system_users` | Залогиненные пользователи |

### CPU
| Инструмент | Описание |
|------------|----------|
| `cpu_info` | Подробная информация о CPU: модель, ядра, кэш |
| `cpu_load` | Текущая нагрузка с разбивкой по ядрам и визуальными индикаторами |
| `cpu_temperature` | Температура процессора |
| `cpu_history` | Мониторинг нагрузки CPU за период (1-60 секунд) |

### Память
| Инструмент | Описание |
|------------|----------|
| `memory_info` | Использование RAM и swap с визуальными индикаторами |
| `memory_layout` | Информация о физических модулях памяти |

### Диски
| Инструмент | Описание |
|------------|----------|
| `disk_usage` | Все смонтированные файловые системы с индикаторами заполненности |
| `disk_io` | Статистика ввода/вывода: скорость чтения/записи |
| `disk_smart` | Данные S.M.A.R.T. о здоровье дисков |

### Сеть
| Инструмент | Описание |
|------------|----------|
| `network_interfaces` | Все сетевые интерфейсы с IP, MAC, статусом |
| `network_stats` | Статистика трафика по интерфейсам |
| `network_connections` | Активные соединения с фильтрацией по состоянию |
| `network_latency` | Пинг любого хоста для измерения задержки |

### Процессы
| Инструмент | Описание |
|------------|----------|
| `process_list` | Топ процессов по CPU или памяти |
| `process_find` | Поиск процессов по имени |
| `process_detail` | Подробная информация о процессе по PID |

### Docker
| Инструмент | Описание |
|------------|----------|
| `docker_containers` | Список всех Docker контейнеров со статусом |
| `docker_stats` | Использование ресурсов контейнерами (CPU, память, сеть) |
| `docker_images` | Локальные Docker образы |

### Здоровье и алерты
| Инструмент | Описание |
|------------|----------|
| `health_check` | Комплексная проверка здоровья с настраиваемыми порогами |
| `performance_report` | Полный отчёт о производительности по всем метрикам |

## Пример вывода

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
✅ CPU Load: 23.5% — Нагрузка CPU в норме
✅ Memory: 62.3% (10.24 GB/16.00 GB) — Использование памяти в норме
✅ Swap: 5.1% (0.52 GB/10.00 GB) — Swap в норме
✅ Disk (/): 45.2% (214.50 GB/475.00 GB) — Диск / OK
⚠️ Disk (/data): 82.1% (780.00 GB/950.00 GB) — Диск /data заполняется
```

## Поддерживаемые платформы

- **Windows** 10/11/Server
- **macOS** (Intel и Apple Silicon)
- **Linux** (все основные дистрибутивы)

## Требования

- Node.js 18+
- Docker (опционально, для мониторинга контейнеров)

## Участие в разработке

PR приветствуются! Форкните репозиторий и создайте Pull Request.

## Лицензия

[MIT](LICENSE) — используйте как хотите.
