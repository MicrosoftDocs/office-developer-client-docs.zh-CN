---
title: LevelDepth 属性 (ADO MD)
TOCTitle: LevelDepth property (ADO MD)
ms:assetid: ba680f1e-2731-ad6b-4cee-cd3d8d114788
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249894(v=office.15)
ms:contentKeyID: 48547366
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 664a21f8b642c8db27580993089268e5d7b6f4ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290004"
---
# <a name="leveldepth-property-ado-md"></a>LevelDepth 属性 (ADO MD)


**适用于**：Access 2013、Office 2013

指示层次结构的根和某个成员之间的级数。

## <a name="return-values"></a>返回值

返回一个 **Long** 整数值，并且该值为只读。

## <a name="remarks"></a>注解

使用 **LevelDepth** 属性可确定 [Member](member-object-ado-md.md) 对象与层次结构的根级别之间的距离。根级别的成员的 **LevelDepth** 为 0。该属性对应于 [Level](level-object-ado-md.md) 对象的 [Depth](depth-property-ado-md.md) 属性。

