---
title: ActiveCommand 属性 (ADO)
TOCTitle: ActiveCommand property (ADO)
ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15)
ms:contentKeyID: 48544459
ms.date: 10/17/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 18fa38176f7174f27b46604c6182dfbdaa422f06
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281927"
---
# <a name="activecommand-property-ado"></a>ActiveCommand 属性 (ADO)

**适用于**：Access 2013、Office 2013

指示创建关联的 [Recordset](command-object-ado.md) 对象的 [Command](recordset-object-ado.md) 对象。

## <a name="return-value"></a>返回值

返回一个包含 **Command** 对象的 **Variant** 。 默认值为一个空对象引用。

## <a name="remarks"></a>注解

**ActiveCommand** 为只读属性。

如果未使用**Command**对象创建当前的**Recordset**, 则返回一个**Null**对象引用。

当仅给定了生成的 **Recordset** 对象时，可以使用此属性来查找关联的 **Command** 对象。

