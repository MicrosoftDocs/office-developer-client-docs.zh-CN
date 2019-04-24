---
title: User 对象 (ADOX-Access 桌面数据库参考)
TOCTitle: User object (ADOX)
ms:assetid: e88b9a8a-e70f-c7ca-cb8c-bd274ff24948
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250178(v=office.15)
ms:contentKeyID: 48548426
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3299a6c0742e7fcbbd26532f3522fdc96b7956b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32313158"
---
# <a name="user-object-adox"></a>User 对象 (ADOX)


**适用于**：Access 2013、Office 2013

代表在受保护的数据库中有访问权限的用户帐户。

## <a name="remarks"></a>注解

[Catalog](catalog-object-adox.md) 的 [Users](users-collection-adox.md) 集合表示该目录的所有用户。[Group](group-object-adox.md) 的 **Users** 集合仅表示特定组的用户。

使用 **User** 对象的属性、集合和方法，可以执行下列操作：

  - 使用 [Name](name-property-adox.md) 属性标识用户。

  - 使用 [ChangePassword](changepassword-method-adox.md) 方法更改用户的密码。

  - 使用 [GetPermissions](getpermissions-method-adox.md) 和 [SetPermissions](setpermissions-method-adox.md) 方法确定用户是否具有读取、写入或删除权限。

  - 使用 [Groups](groups-collection-adox.md) 集合访问用户所属的组。

  - 使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的属性。

