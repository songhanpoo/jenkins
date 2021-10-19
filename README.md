
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


| Parameter         |   Type    | Default Value | Description                |
| :---------------- | :---------| :------------ | :------------------------- |
| `httpPort`        | `number`  |    8080       | Static port running jenkins master |
| `MaxHeapSize`     | `string`  |    1024m      | Set MaxHeapSize for jenkins master |
| `jenkinAdmin`     | `string`  |    admin      | Set admin account for jenkins master |
| `jenkinAdminPwd`  | `string`  |    admin      | Set password account for jenkins master  |
| `jenkinsPreferLts`| `boolean` |    true       |   |
| `jenkins_plugins` | `list`    |    N/A        |  Define list plugin for initialize |
| `jenkinsVer`      | `string`  |    N/A        |  Define version for install |

## Deployment

To deploy this project run

```bash
    git clone https://github.com/songhanpoo/jenkins.git
```
#### Linux Environment
```bash
    ansible-playbook -i test/inventories.ubuntu.yml test/playbook.yml -u <user> -K
```

#### Windows Environment

```bash
    ansible-playbook -i test/inventories.windows.yml test/playbook.yml -u <user> -K
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

  
## Documentation

[Setup a Windows Host](https://www.techbeatly.com/2020/12/configure-your-windows-host-to-manage-by-ansible.html)

  
## Authors


[![MIT License](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/songhanpoo)

[![MIT License](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge&logo=dev.to&logoColor=white
)](https://stackoverflow.com/users/10084143/songhanpoo)

[![MIT License](https://img.shields.io/badge/Stack_Overflow-FE7A16?style=for-the-badge&logo=stack-overflow&logoColor=white)](https://stackoverflow.com/users/10084143/songhanpoo)

## Ansible Galaxy Collection

**ansible.windows:** win_file, win_template, win_stat, win_acl, win_service, win_get_url

**chocolatey.chocolatey:** win_chocolatey

  
## Support Environments

[![MIT License](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/songhanpoo)

[![MIT License](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://github.com/songhanpoo)
  
