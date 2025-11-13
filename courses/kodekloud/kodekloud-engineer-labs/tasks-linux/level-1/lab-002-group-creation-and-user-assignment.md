
------------------------------

- [Requirements](#requirements)
- [Steps](#steps)
- [Resources](#resources)

------------------------------

# Lab 002: Group Creation and User Assignment

## Requirements

The system admin team at `xFusionCorp Industries` has streamlined access management by implementing group-based access control. Here's what you need to do:

a. Create a group named `nautilus_admin_users` across all App servers within the `Stratos Datacenter`.

b. Add the user `jarod` into the `nautilus_admin_users` group on all App servers. If the user doesn't exist, create it as well.

Note: You can find the infrastructure details by clicking on the **Details of all Users and Servers** button on the top-right section of the page.

------------------------------

## Steps


Login to the app server and switch to root. For the server credentials, check out the [Project Nautilus documentation.](https://kodekloudhub.github.io/kodekloud-engineer/docs/projects/nautilus)


```bash
ssh tony@stapp01
sudo su -
*********  
```

```bash
[root@stapp01 ~]# id jarod
id: ‘jarod’: no such user  
```

```bash
[root@stapp01 ~]# groupadd nautilus_admin_users
[root@stapp01 ~]# grep nautilus /etc/group
nautilus_admin_users:x:1002: 
```

```bash
[root@stapp01 ~]# useradd -G nautilus_admin_users jarod

[root@stapp01 ~]# id jarod
uid=1002(jarod) gid=1003(jarod) groups=1003(jarod),1002(nautilus_admin_users)

[root@stapp01 ~]# grep nautilus /etc/group
nautilus_admin_users:x:1002:jarod
```

Repeat the same steps on App server 2 and 3.


------------------------------

## Notes

I discovered you can also add users to a group using the `groupmems` utility.

```bash
[root@stapp01 ~]# groupmems -g nautilus_admin_users -a jarod

[root@stapp01 ~]# id jarod
uid=1002(jarod) gid=1003(jarod) groups=1003(jarod),1002(nautilus_admin_users)

[root@stapp01 ~]# grep nautilus /etc/group
nautilus_admin_users:x:1002:jarod
```