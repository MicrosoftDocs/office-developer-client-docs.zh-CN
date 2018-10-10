---
title: Number 属性 (ADO)
TOCTitle: Number Property (ADO)
ms:assetid: b5103af5-356b-ec74-cd62-86e59467d491
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249868(v=office.15)
ms:contentKeyID: 48547243
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4e9b048643b1892197f610ef6d53e6ba46b170d8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465521"
---
# <a name="number-property-ado"></a><span data-ttu-id="fe384-102">Number 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="fe384-102">Number Property (ADO)</span></span>


<span data-ttu-id="fe384-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="fe384-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="fe384-104">指示用于唯一标识 [Error](error-object-ado.md) 对象的编号。</span><span class="sxs-lookup"><span data-stu-id="fe384-104">Indicates the number that uniquely identifies an [Error](error-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="fe384-105">返回值</span><span class="sxs-lookup"><span data-stu-id="fe384-105">Return Value</span></span>

<span data-ttu-id="fe384-106">返回一个 **Long** 值，该值与 [ErrorValueEnum](errorvalueenum.md) 中的一个常量对应。</span><span class="sxs-lookup"><span data-stu-id="fe384-106">Returns a **Long** value that may correspond to one of the [ErrorValueEnum](errorvalueenum.md) constants.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe384-107">备注</span><span class="sxs-lookup"><span data-stu-id="fe384-107">Remarks</span></span>

<span data-ttu-id="fe384-p101">使用 **Number** 属性可确定发生了哪种错误。此属性的值是与错误条件对应的唯一数字。</span><span class="sxs-lookup"><span data-stu-id="fe384-p101">Use the **Number** property to determine which error occurred. The value of the property is a unique number that corresponds to the error condition.</span></span>

<span data-ttu-id="fe384-110">[Errors](errors-collection-ado.md) 集合返回一个 HRESULT，格式为十六进制（例如，0x80004005）或长整型值（例如，2147467259）。</span><span class="sxs-lookup"><span data-stu-id="fe384-110">The [Errors](errors-collection-ado.md) collection returns an HRESULT in either hexadecimal format (for example, 0x80004005) or long value (for example, 2147467259).</span></span> <span data-ttu-id="fe384-111">这些 HRESULT 可由基础组件引发，如 OLE DB，甚至 OLE 本身。</span><span class="sxs-lookup"><span data-stu-id="fe384-111">These HRESULTs can be raised by underlying components, such as OLE DB or even OLE itself.</span></span> <span data-ttu-id="fe384-112">有关这些号码的详细信息，请参阅第 16 章*OLE DB 程序员参考 （英文）。*</span><span class="sxs-lookup"><span data-stu-id="fe384-112">For more information about these numbers, see Chapter 16 of the *OLE DB Programmer's Reference.*</span></span>

