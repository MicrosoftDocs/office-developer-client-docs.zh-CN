---
title: Property 对象 (ADO)
TOCTitle: Property Object (ADO)
ms:assetid: eec318fd-f5ed-d9ef-9830-848439a8914d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250210(v=office.15)
ms:contentKeyID: 48548567
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5b3cb4d5caedb6e73bf0819639c1feac12b9d3a8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465940"
---
# <a name="property-object-ado"></a>Property 对象 (ADO)


**适用于**： Access 2013 |Office 2013

表示提供程序所定义的 ADO 对象的动态特征。

## <a name="remarks"></a>说明

ADO 对象有两种类型的属性：内置和动态。

内置属性是这些属性在 ADO 中实现并且立即可用到任何新的对象，使用语法。 内置属性不会作为 **Property** 对象出现在对象的 [Properties](properties-collection-ado.md) 集合中，因此，尽管可以更改属性值，但不能修改属性的特征。

动态属性是由基础数据提供程序定义的，它们出现在相应的 ADO 对象的 **Properties** 集合中。 例如，特定于提供程序的属性可以指示 [Recordset](recordset-object-ado.md) 对象是否支持事务或更新。 这些额外的属性将作为 **Property** 对象出现在 **Recordset** 对象的 **Properties** 集合中。 动态属性可以仅通过集合，并使用 MyObject.Properties(0) 引用或 MyObject.Properties("Name") 语法。

这两种属性都是不可删除的。

动态 **Property** 对象有四个它自己的内置属性：

  - [Name](name-property-ado.md) 属性是用于标识该属性的字符串。

  - [Type](type-property-ado.md) 属性是用于指定属性数据类型的整数。

  - [Value](value-property-ado.md) 属性是包含属性设置的变量型。 **Value** 是 **Property** 对象的默认属性。

  - [Attributes](attributes-property-ado.md) 属性是长值，用于指示特定于提供程序的属性的特征。

