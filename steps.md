```
// windows 

open start >> cmd >> as a admin 

mkdir myagent
cd myagent

// copy set up from downloads and paste in myagent

./config.cmd

server URL: https://dev.azure.com/cloudnautic
PAT >> Enter 
PAT >> Paste 
Agent Pool: windows
Agent Pool: windows 
// else other settings defaults >> Press Enter Enter 

./run.cmd

start /B run.cmd

Agents >> Update Agents 

//mac 

mkdir myagent 
cd myagent
sudo mv /Users/atul/Downloads/vsts-agent-osx-x64-5.280.0.tar.gz /Users/atul/myagent
ar zxvf vsts-agent-osx-x64-5.280.0.tar.gz
ls
chmod +x config.sh 
chmod +x run.sh  

xattr -dr com.apple.quarantine .
xattr bin/Agent.Listener

server url: https://dev.azure.com/cloudnautic/

Enter PAT 

./config.sh 

./run.sh 

nohup ./run.sh > agent.log 2>&1 &
```

1. create repo in github 

https://github.com/user-name/azure-pipelines-agent

2. create file azure-pipelines.yml

trigger:
- main

pool:
  name: pool-name
  demands:
  - Agent.Name -equals agent-name

steps:
- script: echo Hello from Windows Self-Hosted Agent
  displayName: 'Hello World'

- script: hostname
  displayName: 'Check Hostname'

3. commit Code 

4. Azure Pipelines >> Github Connection >> Select Repo 

5. // It will automatically select Yaml azure pipeline 

6. Build & Run 
