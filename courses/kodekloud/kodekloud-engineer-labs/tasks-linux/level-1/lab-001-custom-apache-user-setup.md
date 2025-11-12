
------------------------------

- [Requirements](#requirements)
- [Steps](#steps)
- [Resources](#resources)

------------------------------

# Lab 001: Custom Apache User Setup

## Requirements

In response to heightened security concerns, the `xFusionCorp Industries` security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:

a. Create a user named **mariyam** on App Server 2 in Stratos Datacenter.
b. Set UID to 3120 and its home directory to **/var/www/mariyam.**

------------------------------

## Steps


Login to the app server and switch to root. For the server credentials, check out the [Project Nautilus documentation.](https://kodekloudhub.github.io/kodekloud-engineer/docs/projects/nautilus)


```bash
sshpass -p  '**********' ssh -o StrictHostKeyChecking=no steve@172.16.238.11
sudo su -
**********  
```

Create the user based on the requirements.

```bash
useradd -u 3120 -d /var/www/mariyam mariyam 
```

Verify.

```bash
id mariyam
grep mariyam /etc/passwd 
```

------------------------------

## Notes