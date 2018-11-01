---
title: NumericScale 属性 (ADO)
TOCTitle: NumericScale property (ADO)
ms:assetid: 51b232d2-5bfd-521c-f4e9-65655ecc7c70
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249263(v=office.15)
ms:contentKeyID: 48544824
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: eb2c799fd7c9d1cc74c6081c10f7a8d356e79faf
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876013"
---
# <a name="numericscale-property-ado"></a><span data-ttu-id="64cc4-102">NumericScale 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="64cc4-102">NumericScale property (ADO)</span></span>


<span data-ttu-id="64cc4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="64cc4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="64cc4-104">指示 [Parameter](parameter-object-ado.md) 或 [Field](field-object-ado.md) 对象中数值的小数位数。</span><span class="sxs-lookup"><span data-stu-id="64cc4-104">Indicates the scale of numeric values in a [Parameter](parameter-object-ado.md) or [Field](field-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="64cc4-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="64cc4-105">Settings and return values</span></span>

<span data-ttu-id="64cc4-106">设置或返回一个 **Byte** 值，指示数值的小数位数。</span><span class="sxs-lookup"><span data-stu-id="64cc4-106">Sets or returns a **Byte** value that indicates the number of decimal places to which numeric values will be resolved.</span></span>

## <a name="remarks"></a><span data-ttu-id="64cc4-107">备注</span><span class="sxs-lookup"><span data-stu-id="64cc4-107">Remarks</span></span>

<span data-ttu-id="64cc4-108">使用 **NumericScale** 属性可确定将用于表示数字型 **Parameter** 或 **Field** 对象的小数点后的数字个数。</span><span class="sxs-lookup"><span data-stu-id="64cc4-108">Use the **NumericScale** property to determine how many digits to the right of the decimal point will be used to represent values for a numeric **Parameter** or **Field** object.</span></span>

<span data-ttu-id="64cc4-109">对于 **Parameter** 对象， **NumericScale** 属性为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="64cc4-109">For **Parameter** objects, the **NumericScale** property is read/write.</span></span>

<span data-ttu-id="64cc4-p101">对于 **Field** 对象， **NumericScale** 通常为只读。然而，对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，只有在指定了 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序已通过调用 **Fields** 集合的 **Update** 方法成功添加新 [Field](update-method-ado.md) 之后， **NumericScale** 才为可读/写。</span><span class="sxs-lookup"><span data-stu-id="64cc4-p101">For a **Field** object, **NumericScale** is normally read-only. However, for new **Field** objects that have been appended to the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md), **NumericScale** is read/write only after the [Value](value-property-ado.md) property for the **Field** has been specified and the data provider has successfully added the new **Field** by calling the [Update](update-method-ado.md) method of the **Fields** collection.</span></span>

