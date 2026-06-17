# Local AI Stack

One-command deployment of a private, self-hosted AI assistant.

Local AI Stack installs, configures, and manages a complete local AI environment using Ollama and Open WebUI. It automatically detects available hardware, recommends suitable models, and provides sensible defaults while remaining fully configurable.

## Features

### Automated Installation

* Installs Ollama if not already present
* Installs and configures Open WebUI
* Downloads a recommended model automatically
* Configures services to start on boot

### Hardware-Aware Configuration

* Detects CPU, RAM, GPU, and VRAM
* Recommends model sizes based on available resources
* Prevents selecting models that exceed hardware limits
* Supports CPU-only systems

### Guided Setup Wizard

Interactive setup questions:

* Primary use case

  * Coding
  * General chat
  * Research
  * Writing
  * Local knowledge assistant
* Desired response quality vs speed
* Available disk space
* Privacy preferences
* Optional advanced settings

### Intelligent Model Selection

Examples:

| Use Case            | Recommended Models            |
| ------------------- | ----------------------------- |
| Coding              | Qwen3-Coder, DeepSeek-Coder   |
| General Chat        | Qwen3, Gemma                  |
| Research            | Qwen3, DeepSeek               |
| Writing             | Qwen3, Gemma                  |
| Lightweight Systems | Small Qwen3 or Gemma variants |

Recommendations are adjusted according to available hardware.

### Reconfiguration

After installation users can:

* Switch models
* Download new models from Ollama
* Remove unused models
* Re-run hardware detection
* Modify Open WebUI settings
* Update installed components

### Privacy First

* Everything runs locally
* No cloud accounts required
* No API keys required
* No telemetry by default
* User data remains on the machine

## Architecture

```
┌─────────────────┐
│ Local AI Stack  │
│ Setup Wizard    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Hardware Detect │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Model Selection │
└────────┬────────┘
         │
         ▼
 ┌───────────────┐
 │    Ollama     │
 └───────┬───────┘
         │
         ▼
 ┌───────────────┐
 │  Open WebUI   │
 └───────────────┘
```

## Installation

### Linux

```bash
curl -fsSL https://<to-be-determined>.com/install.sh | bash
```

### Manual Build

```bash
git clone https://github.com/RD2P/local-ai-stack.git
cd local-ai-stack

cargo build --release
```

## Example Setup

```text
Detected Hardware:
CPU: Ryzen 7 7700
RAM: 32 GB
GPU: RTX 4070
VRAM: 12 GB

Primary Use Case?
> Coding

Performance Preference?
> Balanced

Recommended Model:
> qwen3-coder:14b

Proceed with installation? [Y/n]
```

## Commands

```bash
local-ai-stack install
local-ai-stack configure
local-ai-stack models
local-ai-stack update
local-ai-stack doctor
local-ai-stack uninstall
```

## Goals

* Make local AI accessible to non-technical users
* Provide optimal default configurations
* Preserve privacy by default
* Eliminate manual setup steps
* Allow advanced customization when desired

## Technology Stack

### Runtime

* Ollama

### Interface

* Open WebUI

### Local AI Stack

* Rust (planned)

## Roadmap

### v0.1

* Linux support
* Ollama installation
* Open WebUI installation
* Hardware detection
* Model recommendation engine

### v0.2

* GUI installer
* Model benchmarking

