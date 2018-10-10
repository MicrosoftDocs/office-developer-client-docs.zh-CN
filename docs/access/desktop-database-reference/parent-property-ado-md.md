---
title: Parent 属性 (ADO MD)
TOCTitle: Parent Property (ADO MD)
ms:assetid: 62649da7-d35f-f11f-674c-28ce95abaf20
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249370(v=office.15)
ms:contentKeyID: 48545238
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: eb1606a745cb8572f54b253bdbbbbbb461cfc74a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466761"
---
# <a name="parent-property-ado-md"></a>Parent 属性 (ADO MD)


**适用于**： Access 2013 |Office 2013

指示层次结构中作为当前成员的父级的成员。

## <a name="return-values"></a>返回值

返回一个 [Member](member-object-ado-md.md) 对象，并且该值为只读。

## <a name="remarks"></a>说明

位于层次结构顶级（根）的成员没有父级。此属性仅在 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。通过属于 **Position** 对象的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。

