---
title: Keys 集合 (ADOX)
TOCTitle: Keys Collection (ADOX)
ms:assetid: 0d480c01-1b36-28b9-9135-51958f313995
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248854(v=office.15)
ms:contentKeyID: 48543215
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 837a81058a7d5ba871069a5d8534e870194ba92f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465927"
---
# <a name="keys-collection-adox"></a>Keys 集合 (ADOX)


**适用于**： Access 2013 |Office 2013

包含表的所有 [Key](key-object-adox.md) 对象。

## <a name="remarks"></a>说明

[Keys](append-method-adox-keys.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新的键。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的键。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的键数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除键。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。

