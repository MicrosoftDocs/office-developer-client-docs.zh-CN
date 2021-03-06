---
title: ChildCount 属性 (ADO MD)
TOCTitle: ChildCount property (ADO MD)
ms:assetid: ff1872f0-d5f6-174e-0473-7997a462ca81
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250309(v=office.15)
ms:contentKeyID: 48548956
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4f8e0fc98d7868eb5462bd7d8714e1a8eda1cfcf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296379"
---
# <a name="childcount-property-ado-md"></a>ChildCount 属性 (ADO MD)


**适用于**：Access 2013、Office 2013

指示在层次结构中将当前 [Member](member-object-ado-md.md) 对象作为父级的成员的数量。

## <a name="return-values"></a>返回值

返回一个 **Long** 整数值，并且该值为只读。

## <a name="remarks"></a>注解

使用 **ChildCount** 属性可返回某个 **Member** 大致拥有的子级的数量。通过 **Children** 属性可返回 [Member](children-property-ado-md.md) 的实际子级。

对于 **Position** 对象中的 [Member](position-object-ado-md.md) 对象，返回的最大数值为 65536。如果实际子级数量超过 65536，则返回的值仍为 65536。因此应用程序应将 **ChildCount** 等于 65536 解释为子级数量大于或等于 65536。

对于 **Level** 对象中的 [Member](level-object-ado-md.md) 对象，请使用 [Children](count-property-ado.md) 集合的 ADO 集合 **Count** 属性来确定子级的准确数量。如果集合中的子级数量巨大，则确定子级准确数量的过程可能会很慢。

