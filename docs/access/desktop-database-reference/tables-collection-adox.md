---
title: Tables 集合 (ADOX)
TOCTitle: Tables collection (ADOX)
ms:assetid: 07bc0541-c528-1c25-c8c4-05736836eda3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248821(v=office.15)
ms:contentKeyID: 48543082
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e53cd4b6d4a61a226103eb443bac7f3b4f92d908
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314047"
---
# <a name="tables-collection-adox"></a>Tables 集合 (ADOX)


**适用于**：Access 2013、Office 2013

包含目录的所有 [Table](table-object-adox.md) 对象。

## <a name="remarks"></a>注解

**Tables** 集合的 [Append](append-method-adox-tables.md) 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新表。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的表。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的表数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除表。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。

某些提供程序可能返回 Tables 集合中的其他架构对象，例如视图。因此，一些 ADOX 集合可能包含对同一对象的引用。如果您删除一个集合中的对象，则另一个引用被删除对象的集合在调用 Refresh 方法之前，将不会反映所做的更改。例如，使用 OLE DB Provider for Microsoft Jet 时，随 Tables 集合返回视图。如果删除视图，则必须刷新 Tables 集合，该集合才会反映所做的更改。

