---
title: 子属性 (ADO MD)
TOCTitle: Children property (ADO MD)
ms:assetid: 66eff203-68e5-a36d-eb2f-2e9faa80deb6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249400(v=office.15)
ms:contentKeyID: 48545352
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 27d69e760b65a917270b0851743c108692c601e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296365"
---
# <a name="children-property-ado-md"></a>子属性 (ADO MD)


**适用于**：Access 2013、Office 2013

返回层次结构中将当前 [Member](members-collection-ado-md.md) 作为父级的 [Members](member-object-ado-md.md) 集合。

## <a name="return-values"></a>返回值

返回一个 **Members** 集合，并且该值为只读。

## <a name="remarks"></a>注解

**Children** 属性包含将当前 **Member** 作为层次结构父级的 **Members** 集合。叶级 **Member** 对象在该 **Members** 集合中没有子成员。此属性仅在属于 [Level](level-object-ado-md.md) 对象的 **Member** 对象上受支持。通过属于 [Position](position-object-ado-md.md) 对象的 **Member** 对象引用此属性时，会发生错误。

