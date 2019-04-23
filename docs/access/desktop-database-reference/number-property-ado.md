---
title: Number 属性 (ADO)
TOCTitle: Number property (ADO)
ms:assetid: b5103af5-356b-ec74-cd62-86e59467d491
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249868(v=office.15)
ms:contentKeyID: 48547243
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b5eb46d6fbeb677e6d0fe73223d74ae2ea42d368
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288572"
---
# <a name="number-property-ado"></a>Number 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示用于唯一标识 [Error](error-object-ado.md) 对象的编号。

## <a name="return-value"></a>返回值

返回一个 **Long** 值，该值与 [ErrorValueEnum](errorvalueenum.md) 中的一个常量对应。

## <a name="remarks"></a>注解

使用 **Number** 属性可确定发生了哪种错误。此属性的值是与错误条件对应的唯一数字。

[Errors](errors-collection-ado.md) 集合返回一个 HRESULT，格式为十六进制（例如，0x80004005）或长整型值（例如，2147467259）。这些 HRESULT 可由基础组件引发，如 OLE DB，甚至 OLE 本身。有关这些编号的详细信息，请参阅 *《OLE DB 程序员参考》* 中的第 16 章。

