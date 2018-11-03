---
title: Delete 方法 （ADOX 集合）
TOCTitle: Delete method (ADOX Collections)
ms:assetid: bcf9b8dd-cc7a-c1f9-fd93-58694766c4d9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249909(v=office.15)
ms:contentKeyID: 48547423
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6a429c18890125f1c047c6356d250713ea5ea817
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944898"
---
# <a name="delete-method-adox-collections"></a>Delete 方法 （ADOX 集合）


**适用于**： Access 2013、 Office 2013



从集合中移除对象。

## <a name="syntax"></a>语法

*集合*。删除*名称*

## <a name="parameters"></a>参数

- *Name*

  - 一个 **Variant** 值，指定要删除的对象的名称或顺序位置（索引）。

## <a name="remarks"></a>备注

如果*名称*不存在集合中，将发生错误。

对于 [Tables](tables-collection-adox.md) 和 [Users](users-collection-adox.md) 集合，如果提供程序不支持删除表或用户，则会发生错误。对于 [Procedures](procedures-collection-adox.md) 和 [Views](views-collection-adox.md) 集合，如果提供程序不支持保留命令，则 **Delete** 将失败。

