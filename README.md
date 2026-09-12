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
cd /Users/atulkamble/myagent
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
Agent Name : atulkamble-mac
Architecture: ARM
```

### Azure Pipeline

```yaml
trigger:
- main

pool:
  name: Default
  demands:
  - Agent.Name -equals atulkamble-mac

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
Agent Name : atulkamble-win
```

### Azure Pipeline

```yaml
trigger:
- main

pool:
  name: Default
  demands:
  - Agent.Name -equals atulkamble-win

steps:
- script: echo Hello from Windows Self-Hosted Agent
  displayName: 'Hello World'

- script: hostname
  displayName: 'Check Hostname'
```
