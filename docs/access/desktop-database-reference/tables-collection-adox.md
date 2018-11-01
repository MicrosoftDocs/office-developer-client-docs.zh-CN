---
title: Tables 集合 (ADOX)
TOCTitle: Tables Collection (ADOX)
ms:assetid: 07bc0541-c528-1c25-c8c4-05736836eda3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248821(v=office.15)
ms:contentKeyID: 48543082
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e59de5fc777d08f12b1030812a6260378924f286
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869265"
---
# <a name="tables-collection-adox"></a>Tables 集合 (ADOX)


**适用于**： Access 2013、 Office 2013

包含目录的所有 [Table](table-object-adox.md) 对象。

## <a name="remarks"></a>说明

[Tables](append-method-adox-tables.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新表。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的表。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的表数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除表。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。

某些提供程序可能返回 Tables 集合中的其他架构对象，例如视图。因此，一些 ADOX 集合可能包含对同一对象的引用。如果您删除一个集合中的对象，则另一个引用被删除对象的集合在调用 Refresh 方法之前，将不会反映所做的更改。例如，使用 OLE DB Provider for Microsoft Jet 时，随 Tables 集合返回视图。如果删除视图，则必须刷新 Tables 集合，该集合才会反映所做的更改。

