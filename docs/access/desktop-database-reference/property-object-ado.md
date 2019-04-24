---
title: Property 对象 (ADO)
TOCTitle: Property object (ADO)
ms:assetid: eec318fd-f5ed-d9ef-9830-848439a8914d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250210(v=office.15)
ms:contentKeyID: 48548567
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 262f4873359508a985b27f3d4ea70a5fcbfd620f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302917"
---
# <a name="property-object-ado"></a>Property 对象 (ADO)


**适用于**：Access 2013、Office 2013

表示提供程序所定义的 ADO 对象的动态特征。

## <a name="remarks"></a>注解

ADO 对象有两种类型的属性：内置和动态。

内置属性是在 ADO 中实现的这些属性, 可立即用于任何新对象 (使用语法)。 内置属性不会作为 **Property** 对象出现在对象的 [Properties](properties-collection-ado.md) 集合中，因此，尽管可以更改属性值，但不能修改属性的特征。

动态属性是由基础数据提供程序定义的，它们出现在相应的 ADO 对象的 **Properties** 集合中。 例如，特定于提供程序的属性可以指示 [Recordset](recordset-object-ado.md) 对象是否支持事务或更新。 这些额外的属性将作为 **Property** 对象出现在 **Recordset** 对象的 **Properties** 集合中。 只能通过集合 (使用 MyObject (0) 或 or MyObject ("Name") 语法来引用动态属性。

这两种属性都是不可删除的。

动态 **Property** 对象有四个它自己的内置属性：

  - [Name](name-property-ado.md) 属性是用于标识该属性的字符串。

  - [Type](type-property-ado.md) 属性是用于指定属性数据类型的整数。

  - [Value](value-property-ado.md) 属性是包含属性设置的变量型。 **Value** 是 **Property** 对象的默认属性。

  - [Attributes](attributes-property-ado.md) 属性是长值，用于指示特定于提供程序的属性的特征。

