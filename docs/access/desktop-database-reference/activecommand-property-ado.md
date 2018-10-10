---
title: ActiveCommand 属性 (ADO)
TOCTitle: ActiveCommand Property (ADO)
ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15)
ms:contentKeyID: 48544459
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f01ae4c821d8beb6c8de84c7ed671a373d7372c9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468399"
---
# <a name="activecommand-property-ado"></a>ActiveCommand 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示创建关联的 [Recordset](command-object-ado.md) 对象的 [Command](recordset-object-ado.md) 对象。

## <a name="return-value"></a>返回值

返回一个包含 **Command** 对象的 **Variant** 。默认值为一个空对象引用。

## <a name="remarks"></a>备注

**ActiveCommand** 为只读属性。

如果未使用 **Command** 对象创建当前的 **Recordset** ，则会返回一个 **Null** 对象引用。

当仅给定了生成的 **Recordset** 对象时，可以使用此属性来查找关联的 **Command** 对象。

