**Run the container**

   * map ssh socket in the container to allow Ansible to ssh into your hosts
   * map your current working dir in the container to gain access to the inventory & playbook files (assumes these are relative to local path)

```console
$ docker run --rm -v "${SSH_AUTH_SOCK}:/home/ansible/.ssh/ssh_auth_sock" -e "SSH_AUTH_SOCK=/home/ansible/.ssh/ssh_auth_sock" -v $(pwd):/home/ansible/ --dns=${DOCKER_DNS} <name>:<tag> "$@"
```
