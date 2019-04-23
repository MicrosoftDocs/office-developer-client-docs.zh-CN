---
title: ActualSize 属性 (ADO)
TOCTitle: ActualSize property (ADO)
ms:assetid: 020a414d-e6aa-5fb9-9b77-bd9d10124f8a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248787(v=office.15)
ms:contentKeyID: 48542949
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c13cb41299ddaf786e6412e43a50b1414ad818b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280430"
---
# <a name="actualsize-property-ado"></a><span data-ttu-id="b9cb8-102">ActualSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b9cb8-102">ActualSize property (ADO)</span></span>

<span data-ttu-id="b9cb8-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b9cb8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b9cb8-104">指示字段值的实际长度。</span><span class="sxs-lookup"><span data-stu-id="b9cb8-104">Indicates the actual length of a field's value.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="b9cb8-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="b9cb8-105">Settings and return values</span></span>

<span data-ttu-id="b9cb8-p101">返回 **Long** 值。某些提供程序可能允许设置此属性来为 BLOB 数据保留空间，此时的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="b9cb8-p101">Returns a **Long** value. Some providers may allow this property to be set to reserve space for BLOB data, in which case the default value is 0.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9cb8-108">注解</span><span class="sxs-lookup"><span data-stu-id="b9cb8-108">Remarks</span></span>

<span data-ttu-id="b9cb8-p102">使用 **ActualSize** 属性可以返回 [Field](field-object-ado.md) 对象值的实际长度。对于所有字段，**ActualSize** 属性都是只读的。如果 ADO 无法确定 **Field** 对象值的长度，**ActualSize** 属性将返回 **adUnknown**。</span><span class="sxs-lookup"><span data-stu-id="b9cb8-p102">Use the **ActualSize** property to return the actual length of a [Field](field-object-ado.md) object's value. For all fields, the **ActualSize** property is read-only. If ADO cannot determine the length of the **Field** object's value, the **ActualSize** property returns **adUnknown**.</span></span>

<span data-ttu-id="b9cb8-112">**ActualSize**和[DefinedSize](definedsize-property-ado.md)属性不同。</span><span class="sxs-lookup"><span data-stu-id="b9cb8-112">The **ActualSize** and [DefinedSize](definedsize-property-ado.md) properties are different.</span></span> <span data-ttu-id="b9cb8-113">声明的类型为 **adVarChar** 且最大长度为 50 个字符的 **Field** 对象返回的 **DefinedSize** 属性值为 50，但其返回的 **ActualSize** 属性值为存储在当前记录的字段中的数据的长度。</span><span class="sxs-lookup"><span data-stu-id="b9cb8-113">A **Field** object with a declared type of **adVarChar** and a maximum length of 50 characters returns a **DefinedSize** property value of 50, but the **ActualSize** property value it returns is the length of the data stored in the field for the current record.</span></span> <span data-ttu-id="b9cb8-114">**DefinedSize** 大于 255 个字节的 **Fields** 将作为可变长度列处理。</span><span class="sxs-lookup"><span data-stu-id="b9cb8-114">**Fields** with a **DefinedSize** greater than 255 bytes are treated as variable length columns.</span></span>

