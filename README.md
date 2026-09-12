# azure-pipelines-agent
Agent Settings
# Azure DevOps Self-Hosted Agent Setup

## 1. Mac Agent – ARM

### Install Azure DevOps Extension

```bash
az extension add --name azure-devops
```

### Go to Agent Directory

```bash
cd /Users/mayurbarage/myagent
```

### Remove macOS Quarantine

```bash
xattr -dr com.apple.quarantine .
```

### Check Agent Listener

```bash
xattr bin/Agent.Listener
```

### Configure Agent

```bash
./config.sh
```

### Mac Agent Details

```text
Agent Pool : Default
Agent Name : Mayurs-MacBook-Air
Architecture: ARM
```

### Azure Pipeline

```yaml
trigger:
- main

pool:
  name: Default
  demands:
  - Agent.Name -equals Mayurs-MacBook-Air

steps:
- script: echo "Hello from Self-Hosted Mac Agent"
  displayName: 'Hello World'

- script: hostname
  displayName: 'Check Hostname'
```

---

# 2. Windows Agent

### Windows Agent Details

```text
Agent Pool : Default
Agent Name : DESKTOP-NN9BP9S
```

### Azure Pipeline

```yaml
trigger:
- main

pool:
  name: Default
  demands:
  - Agent.Name -equals DESKTOP-NN9BP9S

steps:
- script: echo Hello from Windows Self-Hosted Agent
  displayName: 'Hello World'

- script: hostname
  displayName: 'Check Hostname'
```
