# How To Configure Sonarlint for VSCode
## Install Sonarlint Extension
Install [SonarLint](https://www.sonarlint.org/vscode/) extension for VSCode

![enter image description here](https://user-images.githubusercontent.com/40820154/64608741-9f8ab400-d3cb-11e9-8739-5a1ce2c743bd.png)

## Create Sonar Token
Generate a Sonar __token__ under the menu *My Account* → *Security*

![enter image description here](https://user-images.githubusercontent.com/40820154/64609174-99490780-d3cc-11e9-924f-79a8d6b031de.png)

## Configure Sonarlint extension on VSCode
### Configure user settings
Under *VSCode Settings*, search for sonarlint and edit ```connectedMode.servers```

![enter image description here](https://user-images.githubusercontent.com/40820154/64609726-db267d80-d3cd-11e9-84db-cc6b92212501.png)

Add these lines to *settings.json* file
> Do not forget to put your Sonar Token
```
"sonarlint.connectedMode.servers":  [{
	"serverId":  "sonarqube",
	"serverUrl":  "https://scmqm2.deutsche-boerse.de/sonar",
	"token":  "YOUR_TOKEN_GOES_HERE"
}],
"sonarlint.analyzerProperties":  {
	"sonar.javascript.globals":  "sap"
}
```
![enter image description here](https://user-images.githubusercontent.com/40820154/64610034-9f3fe800-d3ce-11e9-8176-d4f8750ce278.png)

### Configure workspace settings
Under *VSCode Settings*, search for sonarlint and edit ```connectedMode.Project```

> ⚠️**WARNING**: Make sure you are on Workspace settings tab!
> ![enter image description here](https://user-images.githubusercontent.com/40820154/64610523-b29f8300-d3cf-11e9-820a-d5c72822bc9b.png =500x)

![enter image description here](https://user-images.githubusercontent.com/40820154/64610174-f776ea00-d3ce-11e9-9bda-b8f88b71f20f.png)

Add these lines to *settings.json* file
```
"sonarlint.connectedMode.project":  {
	"serverId":  "sonarqube",
	"projectKey":  "sap.crm-001"
}
```
## Identifying Issues
You can see the issues with the ```sonarlint``` tag on Problems tab

![](https://user-images.githubusercontent.com/40820154/64610758-3b1e2380-d3d0-11e9-9c69-46421ad91fe9.png)
