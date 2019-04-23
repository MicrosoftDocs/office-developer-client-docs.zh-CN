---
title: Parent 属性 (ADO MD)
TOCTitle: Parent property (ADO MD)
ms:assetid: 62649da7-d35f-f11f-674c-28ce95abaf20
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249370(v=office.15)
ms:contentKeyID: 48545238
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e0c0eef638cb76676cd2287a34c0e4b17bd89c4d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287788"
---
# <a name="parent-property-ado-md"></a>Parent 属性 (ADO MD)


**适用于**：Access 2013、Office 2013

指示层次结构中作为当前成员的父级的成员。

## <a name="return-values"></a>返回值

返回一个 [Member](member-object-ado-md.md) 对象，并且该值为只读。

## <a name="remarks"></a>注解

位于层次结构顶级（根）的成员没有父级。此属性仅在 [Level](level-object-ado-md.md) 对象所属的 **Member** 对象上受支持。通过属于 [Position](position-object-ado-md.md) 对象的 **Member** 对象引用此属性时，会发生错误。

