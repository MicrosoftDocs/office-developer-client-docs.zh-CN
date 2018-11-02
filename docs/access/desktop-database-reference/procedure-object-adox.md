---
title: Procedure 对象 (ADOX)
TOCTitle: Procedure object (ADOX)
ms:assetid: d5fcf0fe-f59f-e114-dc11-515f11c2a2c1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250076(v=office.15)
ms:contentKeyID: 48547972
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 72f0475aeca38b5c6ba6cd2954ff894f00fb6f7f
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922648"
---
# <a name="procedure-object-adox"></a>Procedure 对象 (ADOX)


**适用于**： Access 2013、 Office 2013

代表存储过程。与 ADO [Command](command-object-ado.md) 对象一起使用时， **Procedure** 对象可用于添加、删除或修改存储过程。

## <a name="remarks"></a>说明

使用 **Procedure** 对象，无需了解或使用提供程序的"CREATE PROCEDURE"语法，即可创建存储过程。

使用 **Procedure** 对象的属性和集合，可以执行下列操作：

  - 使用 [Name](name-property-adox.md) 属性标识过程。

  - 使用 **Command** 属性指定可用于创建或执行过程的 ADO [Command](command-property-adox.md) 对象。

  - 使用 [DateCreated](datecreated-property-adox.md) 和 [DateModified](datemodified-property-adox.md) 属性返回日期信息。

