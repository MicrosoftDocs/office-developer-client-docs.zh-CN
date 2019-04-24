---
title: Append 方法（ADOX 表）
TOCTitle: Append method (ADOX Tables)
ms:assetid: 9e9fd57c-a856-6179-013f-9f378c3b7df0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249726(v=office.15)
ms:contentKeyID: 48546664
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d2bf2479c2a34291f245783ebaecd75ba31d2ac8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297072"
---
# <a name="append-method-adox-tables"></a>Append 方法（ADOX 表）

**适用于**：Access 2013、Office 2013

将新的 [Table](table-object-adox.md) 对象添加到 [Tables](tables-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*表格*。追加*表格*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Table* | 一个 **Variant** 值，包含对要追加的 **Table** 的引用，或者是要创建并追加的表的名称。|

## <a name="remarks"></a>注解

如果提供程序不支持创建表，则会发生错误。

