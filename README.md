# Jenkins implementation using Ansible Pulltle
<div align="center">
 <img src="https://1.bp.blogspot.com/-b7YyMHGBZ08/YYFHdXDqH_I/AAAAAAAAFuY/TFO2pYNrCeEkfFVtI8WVDl2LHrpxlz-BwCLcBGAsYHQ/s16000/under_const.jpg"</img>
</div>

## Resources deployed by this manifest:

## Tested with: 

| Environment | Application | Version  |
| ----------------- |-----------|---------|
| WSL2 Ubuntu 20.04 | Terraform | v1.0.0  |

## Deployment How-To:


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

```bash
wget https://raw.githubusercontent.com/JManzur/jenkins-ansible-pull/main/bootstrap.sh
chmod +x bootstrap.sh
./bootstrap.sh
ansible-pull -U https://github.com/JManzur/jenkins-ansible-pull.git
```

## Debugging / Troubleshooting:

#### **Debugging Tip #1**: 

#### **Known issue #1**: 
 - **Issue**: 
- **Cause**: 
- **Solution**: 

## Author:

- [@JManzur](https://jmanzur.com.ar)

## Documentation:

- [EXAMPLE](URL)