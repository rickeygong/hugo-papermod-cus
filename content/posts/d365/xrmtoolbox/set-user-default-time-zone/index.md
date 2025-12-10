---
title: "D365 - Set User Default Time Zone"
date: 2025-08-28T04:06:31Z
tags: ["Dynamics 365", "XrmToolBox"]
description: Learn how to set the default time zone for users in Dynamics 365 using the User Settings Utility in XrmToolBox. This guide covers installation, user information loading, and time zone updating, along with SQL queries to retrieve current user time zone settings.
url: posts/d365/set-default-time-zone-for-user

cover:
  image: "images/hero-d365-default.webp"

---

Learn how to set the default time zone for users in Dynamics 365 using the User Settings Utility in XrmToolBox. This guide covers installation, user information loading, and time zone updating, along with SQL queries to retrieve current user time zone settings.

<!--more-->

（1）Install and open **User Settings Utility** in XrmToolBox

![Open User Settings Utility](images/setUserDefaultTimeZone-01.webp)

（2）Load user information

![Load User Information](images/setUserDefaultTimeZone-02.webp)

（3）Select and check the users, choose the desired time zone, and finally click **Update User Settings**

![Update User Settings](images/setUserDefaultTimeZone-03.webp)

---

Additionally, you can also query the current time zone of users via SQL:

```sql
SELECT s.fullname AS UserName,
       s.businessunitidname AS BusinessUnit,
       s.domainname AS Domain,
       us.timezonecode AS TimeZoneCode,
       tz.standardname AS TimeZoneName
FROM   systemuser AS s
       INNER JOIN
       usersettings AS us
       ON s.systemuserid = us.systemuserid
       INNER JOIN
       timezonedefinition AS tz
       ON us.timezonecode = tz.timezonecode
WHERE  s.isdisabled = 0;
```

![Query User Time Zone via SQL](images/setUserDefaultTimeZone-04.webp)

### SQL Field Description

| # | Field | Description |
| :---: | :--- | :--- |
| 1 | UserName | Full name of the user. |
| 2 | BusinessUnit | The business unit to which the user belongs. |
| 3 | Domain | The user’s domain account (e.g., `contoso\johndoe`). |
| 4 | TimeZoneCode | The numeric code that represents the time zone in Dynamics 365. |
| 5 | TimeZoneName | The standard name of the time zone (e.g., *Pacific Standard Time*). |
