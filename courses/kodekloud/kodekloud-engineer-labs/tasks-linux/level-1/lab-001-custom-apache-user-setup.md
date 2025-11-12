
------------------------------

- [Requirements](#requirements)
- [Steps](#steps)
- [Resources](#resources)

------------------------------

# Lab 001: Custom Apache User Setup

## Requirements

In response to heightened security concerns, the `xFusionCorp Industries` security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:

a. Create a user named `ammar` on `App Server 2` in Stratos Datacenter.
b. Assign a unique UID `1194` and its home directory to `/var/www/ammar`.

------------------------------

## Steps


Login to the app server and switch to root. For the server credentials, check out the [Project Nautilus documentation.](https://kodekloudhub.github.io/kodekloud-engineer/docs/projects/nautilus)


```bash
sshpass -p  '**********' ssh steve@stapp02
sudo su -
**********  
```

Create the user based on the requirements.

```bash
useradd ammar -u 1194 -d /var/www/ammar 
```

Verify.

```bash
id ammar
grep ammar /etc/passwd 
```

------------------------------

## Notes

![](https://i.imgur.com/M8gvtOR.png)