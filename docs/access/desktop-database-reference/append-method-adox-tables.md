---
title: Append 方法（ADOX 表）
TOCTitle: Append method (ADOX Tables)
ms:assetid: 9e9fd57c-a856-6179-013f-9f378c3b7df0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249726(v=office.15)
ms:contentKeyID: 48546664
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8e43f8fe5537ded015b5b8d79bb32f811e73368c
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949346"
---
# <a name="append-method-adox-tables"></a>Append 方法（ADOX 表）

**适用于**： Access 2013、 Office 2013

将新的 [Table](table-object-adox.md) 对象添加到 [Tables](tables-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*表*。追加*表*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Table* | 一个 **Variant** 值，包含对要追加的 **Table** 的引用，或者是要创建并追加的表的名称。|

## <a name="remarks"></a>说明

如果提供程序不支持创建表，则会发生错误。

