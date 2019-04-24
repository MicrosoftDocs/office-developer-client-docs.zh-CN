---
title: View 对象 (ADOX-Access 桌面数据库参考)
TOCTitle: View object (ADOX)
ms:assetid: 3b2e9972-8a0d-eaa3-1c93-ae0665a47f02
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249149(v=office.15)
ms:contentKeyID: 48544280
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b3b5d25a727233b5fda5627df8dff952003bbfe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306046"
---
# <a name="view-object-adox"></a>View 对象 (ADOX)


**适用于**：Access 2013、Office 2013

表示经过筛选的记录集或虚拟表。与 ADO [Command](command-object-ado.md) 对象一起使用时，**View** 对象可用于添加、删除或修改视图。

## <a name="remarks"></a>注解

视图是从其他数据库表或视图创建的虚拟表。使用 **View** 对象，无需了解或使用提供程序的“CREATE VIEW”语法，即可创建视图。

使用 **View** 对象的属性和集合，可以执行下列操作：

  - 使用 [Name](name-property-adox.md) 属性标识视图。

  - 使用 [Command](command-property-adox.md) 属性指定可用于添加、删除或修改视图的 ADO **Command** 对象。

  - 使用 [DateCreated](datecreated-property-adox.md) 和 [DateModified](datemodified-property-adox.md) 属性返回日期信息。

