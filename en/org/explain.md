---
description: Rights management solution based on RBAC design
icon: screwdriver-wrench
---

# Organization management framework description

### Feature Brief

The system is based on RBAC and provides a complete organizational management solution that enables organizations to effectively organize teams, assign permissions, and monitor resource usage. Hierarchical design makes it easy to create and manage multiple roles while ensuring proper permission control and resource allocation.

<figure><img src="../.gitbook/assets/截圖 2025-03-30 下午6.42.56.png" alt=""><figcaption></figcaption></figure>

Roles are the core units that define permissions and resource allocation. Organizational owners can set specific functional permissions and resource quotas for each role according to the needs of different teams to achieve granular management.

<table><thead><tr><th>Member Type</th><th width="215.55859375"> Description</th><th> Permission Scope</th></tr></thead><tbody><tr><td> Owner</td><td> Defaults to the creator of the organization</td><td> Has organization settings permissions in Admin<br>to assign organization settings permissions to others</td></tr><tr><td> Regular Members</td><td> Members in Roles</td><td> Permissions and resources for all roles, such as internal Q&A, conversation permissions, etc.</td></tr></tbody></table>

### Hierarchy

* * * Hierarchical * *: Organization → role → members
* * * Flexible permissions * *: can be set individually according to role requirements
* * * Centralized management * *: Organizational owners manage all settings in one place
* * * Membership flexibility * *: Ability to participate in different projects or teams across roles

<figure><img src="../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

### Create Organization

* Any account user can create a new organization
* The organization creator automatically becomes the owner of the organization
* Separate management space for each organization

<figure><img src="../.gitbook/assets/截圖 2025-03-30 下午5.55.17.png" alt=""><figcaption></figcaption></figure>

### Organization Owner Role

#### Member Management

* Add new members to the organization and assign them to roles via email
* Removing a member from a role

#### Managing Roles

* People with Organization Settings permissions can manage role settings to give permissions to each role.
* Once the role is created, members can be added to the role to inherit the permissions and resources to which the role belongs.

#### 权限管理

Set the following permissions for the role:

* AI Assistant permissions
* All Q&A permissions
* Internal Q&A permissions
* Chat Platform Permissions
* Organization settings permissions

#### Resource Allocation

To assign available resources to a role:

<figure><img src="../.gitbook/assets/截圖 2025-03-30 下午5.59.41.png" alt=""><figcaption></figcaption></figure>

### Role Features

* Roles are functional units within an organization, with freely configurable membership
* Roles can be assigned to members from any member within the organization
* One member can inherit multiple roles at the same time for flexible permission management
* Each role has its own permission settings for different scenarios

### Design Advantages

Designs like this can:

* Make the internal structure of the organization clearer
* Easily manage permission requirements for different teams
* Provides real-time visibility into your organization's operations
* Ensure effective management of resource use