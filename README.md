# zlegbot toolkit

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Small, mechanical, MIT-licensed automation tools. They cut AI-agent credit usage by doing deterministic work in cron and CI instead of LLM turns.

## Tools

| Tool | What it does |
| --- | --- |
| [zlegbot-wakegate](https://github.com/zlephir42069/zlegbot-wakegate) | Cron-first wake gate: it evaluates cheap signals on a schedule and calls the agent only when one of them fires. The gate does not call a model. |
| [zlegbot-claimcheck](https://github.com/zlephir42069/zlegbot-claimcheck) | Mechanically verifies an agent's done report against real files, hashes, URLs, and commands. |
| [zlegbot-autostart](https://github.com/zlephir42069/zlegbot-autostart) | Zero-credit recovery hook after reboot or reset, with a GitHub Actions fallback. |
| [zlegbot-notifier](https://github.com/zlephir42069/zlegbot-notifier) | Idempotent scheduled announcement poster for cron and GitHub Actions. |
| [zlegbot-usage-audit](https://github.com/zlephir42069/zlegbot-usage-audit) | Offline analyzer that finds wasted agent runs in logs. |

## How they fit together

autostart restores the jobs after a reboot or reset. wakegate gates each cycle and wakes an agent only when a cheap check fires. notifier announces on a schedule and does not post the same announcement twice. claimcheck verifies the agent's done report against the files, hashes, URLs, and commands it names. usage-audit measures the logs afterward and flags runs that did not need a wake.

## Install

```bash
python -m pip install "git+https://github.com/zlephir42069/<repo>.git"
```

Replace `<repo>` with the repository name, for example `zlegbot-wakegate`. wakegate requires Python 3.10 or newer.
