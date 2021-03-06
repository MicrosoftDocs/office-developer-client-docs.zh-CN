---
title: Count 属性 (ADO)
TOCTitle: Count property (ADO)
ms:assetid: b59f9581-ffd1-471d-44fa-3c1bb812e140
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249871(v=office.15)
ms:contentKeyID: 48547253
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e2a341a82e5cdc9ed5a55ca9f4b80ba80c6875bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295469"
---
# <a name="count-property-ado"></a>Count 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示集合中的对象数。

## <a name="return-value"></a>返回值

返回 **Long** 值。

## <a name="remarks"></a>注解

使用 **Count** 属性可确定在给定集合中有多少个对象。

由于集合中的成员是从零开始进行编号的，因此应始终将循环编写为从第零个成员开始，而在 **Count** 属性的值减 1 处终止。如果在使用 Microsoft Visual Basic，而希望在不检查 **Count** 属性的情况下遍历集合的成员，则请使用 **For** **Each...Next** 命令。

如果 **Count** 属性为零，则表明集合中没有对象。

