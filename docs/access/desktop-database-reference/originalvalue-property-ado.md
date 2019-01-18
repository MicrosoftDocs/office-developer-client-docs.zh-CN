---
title: OriginalValue 属性 (ADO)
TOCTitle: OriginalValue property (ADO)
ms:assetid: 02ffc728-4692-d439-e2a6-2f02cca53a71
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248798(v=office.15)
ms:contentKeyID: 48542974
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0724320e1aaa1e7bfd3ceab8cf54afd5921c7425
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700421"
---
# <a name="originalvalue-property-ado"></a><span data-ttu-id="dfe9b-102">OriginalValue 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="dfe9b-102">OriginalValue property (ADO)</span></span>

<span data-ttu-id="dfe9b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="dfe9b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dfe9b-104">指示记录发生任何更改之前的 [Field](field-object-ado.md) 值。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-104">Indicates the value of a [Field](field-object-ado.md) that existed in the record before any changes were made.</span></span>

## <a name="return-value"></a><span data-ttu-id="dfe9b-105">返回值</span><span class="sxs-lookup"><span data-stu-id="dfe9b-105">Return value</span></span>

<span data-ttu-id="dfe9b-106">返回一个 **Variant** 值，表示发生任何更改之前的字段值。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-106">Returns a **Variant** value that represents the value of a field prior to any change.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfe9b-107">备注</span><span class="sxs-lookup"><span data-stu-id="dfe9b-107">Remarks</span></span>

<span data-ttu-id="dfe9b-108">使用 **OriginalValue** 属性可从当前记录返回字段的原始字段值。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-108">Use the **OriginalValue** property to return the original field value for a field from the current record.</span></span>

<span data-ttu-id="dfe9b-109">在*即时更新模式*中 （其中提供程序将更改写入基础数据源后调用[Update](update-method-ado.md)方法）， **OriginalValue**属性返回字段值的发生任何更改之前的状态 (也就是说，因为上次调用**Update**方法）。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-109">In *immediate update mode* (in which the provider writes changes to the underlying data source after you call the [Update](update-method-ado.md) method), the **OriginalValue** property returns the field value that existed prior to any changes (that is, since the last **Update** method call).</span></span> <span data-ttu-id="dfe9b-110">该值与 [CancelUpdate](cancelupdate-method-ado.md) 方法用于替换 [Value](value-property-ado.md) 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-110">This is the same value that the [CancelUpdate](cancelupdate-method-ado.md) method uses to replace the [Value](value-property-ado.md) property.</span></span>

<span data-ttu-id="dfe9b-111">以*批更新模式*（顺序提供程序缓存多个更改和将它们写入到基础数据源，仅在调用[UpdateBatch](updatebatch-method-ado.md)方法），则**OriginalValue**属性返回任何之前存在的字段值更改 （即，因为呼叫的最后一个**UpdateBatch**方法）。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-111">In *batch update mode* (in which the provider caches multiple changes and writes them to the underlying data source only when you call the [UpdateBatch](updatebatch-method-ado.md) method), the **OriginalValue** property returns the field value that existed prior to any changes (that is, since the last **UpdateBatch** method call).</span></span> <span data-ttu-id="dfe9b-112">该值与 [CancelBatch](cancelbatch-method-ado.md) 方法用于替换 **Value** 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-112">This is the same value that the [CancelBatch](cancelbatch-method-ado.md) method uses to replace the **Value** property.</span></span> <span data-ttu-id="dfe9b-113">与 [UnderlyingValue](underlyingvalue-property-ado.md) 属性一起使用此属性时，可以解决批更新引发的冲突。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-113">When you use this property with the [UnderlyingValue](underlyingvalue-property-ado.md) property, you can resolve conflicts that arise from batch updates.</span></span>

## <a name="record"></a><span data-ttu-id="dfe9b-114">Record</span><span class="sxs-lookup"><span data-stu-id="dfe9b-114">Record</span></span>

<span data-ttu-id="dfe9b-115">对于 [Record](record-object-ado.md) 对象，在调用 **Update** 之前，添加字段的 [OriginalValue](update-method-ado.md) 属性将为空。</span><span class="sxs-lookup"><span data-stu-id="dfe9b-115">For [Record](record-object-ado.md) objects, the **OriginalValue** property will be empty for fields added before [Update](update-method-ado.md) is called.</span></span>

