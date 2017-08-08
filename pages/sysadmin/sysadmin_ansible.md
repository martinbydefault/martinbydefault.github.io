---
title: Sysadmin / Ansible
tags: [sysadmin, ansible]
keywords: sysadmin, ansible
sidebar: wiki_sidebar
permalink: sysadmin_ansible.html
---

## Tips
* **validate**: If the service has this option available, use it to check the validity of the config file in order to detect and prevent an incorrect modification introduced by ansible (e.g. `sshd -tf` , `apachectl configtest`).
