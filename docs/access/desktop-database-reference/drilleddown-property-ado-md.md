---
title: DrilledDown 属性 (ADO MD)
TOCTitle: DrilledDown property (ADO MD)
ms:assetid: 1dfe728f-8da2-1d2b-7361-8689a0b088b4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248972(v=office.15)
ms:contentKeyID: 48543610
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 40a97c7f755f681169c77c3a2077ee41d9cdc980
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712447"
---
# <a name="drilleddown-property-ado-md"></a>DrilledDown 属性 (ADO MD)


**适用于**： Access 2013、 Office 2013

指示该成员在轴上是否有直接子级。

## <a name="return-values"></a>返回值

返回一个 **Boolean** 值，并且是只读的。如果当前成员在轴上没有子成员，则 **DrilledDown** 返回 **True** 。如果当前成员在轴上有一个或多个子级成员，则 **DrilledDown** 返回 **False** 。

## <a name="remarks"></a>说明

使用 **DrilledDown** 属性可确定此成员在轴上是否至少有一个直接子成员。此信息在显示成员时很有用。

此属性仅在 [Position](member-object-ado-md.md) 对象所属的 [Member](position-object-ado-md.md) 对象上受支持。从 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象引用此属性时，会发生错误。

