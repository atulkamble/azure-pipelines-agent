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

Settings 



```
