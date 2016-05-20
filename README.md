# ovirt_iso_uploader Ansible role

This role will upload ISOs to ovirt 3.6 hosted engine.

When this role is run it will fetch an ISO from a web server.

First you will need to upload your ISO to a webserver.
Then you need to create a checksum file for your ISO and place it in the same folder.

eg.

If your image is named ubuntu-14_04.iso

do the following.
```
$ md5sum  ubuntu-14_04.iso > ubuntu-14_04.iso.chk
```

This is used so that ansible will download the checksum file and if that changes ansible will re-download the ISO.

##Requirements
Centos 7
Ansible 1.4 and a above

##Role variables
* ovirt_iso_uploader_engine_user: 
Ovirt engine username.

* ovirt_iso_uploader_engine_password: 
Ovrt engine password.

* ovirt_iso_uploader_engine_fqdn: 
Ovirt engine password.

* ovirt_iso_uploader_iso_url:
The URL of where the ISOs are stored.

* ovirt_iso_uploader_images:
Name of image to download. 

## Example Playbook
```yaml
- hosts: ovirt_host
  roles:
    - ovirt_iso_uploader
```

See defaults for values.
