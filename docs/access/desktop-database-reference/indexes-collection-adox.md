---
title: 索引集合 (ADOX)
TOCTitle: Indexes collection (ADOX)
ms:assetid: ab04bdd1-7c4a-44cb-dfc6-add3a52f502f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249793(v=office.15)
ms:contentKeyID: 48546963
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6eac0d1b73e0380f582ce0bc69cdb358c67d185e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291578"
---
# <a name="indexes-collection-adox"></a>索引集合 (ADOX)


**适用于**：Access 2013、Office 2013

包含表的所有 [Index](index-object-adox.md) 对象。

## <a name="remarks"></a>注解

[Indexes](append-method-adox-indexes.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新索引。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的索引。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的索引数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除索引。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。

