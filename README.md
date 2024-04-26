Deploy Moodle
=========

This role is for deploying and managing Moodle instances with different versions.

It is intended to be used with the Ansible Tower and the Xayma.sh Platform already deployed (with all it's components).
However if you want to use command create and manage n8n instances from the command line, with the Xayma.sh Platform already deployed, you can use the following:

```bash
ansible-playbook site.yml -i production --tags "deploy" --extra-vars "organization=xaymasolutions instancename=automation domain=moodle.xaymasolutions.com" --vault-pass-file "vault_password" -K
```

Requirements
------------
- Deployment of the Xayma.sh Platform. Otherwise this is completely useless.
- Make sure to use the secret vault password 😎. Can be a file (if you are using CLI) or a credential record in Ansible Tower.


Role Tags
---------
You can use this role with the following tags: 

| Tag                    | Description              |
|------------------------|--------------------------|
| deploy             | To create a new instance of Moodle      |
| stopinstance           | To stop the instance     |
| startinstance          | To start the instance    |
| suspendinstance        | To suspend the instance (stop and display a "suspended" page in the browser) |
| editinstancedomainname | To change the main domain name of the instance   |


Role Variables
--------------

You can customize you instance by using thes variables
| Tag                    | Description              |
|------------------------|--------------------------|
| organization           | The customer for which the instance is being created (*should be one single word with no special characters*) |
| instancename           | The name of the instance (*should be one single word with no special characters*)  |
| domain                 | The domain name to which the instance will be bound |
| version                | The version N8N that will be deployed (*Should be an existing version*) |


Dependencies
------------
All dependencies should be already installed during the deployment of the Xayma.sh platform.

License
-------

MIT

Author Information
------------------

- Elhadji Malang Diedhiou  
For the past nine years I have been helping businesses to increase efficiency, using automation tools. I am passionate in learning and sharing.  
**More about me**:
  * [LinkedIn]
  * [Twitter]
  * [GitHub]

[LinkedIn]: https://linkedin.com/in/supermalang
[GitHub]: https://github.com/supermalang
[Twitter]: https://twitter.com/supermalang_