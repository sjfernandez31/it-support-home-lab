# Lab 02 — User and Group Management

## Overview

In this lab I created Organizational Units, a user account, and a security group inside Active Directory Users and Computers. I then added the user to the group and verified the membership. These are some of the most common tasks an IT support technician performs when managing users in an enterprise environment.

## Environment

| Component | Details |
|---|---|
| Server OS | Windows Server 2022 |
| Platform | VMware Workstation Pro |
| Domain | support.local |
| Tool | Active Directory Users and Computers |

## What are Organizational Units

Organizational Units are containers inside Active Directory that allow administrators to organize users, computers, and groups into logical structures. They make it easier to manage objects and apply Group Policy to specific sets of users or machines.

## What are Security Groups

Security groups are used to manage access to resources. Instead of assigning permissions to individual users you add users to a group and assign permissions to the group. This makes managing access across a large number of users much easier.

## Steps

### Step 1 — Open Active Directory Users and Computers
I opened Server Manager and clicked **Tools** in the top right corner then selected **Active Directory Users and Computers**.

### Step 2 — Create Organizational Units
I right clicked on `support.local` in the left panel, hovered over **New**, and clicked **Organizational Unit**. I created three Organizational Units one at a time:

```
IT Users
IT Computers
IT Groups
```

Each OU now appears in the left panel under `support.local`.

### Step 3 — Create a User Account
I right clicked on the **IT Users** OU, hovered over **New**, and clicked **User**. I filled in the following information:

| Field | Value |
|---|---|
| First Name | Steven |
| Last Name | Fernandez |
| User Logon Name | sfernandez |

I clicked Next and set a password of **User123** with **User must change password at next logon** checked. I clicked Next then Finish.

### Step 4 — Create a Security Group
I right clicked on the **IT Groups** OU, hovered over **New**, and clicked **Group**. I filled in the following:

| Field | Value |
|---|---|
| Group Name | IT Support |
| Group Scope | Global |
| Group Type | Security |

I clicked OK to create the group.

### Step 5 — Add User to Group
I right clicked on the **IT Support** group and clicked **Properties**. I clicked the **Members** tab then clicked **Add**. I typed `sfernandez` in the search box and clicked **Check Names** to locate the account. I clicked OK to add the user then clicked OK again to close the Properties window.

### Step 6 — Verify Group Membership
I right clicked on the **sfernandez** user account in the IT Users OU and clicked **Properties**. I clicked the **Member Of** tab and confirmed the user was listed as a member of both **Domain Users** and **IT Support**.

## Result

Three Organizational Units were created to organize the lab environment. A user account was created and placed in the IT Users OU. A security group called IT Support was created in the IT Groups OU and the user was successfully added to it. Group membership was verified through the user properties.
