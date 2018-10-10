---
title: Columns 集合 (ADOX)
TOCTitle: Columns Collection (ADOX)
ms:assetid: 231645db-70da-9ad1-fb27-02145ce32e66
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249008(v=office.15)
ms:contentKeyID: 48543723
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 13f9a17d7dfcd9e621e4f4b1f1fcc03e88b4d832
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468339"
---
# <a name="columns-collection-adox"></a>Columns 集合 (ADOX)


**适用于**： Access 2013 |Office 2013

包含表、索引或键的所有 [Column](column-object-adox.md) 对象。

## <a name="remarks"></a>说明

[Columns](append-method-adox-columns.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新列。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的列。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的列数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除列。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。


> [!NOTE]
> <P>[!注释] 如果追加到 <STRONG>Tables</STRONG> 集合中的 <STRONG>Table</STRONG> 中没有某个 <A href="index-object-adox.md">Column</A> ，则在将该 <STRONG>Column</STRONG> 追加到 <A href="table-object-adox.md">Index</A> 的 <A href="tables-collection-adox.md">Columns</A> 集合时将发生错误。</P>


