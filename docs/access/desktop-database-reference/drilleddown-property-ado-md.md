---
title: DrilledDown 属性 (ADO MD)
TOCTitle: DrilledDown Property (ADO MD)
ms:assetid: 1dfe728f-8da2-1d2b-7361-8689a0b088b4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248972(v=office.15)
ms:contentKeyID: 48543610
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f8d203513ce88998143d3043e76ce6ffb6a64741
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465556"
---
# <a name="drilleddown-property-ado-md"></a>DrilledDown 属性 (ADO MD)


**适用于**： Access 2013 |Office 2013

指示该成员在轴上是否有直接子级。

## <a name="return-values"></a>返回值

返回一个 **Boolean** 值，并且是只读的。如果当前成员在轴上没有子成员，则 **DrilledDown** 返回 **True** 。如果当前成员在轴上有一个或多个子级成员，则 **DrilledDown** 返回 **False** 。

## <a name="remarks"></a>说明

使用 **DrilledDown** 属性可确定此成员在轴上是否至少有一个直接子成员。此信息在显示成员时很有用。

此属性仅在 [Position](member-object-ado-md.md) 对象所属的 [Member](position-object-ado-md.md) 对象上受支持。从 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象引用此属性时，会发生错误。

