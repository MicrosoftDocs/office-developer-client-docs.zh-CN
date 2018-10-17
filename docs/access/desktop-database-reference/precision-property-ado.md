---
title: Precision 属性 (ADO)
TOCTitle: Precision Property (ADO)
ms:assetid: c9d54d78-d5a5-caf8-d635-259d1fcc0595
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249983(v=office.15)
ms:contentKeyID: 48547685
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a9e98227e98b4f731cd4d361ff6a2c5394058e86
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468947"
---
# <a name="precision-property-ado"></a><span data-ttu-id="75948-102">Precision 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="75948-102">Precision Property (ADO)</span></span>


<span data-ttu-id="75948-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="75948-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="75948-104">指示 [Parameter](parameter-object-ado.md) 对象或数字 [Field](field-object-ado.md) 对象中数值的精度。</span><span class="sxs-lookup"><span data-stu-id="75948-104">Indicates the degree of precision for numeric values in a [Parameter](parameter-object-ado.md) object or for numeric [Field](field-object-ado.md) objects.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="75948-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="75948-105">Settings and Return Values</span></span>

<span data-ttu-id="75948-106">设置或返回一个 **Byte** 值，指示用于表示值的最大位数。</span><span class="sxs-lookup"><span data-stu-id="75948-106">Sets or returns a **Byte** value that indicates the maximum number of digits used to represent values.</span></span>

## <a name="remarks"></a><span data-ttu-id="75948-107">备注</span><span class="sxs-lookup"><span data-stu-id="75948-107">Remarks</span></span>

<span data-ttu-id="75948-108">使用 **Precision** 属性可确定用于表示数字型 **Parameter** 或 **Field** 对象的值的最大位数。</span><span class="sxs-lookup"><span data-stu-id="75948-108">Use the **Precision** property to determine the maximum number of digits used to represent values for a numeric **Parameter** or **Field** object.</span></span>

<span data-ttu-id="75948-109">在 **Parameter** 对象上该值为可读/写。</span><span class="sxs-lookup"><span data-stu-id="75948-109">The value is read/write on a **Parameter** object.</span></span>

<span data-ttu-id="75948-p101">对于 **Field** 对象， **Precision** 通常为只读。然而，对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，只有在指定了 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序通过调用 **Fields** 集合的 **Update** 方法成功添加新 [Field](update-method-ado.md) 之后， **Precision** 才为可读/写。</span><span class="sxs-lookup"><span data-stu-id="75948-p101">For a **Field** object, **Precision** is normally read-only. However, for new **Field** objects that have been appended to the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md), **Precision** is read/write only after the [Value](value-property-ado.md) property for the **Field** has been specified and the data provider has successfully added the new **Field** by calling the [Update](update-method-ado.md) method of the **Fields** collection.</span></span>
