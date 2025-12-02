---
title: "[Sample] D365 - Commonly Used SQL"
date: 2025-02-17T04:06:31Z
tags: ["Dynamics 365", "D365 Note"]
description: A guide on commonly used SQL queries in Dynamics 365 for querying views, reports, file sizes, security roles, and user assignments.
---

## Querying all views under a specific entity

```sql
-- Example: Query all views and their Ids under the Account entity
SELECT 
    v.SavedQueryId AS 'View Id', 
    v.Name AS 'View name',
    v.returnedtypecode AS 'Owning entity'
FROM 
    SavedQuery v
WHERE 
    returnedtypecode = 'account'
```

## Querying reports/report Ids

```sql
SELECT reportid,
       name,
       filename,
       description,
       owneridname,
       componentstatename,
       createdon,
       createdbyname
FROM   report;
```

## Querying Annotation file size

```sql
-- Warning: May freeze if data is large
-- 1 MB = 1024 * 1024 Bytes = 1,048,576 Bytes
SELECT SUM(filesize) / 1048576 AS TotalFileSizeMB
FROM   annotation;
```

## Finding users assigned to a specific security role

```sql
SELECT 
    systemuser.fullname AS UserFullName,
    systemuser.domainname AS DomainName,
    systemuser.systemuserid AS UserId,
    role.name AS RoleName
FROM 
    systemuserroles
INNER JOIN 
    systemuser ON systemuserroles.systemuserid = systemuser.systemuserid
INNER JOIN 
    role ON systemuserroles.roleid = role.roleid
WHERE 
    role.name = 'Pre-sales' -- Security role name
```

Query result:

| UserFullName | DomainName | UserId | RoleName |
| :--- | :--- | :--- | :--- |
| Zhang San | <zhangsan@sample.com> | xxx.. | Pre-sales |
| Li Si | <lisi@sample.com> | xxx.. | Pre-sales |

## Finding security roles for users

```sql
SELECT 
    su.fullname AS UserFullName,
    su.domainname AS DomainName,
    su.systemuserid AS UserId,
    STRING_AGG(r.name, ', ') AS RoleNames
FROM 
    systemuserroles sur
INNER JOIN 
    systemuser su ON sur.systemuserid = su.systemuserid
INNER JOIN 
    role r ON sur.roleid = r.roleid
GROUP BY 
    su.fullname,
    su.domainname,
    su.systemuserid
ORDER BY 
    su.fullname
```

Query result:

| UserFullName | DomainName | UserId | RoleName |
| :--- | :--- | :--- | :--- |
| Zhang San | <zhangsan@sample.com> | xxx | Pre-sales, Sales Manager |
| Li Si | <lisi@sample.com> | xxx | Pre-sales, Sales Director, System Administrator |