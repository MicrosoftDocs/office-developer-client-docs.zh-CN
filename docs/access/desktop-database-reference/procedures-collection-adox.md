---
title: Procedures 集合 (ADOX)
TOCTitle: Procedures collection (ADOX)
ms:assetid: e1ca53ad-1213-b514-e015-e18c2ab15e23
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250150(v=office.15)
ms:contentKeyID: 48548267
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd426f25567dee3eb7e43e46b341ac503e558f1f
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919113"
---
# <a name="procedures-collection-adox"></a>Procedures 集合 (ADOX)


**适用于**： Access 2013、 Office 2013

包含目录的所有 [Procedure](procedure-object-adox.md) 对象。

## <a name="remarks"></a>说明

[Procedures](append-method-adox-procedures.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新过程。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的过程。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的过程数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除过程。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。

