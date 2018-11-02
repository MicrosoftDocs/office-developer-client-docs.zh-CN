---
title: FormattedValue 属性 (ADO MD)
TOCTitle: FormattedValue property (ADO MD)
ms:assetid: ea7962f2-b08b-52c9-34e5-c5490c72662f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250189(v=office.15)
ms:contentKeyID: 48548464
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 547feea04a7e6d103f30071094070650705789be
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922109"
---
# <a name="formattedvalue-property-ado-md"></a><span data-ttu-id="37ba1-102">FormattedValue 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="37ba1-102">FormattedValue property (ADO MD)</span></span>


<span data-ttu-id="37ba1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="37ba1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="37ba1-104">指示单元格值的格式化显示。</span><span class="sxs-lookup"><span data-stu-id="37ba1-104">Indicates the formatted display of a cell value.</span></span>

## <a name="return-values"></a><span data-ttu-id="37ba1-105">返回值</span><span class="sxs-lookup"><span data-stu-id="37ba1-105">Return values</span></span>

<span data-ttu-id="37ba1-106">返回一个 **String** 值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="37ba1-106">Returns a **String** and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="37ba1-107">备注</span><span class="sxs-lookup"><span data-stu-id="37ba1-107">Remarks</span></span>

<span data-ttu-id="37ba1-p101">使用 **FormattedValue** 属性可获取 [Cell](value-property-ado-md.md) 对象的 [Value](cell-object-ado-md.md) 属性的带格式显示值。例如，如果单元格值为 1056.87，并且此值表示一个美元金额，则 **FormattedValue** 为 $1,056.87。</span><span class="sxs-lookup"><span data-stu-id="37ba1-p101">Use the **FormattedValue** property to obtain the formatted display value of the [Value](value-property-ado-md.md) property of a [Cell](cell-object-ado-md.md) object. For example, if the value of a cell was 1056.87, and this value represented a dollar amount, **FormattedValue** would be $1,056.87.</span></span>

