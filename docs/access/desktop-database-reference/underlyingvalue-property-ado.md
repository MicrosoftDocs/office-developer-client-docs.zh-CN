---
title: UnderlyingValue 属性 (ADO)
TOCTitle: UnderlyingValue Property (ADO)
ms:assetid: f84f4c1c-2bd4-a725-3575-ed063ead13c8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250262(v=office.15)
ms:contentKeyID: 48548782
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 10140d0cc4105ed46ddaaf48e4c827f364adc90c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467672"
---
# <a name="underlyingvalue-property-ado"></a><span data-ttu-id="57501-102">UnderlyingValue 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="57501-102">UnderlyingValue Property (ADO)</span></span>


<span data-ttu-id="57501-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="57501-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="57501-104">指示数据库中 [Field](field-object-ado.md) 对象的当前值。</span><span class="sxs-lookup"><span data-stu-id="57501-104">Indicates a [Field](field-object-ado.md) object's current value in the database.</span></span>

## <a name="return-value"></a><span data-ttu-id="57501-105">返回值</span><span class="sxs-lookup"><span data-stu-id="57501-105">Return Value</span></span>

<span data-ttu-id="57501-106">返回一个指示 **Field** 的值的 **Variant** 值。</span><span class="sxs-lookup"><span data-stu-id="57501-106">Returns a **Variant** value that indicates the value of the **Field**.</span></span>

## <a name="remarks"></a><span data-ttu-id="57501-107">备注</span><span class="sxs-lookup"><span data-stu-id="57501-107">Remarks</span></span>

<span data-ttu-id="57501-p101">使用 **UnderlyingValue** 属性可以返回数据库中的当前字段的值。 **UnderlyingValue** 属性中的字段值是事务可见的值，而且可能是其他事务所进行的最近更新的结果。此值可能不同于 [OriginalValue](originalvalue-property-ado.md) 属性，后者反映的是最初返回到 [Recordset](recordset-object-ado.md) 的值。</span><span class="sxs-lookup"><span data-stu-id="57501-p101">Use the **UnderlyingValue** property to return the current field value from the database. The field value in the **UnderlyingValue** property is the value that is visible to your transaction and may be the result of a recent update by another transaction. This may differ from the [OriginalValue](originalvalue-property-ado.md) property, which reflects the value that was originally returned to the [Recordset](recordset-object-ado.md).</span></span>

<span data-ttu-id="57501-p102">这类似于使用 [Resync](resync-method-ado.md) 方法，但是 **UnderlyingValue** 属性仅返回当前记录中的特定字段的值。该值与 [Resync](resync-method-ado.md) 方法用于替换 [Value](value-property-ado.md) 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="57501-p102">This is similar to using the [Resync](resync-method-ado.md) method, but the **UnderlyingValue** property returns only the value for a specific field from the current record. This is the same value that the [Resync](resync-method-ado.md) method uses to replace the [Value](value-property-ado.md) property.</span></span>

<span data-ttu-id="57501-113">将此属性与 **OriginalValue** 属性结合使用时，可以解决因批更新而引发的冲突。</span><span class="sxs-lookup"><span data-stu-id="57501-113">When you use this property with the **OriginalValue** property, you can resolve conflicts that arise from batch updates.</span></span>

## <a name="record"></a><span data-ttu-id="57501-114">Record</span><span class="sxs-lookup"><span data-stu-id="57501-114">Record</span></span>

<span data-ttu-id="57501-115">对于调用 [Update](record-object-ado.md) 之前添加的字段，此属性将为空（适用于 [Record](update-method-ado.md) 对象）。</span><span class="sxs-lookup"><span data-stu-id="57501-115">For [Record](record-object-ado.md) objects, this property will be empty for fields added before [Update](update-method-ado.md) is called.</span></span>

