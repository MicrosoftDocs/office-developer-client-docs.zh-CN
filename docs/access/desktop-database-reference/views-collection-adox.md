---
title: Views 集合 (ADOX)
TOCTitle: Views collection (ADOX)
ms:assetid: 8d0f9517-4be1-be9c-d4cd-6d50cd5a8983
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249618(v=office.15)
ms:contentKeyID: 48546246
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 053faa15583809ef7dad0db33de01fa16dd37d44
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930838"
---
# <a name="views-collection-adox"></a>Views 集合 (ADOX)


**适用于**： Access 2013、 Office 2013

包含目录的所有 [View](view-object-adox.md) 对象。

## <a name="remarks"></a>说明

[Views](append-method-adox-views.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新视图。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的视图。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的视图数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除视图。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。

