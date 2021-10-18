
# Jenkins Role

Role Ansible Install, deploy configuration

## Features

- Install Jenkins Master / Slave Node ( Support Windows, Debian, RedHat )
- Render Configurations jenkins master, agent-jenkins
- Create User handle service jenkins, agent
- Create Script automate install list plugin input
- Automate Add Node with SSH mode and JNLP
- Automate Add Credentials for NODE SSH mode

  
## Parameter Reference

#### Master node

| Parameter         |   Type    | Default Value | Description                |
| :---------------- | :---------| :------------ | :------------------------- |
| `httpPort`        | `number`  |    8080       | **Required**. Static port running jenkins master |
| `MaxHeapSize`     | `number`  |    1024       | **Required**.  |
| `jenkinAdmin`     | `string`  |    admin      |   |
| `jenkinAdminPwd`  | `string`  |    admin      |   |
| `jenkinsPreferLts`| `boolean` |    true       |   |
| `jenkins_plugins` | `string`  |    N/A        |   |
| `jenkinsVer`      | `string`  |    2.303.2    |   |



  
## Deployment

To deploy this project run

```bash
    git clone https://github.com/songhanpoo/jenkins.git
```

```bash
    ansible-playbook -i test/inventories.yml test/playbook.yml -u <user> -K
```
  
## Structure role

This project is used by the following companies:
```bash
.
├── README.md
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── tasks
│   ├── config-Debian.yml
│   ├── config-RedHat.yml
│   ├── config-Windows.yml
│   ├── credentials.yml
│   ├── main.yml
│   ├── node.yml
│   ├── setup-Debian.yml
│   ├── setup-RedHat.yml
│   └── setup-Windows.yml
├── templates
│   ├── Debian
│   │   ├── jenkins-agent.service.j2
│   │   └── jenkins.j2
│   ├── RedHat
│   │   ├── jenkins-agent.service.j2
│   │   └── jenkins.j2
│   ├── Windows
│   │   ├── agent.bat.j2
│   │   └── jenkins.win.xml.j2
│   └── init.groovy.j2
├── tests
│   ├── host
│   ├── inventory.ubuntu.yml
│   ├── inventory.windows.yml
│   └── test.yml
└── vars
    ├── Debian.yml
    ├── RedHat.yml
    ├── Windows.yml
    └── main.yml

```

  