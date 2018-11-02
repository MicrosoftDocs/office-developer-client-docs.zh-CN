---
title: Indexes 集合 (ADOX)
TOCTitle: Indexes collection (ADOX)
ms:assetid: ab04bdd1-7c4a-44cb-dfc6-add3a52f502f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249793(v=office.15)
ms:contentKeyID: 48546963
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7d40736d30b0ebb62796b7cd2d0f8b4ede9e964c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930649"
---
# <a name="indexes-collection-adox"></a>Indexes 集合 (ADOX)


**适用于**： Access 2013、 Office 2013

包含表的所有 [Index](index-object-adox.md) 对象。

## <a name="remarks"></a>说明

[Indexes](append-method-adox-indexes.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新索引。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的索引。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的索引数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除索引。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。

