---
title: View 对象 (ADOX-访问桌面数据库引用)
TOCTitle: View Object (ADOX)
ms:assetid: 3b2e9972-8a0d-eaa3-1c93-ae0665a47f02
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249149(v=office.15)
ms:contentKeyID: 48544280
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ca58dd83ee3d3675a4ca272e1074b8d8cc930391
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468816"
---
# <a name="view-object-adox"></a>View 对象 (ADOX)


**适用于**： Access 2013 |Office 2013

表示经过筛选的记录集或虚拟表。与 ADO [Command](command-object-ado.md) 对象一起使用时， **View** 对象可用于添加、删除或修改视图。

## <a name="remarks"></a>说明

视图是从其他数据库表或视图创建的虚拟表。使用 **View** 对象，无需了解或使用提供程序的"CREATE VIEW"语法，即可创建视图。

使用 **View** 对象的属性和集合，可以执行下列操作：

  - 使用 [Name](name-property-adox.md) 属性标识视图。

  - 使用 **Command** 属性指定可用于添加、删除或修改视图的 ADO [Command](command-property-adox.md) 对象。

  - 使用 [DateCreated](datecreated-property-adox.md) 和 [DateModified](datemodified-property-adox.md) 属性返回日期信息。

