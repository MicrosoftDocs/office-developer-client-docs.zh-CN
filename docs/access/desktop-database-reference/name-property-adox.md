---
title: Name 属性 (ADOX)
TOCTitle: Name Property (ADOX)
ms:assetid: c92a3b2b-6e3f-1ed9-c7be-bf348a0737af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249979(v=office.15)
ms:contentKeyID: 48547674
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 51ea68718c7605df03ed8e4d44d4cb48011649fd
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465805"
---
# <a name="name-property-adox"></a>Name 属性 (ADOX)


**适用于**： Access 2013 |Office 2013

指示对象的名称。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **String** 值。

## <a name="remarks"></a>备注

名称在一个集合中不必是唯一的。

**Name** 属性对于 [Column](column-object-adox.md)、[Group](group-object-adox.md)、[Key](key-object-adox.md)、[Index](index-object-adox.md)、[Table](table-object-adox.md) 以及 [User](user-object-adox.md) 对象是可读写的。 **Name** 属性对于 [Catalog](catalog-object-adox.md)、[Procedure](procedure-object-adox.md) 和 [View](view-object-adox.md) 对象为只读。

对于可读写对象（**Column**、**Group**、**Key**、**Index**, **Table** 以及 **User** 对象），默认值为空字符串 ("")。


> [!NOTE]
> <P>[!注释] 对于键，此属性对于已追加到集合中的 <STRONG>Key</STRONG> 对象为只读。</P>




> [!NOTE]
> <P>[!注释] 对于表，此属性对于已追加到集合中的 <STRONG>Table</STRONG> 对象为只读。</P>


