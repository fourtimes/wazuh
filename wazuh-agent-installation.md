Deploying Wazuh agents on Linux endpoints
---

_**Add the Wazuh repository**_

_Install the GPG key_

```cmd
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import && chmod 644 /usr/share/keyrings/wazuh.gpg
```

_Add the repository_

```cmd
echo "deb [signed-by=/usr/share/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list
```
_Update the package_

```cmd
apt-get update
```
**_Deploy Wazuh agent_**

* To deploy the Wazuh agent on your endpoint, select your package manager and edit the WAZUH_MANAGER variable to contain your Wazuh manager IP address or hostname
* Find Manager-server ip add and paste it here

```cmd
WAZUH_MANAGER="wazuh-manager-server-ip" apt-get install wazuh-agent -y
```

_Enable and start the Wazuh agent service_

```cmd
systemctl daemon-reload
systemctl enable wazuh-agent
systemctl start wazuh-agent
```

[OR]
---
1. Go to the wazuh manager console - https://wazuh-manager-public-ip
2. Click on the `add new agent (or) deploy new agent` option.
3. Select your wazuh agent OS type.
4. Paste the wazuh manager public ip.
5. Select the default method.
6. copy the command and paste it to the agent server and execute the command.
7. after executing the command, we need to start and enable the wazuh agent service.
8. Go to the wazuh manager console, and check it to the wazuh added agent.

 



