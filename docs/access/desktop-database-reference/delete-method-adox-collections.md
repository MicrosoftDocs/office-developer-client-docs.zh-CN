---
title: Delete 方法（ADOX 集合）
TOCTitle: Delete Method (ADOX Collections)
ms:assetid: bcf9b8dd-cc7a-c1f9-fd93-58694766c4d9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249909(v=office.15)
ms:contentKeyID: 48547423
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ea02f02270649783873f1f086bb9f39b804034a2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468453"
---
# <a name="delete-method-adox-collections"></a>Delete 方法（ADOX 集合）


**适用于**： Access 2013 |Office 2013



从集合中移除对象。

## <a name="syntax"></a>语法

*集合*。删除*名称*

## <a name="parameters"></a>参数

  - *Name*

  - 一个 **Variant** 值，指定要删除的对象的名称或顺序位置（索引）。

## <a name="remarks"></a>备注

如果*名称*不存在集合中，将发生错误。

对于 [Tables](tables-collection-adox.md) 和 [Users](users-collection-adox.md) 集合，如果提供程序不支持删除表或用户，则会发生错误。对于 [Procedures](procedures-collection-adox.md) 和 [Views](views-collection-adox.md) 集合，如果提供程序不支持保留命令，则 **Delete** 将失败。

