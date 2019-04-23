---
title: Name 属性 (ADOX)
TOCTitle: Name property (ADOX)
ms:assetid: c92a3b2b-6e3f-1ed9-c7be-bf348a0737af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249979(v=office.15)
ms:contentKeyID: 48547674
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5c7021c6f97d1aaa9c82e65eab98a3259d6eb87e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288649"
---
# <a name="name-property-adox"></a>Name 属性 (ADOX)

**适用于**：Access 2013、Office 2013

指示对象的名称。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **String** 值。

## <a name="remarks"></a>注解

名称在一个集合中不必是唯一的。

**Name** 属性对于 [Column](column-object-adox.md)、[Group](group-object-adox.md)、[Key](key-object-adox.md)、[Index](index-object-adox.md)、[Table](table-object-adox.md) 以及 [User](user-object-adox.md) 对象是可读写的。 **Name** 属性对于 [Catalog](catalog-object-adox.md)、[Procedure](procedure-object-adox.md) 和 [View](view-object-adox.md) 对象为只读。

对于可读写对象（**Column**、**Group**、**Key**、**Index**, **Table** 以及 **User** 对象），默认值为空字符串 ("")。

> [!NOTE]
> - 对于键，此属性对于已追加到集合中的 **Key** 对象为只读。
> - [!注释] 对于表，此属性对于已追加到集合中的 **Table** 对象为只读。


