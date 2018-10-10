---
title: Type 属性 (ADO)
TOCTitle: Type Property (ADO)
ms:assetid: 14d99172-2145-05ae-620b-459ba097f05c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248914(v=office.15)
ms:contentKeyID: 48543397
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2ac119b9582634e619455870c8a2e115f5e8dafa
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466432"
---
# <a name="type-property-ado"></a><span data-ttu-id="ae9cc-102">Type 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="ae9cc-102">Type Property (ADO)</span></span>


<span data-ttu-id="ae9cc-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ae9cc-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ae9cc-104">指示 [Parameter](parameter-object-ado.md)、[Field](field-object-ado.md) 或 [Property](property-object-ado.md) 对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="ae9cc-104">Indicates the operational type or data type of a [Parameter](parameter-object-ado.md), [Field](field-object-ado.md), or [Property](property-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="ae9cc-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="ae9cc-105">Settings and Return Values</span></span>

<span data-ttu-id="ae9cc-106">设置或返回一个 [DataTypeEnum](datatypeenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="ae9cc-106">Sets or returns a [DataTypeEnum](datatypeenum.md) value.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae9cc-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae9cc-107">Remarks</span></span>

<span data-ttu-id="ae9cc-p101">对于 **Parameter** 对象， **Type** 属性为可读/写属性。对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合中的新 [Field](record-object-ado.md) 对象，仅在指定了 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序通过调用 **Fields** 集合的 **Update** 方法成功添加了新的 [Field](update-method-ado.md) 后， **Type** 才为可读/写。</span><span class="sxs-lookup"><span data-stu-id="ae9cc-p101">For **Parameter** objects, the **Type** property is read/write. For new **Field** objects that have been appended to the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md), **Type** is read/write only after the [Value](value-property-ado.md) property for the **Field** has been specified and the data provider has successfully added the new **Field** by calling the [Update](update-method-ado.md) method of the **Fields** collection.</span></span>

<span data-ttu-id="ae9cc-110">对于所有其他对象， **Type** 属性为只读属性。</span><span class="sxs-lookup"><span data-stu-id="ae9cc-110">For all other objects, the **Type** property is read-only.</span></span>

