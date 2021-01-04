# Azure DevOps Server self-hosted agent Dockerfile

## Windows
1.  Enable Hyper-V
2.  Install Docker for Windows
3.  Switch Docker to use Windows containers
4.  Run the following command within that directory: 
    
    docker build -t dockeragent:latest .

5.  Start the image

    docker run -e AZP_URL=<Azure DevOps instance> -e AZP_TOKEN=<PAT token> -e AZP_AGENT_NAME=mydockeragent dockeragent:latest

<br>

## Linux
1.  Install Docker
2.  Run the following command within that directory:

    docker build -t dockeragent:latest .
3.  Start the image

    docker run -e AZP_URL=<Azure DevOps instance> -e AZP_TOKEN=<PAT token> -e AZP_AGENT_NAME=mydockeragent dockeragent:latest

<br>

### Note:

1.  AZP_URL<br>
The URL of the Azure DevOps or Azure DevOps Server instance.

2.  AZP_TOKEN<br>
Personal Access Token (PAT) with Agent Pools (read, manage) scope, created by a user who has permission to configure agents, at AZP_URL.

3.  AZP_AGENT_NAME<br>
Agent name (default value: the container hostname).

4.  AZP_POOL<br>
Agent pool name (default value: Default).

5.  AZP_WORK<br>
Work directory (default value: _work).