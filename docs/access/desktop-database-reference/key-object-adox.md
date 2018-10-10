---
title: Key 对象 (ADOX-访问桌面数据库引用)
TOCTitle: Key Object (ADOX)
ms:assetid: 727198ec-57d2-7766-790c-370beb931de6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249461(v=office.15)
ms:contentKeyID: 48545608
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c77e45f52994f14d79acf424da14b55b2cdd9814
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25469031"
---
# <a name="key-object-adox"></a>Key 对象 (ADOX)


**适用于**： Access 2013 |Office 2013

表示数据库表中的主键、外键或唯一键字段。

## <a name="remarks"></a>说明

以下代码创建一个新的 **Key** ：

`Dim obj As New Key`

使用 **Key** 对象的属性和集合，可以执行下列操作：

- 使用 [Name](name-property-adox.md) 属性标识键。

- 使用 [Type](https://msdn.microsoft.com/library/jj248879\(v=office.15\)) 属性确定键是主键、外键还是唯一键。

- 使用 [Columns](columns-collection-adox.md) 集合访问键的数据库列。

- 使用 [RelatedTable](relatedtable-property-adox.md) 属性指定相关表的名称。

- 使用 [DeleteRule](deleterule-property-adox.md) 和 [UpdateRule](updaterule-property-adox.md) 属性确定在删除或更新主键时执行的操作。

