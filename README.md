F5 Declarative Onboarding (DO) Install
=========

This role will install Declarative Onboarding using F5's API. First we determine if we have DO locally, if not the sha256 checksum is downloaded followed by <br >
the DO rpm file from [F5's Github site](https://github.com/F5Networks/f5-declarative-onboarding/releases). Once downloaded and validated via sha256 checksum. Now focus is put on the F5 to see if DO exists, upon a 404 return (no DO installation exists)<br>
the installation begins and is verified.  Optionally you can delete the downloaded files.

Requirements
------------

None

Role Variables
--------------

Variables needed for this role include:

* DO version tag
* DO RPM version number
* DO checksum file name
* F5 management IP Address
* F5 Administrator username
* F5 Administrator passowrd
* Path to roles directory

```
doTag: "v1.10.0"
doRPM: "f5-declarative-onboarding-1.10.0-2.noarch.rpm"
doSha: "f5-declarative-onboarding-1.10.0-2.noarch.rpm.sha256"
f5_mgmt: "<IP address>"
f5_u_cred: "admin"
f5_u_pass: "secret"
roles_d: "/home/user/roles"

```


Dependencies
------------

None

Example
----------------


```
---
- hosts: [adc]
  gather_facts: no
  connection: local

  vars_files:
    - var_file.yml

  roles:
    - f5_do_install
```



License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
