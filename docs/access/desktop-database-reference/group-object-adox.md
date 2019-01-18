---
title: Group 对象 (ADOX)
TOCTitle: Group object (ADOX)
ms:assetid: 91cf1b87-c928-1d89-2731-138f6299cc60
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249642(v=office.15)
ms:contentKeyID: 48546359
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e010ac58ff0b573d42c562ce3be7a99acab5abea
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718166"
---
# <a name="group-object-adox"></a>Group 对象 (ADOX)


**适用于**： Access 2013、 Office 2013

代表在受保护的数据库中有访问权限的组帐户。

## <a name="remarks"></a>说明

[Catalog](groups-collection-adox.md) 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。

使用 **Group** 对象的属性、集合和方法，可以执行下列操作：

  - 使用 [Name](name-property-adox.md) 属性标识组。

  - 使用 [GetPermissions](getpermissions-method-adox.md) 和 [SetPermissions](setpermissions-method-adox.md) 方法确定组是否具有读取、写入或删除权限。

  - 使用 [Users](users-collection-adox.md) 集合访问在组中具有成员资格的用户帐户。

  - 使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的属性。

