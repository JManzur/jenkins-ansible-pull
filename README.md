# Jenkins implementation using Ansible-Pull

**ansible-pull** is a part of Ansible that allows you to download a configuration playbook from a Git repository and immediately apply it on the machine running the ansible-pull command.

## Tested with: 

| Environment | Application | Version  |
| ----------------- |-----------|---------|
| Ubuntu 20.04.3 LTS | Terraform | v 2.9.6  |

### Using EC2 "User Data" (cloud-init):

```bash
  # Jenkins instalation with Ansible Pull
  user_data = <<EOF
  #!/bin/bash
  yum update -y
  yum install git
  amazon-linux-extras install ansible2
  sleep 10
  ansible-pull -U https://github.com/JManzur/bastion-ansible-pull.git
  EOF
```

#### Manual Installation:

Download the bootstrap script:
```bash
wget https://raw.githubusercontent.com/JManzur/jenkins-ansible-pull/main/bootstrap.sh
```

Make it executable:
```bash
chmod +x bootstrap.sh
```

Run it:
```bash
./bootstrap.sh
```

Pull:
```bash
ansible-pull -U https://github.com/JManzur/jenkins-ansible-pull.git
```

## Author:

- [@JManzur](https://jmanzur.com.ar)

## Documentation:

- [Jenkins Official Site](https://www.jenkins.io/)
- [Jenkins Handbook](https://www.jenkins.io/doc/book/)