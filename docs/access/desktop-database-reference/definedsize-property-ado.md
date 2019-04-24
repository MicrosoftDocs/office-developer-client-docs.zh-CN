---
title: DefinedSize 属性 (ADO)
TOCTitle: DefinedSize property (ADO)
ms:assetid: 8d6db4c9-fbdc-9fcd-63f0-bd677c5ebcf6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249619(v=office.15)
ms:contentKeyID: 48546257
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 121e81734fc5ecc0a761dae53942f1cbed98df2a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294132"
---
# <a name="definedsize-property-ado"></a><span data-ttu-id="54442-102">DefinedSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="54442-102">DefinedSize property (ADO)</span></span>


<span data-ttu-id="54442-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="54442-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="54442-104">指示 [Field](field-object-ado.md) 对象的数据容量。</span><span class="sxs-lookup"><span data-stu-id="54442-104">Indicates the data capacity of a [Field](field-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="54442-105">返回值</span><span class="sxs-lookup"><span data-stu-id="54442-105">Return value</span></span>

<span data-ttu-id="54442-106">返回一个 **Long** 值，该值以字节数反映字段的定义大小。</span><span class="sxs-lookup"><span data-stu-id="54442-106">Returns a **Long** value that reflects the defined size of a field as a number of bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="54442-107">注解</span><span class="sxs-lookup"><span data-stu-id="54442-107">Remarks</span></span>

<span data-ttu-id="54442-108">使用 **DefinedSize** 属性可以确定 **Field** 对象的数据容量。</span><span class="sxs-lookup"><span data-stu-id="54442-108">Use the **DefinedSize** property to determine the data capacity of a **Field** object.</span></span>

<span data-ttu-id="54442-p101">**DefinedSize** 和 [ActualSize](actualsize-property-ado.md) 属性不同。例如，假如声明类型为 **adVarChar** 且 **DefinedSize** 属性值为 50 的 **Field** 对象中只包含了一个字符。其返回的 **ActualSize** 属性值为单个字符所占的字节长度。</span><span class="sxs-lookup"><span data-stu-id="54442-p101">The **DefinedSize** and [ActualSize](actualsize-property-ado.md) properties are different. For example, consider a **Field** object with a declared type of **adVarChar** and a **DefinedSize** property value of 50, containing a single character. The **ActualSize** property value it returns is the length in bytes of the single character.</span></span>

