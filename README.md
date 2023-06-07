# jenkins-docker
Use Jenkins with Docker Environments

## Troubleshoot
### Problem with /var/jenkins_home/.ssh/known_hosts
#### Add new host to known_hosts file

`ssh-keyscan -H jenkins-agent > /var/jenkins_home/.ssh/known_hosts`

More:

```
ssh-keygen -R [hostname]
ssh-keygen -R [ip_address]
ssh-keygen -R [hostname],[ip_address]
ssh-keyscan -H [hostname],[ip_address] >> ~/.ssh/known_hosts
ssh-keyscan -H [ip_address] >> ~/.ssh/known_hosts
ssh-keyscan -H [hostname] >> ~/.ssh/known_hosts
```

Ref: https://serverfault.com/a/316100

