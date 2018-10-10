---
title: RecordCount 属性 (ADO)
TOCTitle: RecordCount Property (ADO)
ms:assetid: e3072d10-5bf7-02a8-027e-a9d9a34e3f27
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250155(v=office.15)
ms:contentKeyID: 48548304
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a619570264973fc70b7cc5bd581437a4002b00be
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468359"
---
# <a name="recordcount-property-ado"></a><span data-ttu-id="6c16b-102">RecordCount 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="6c16b-102">RecordCount Property (ADO)</span></span>


<span data-ttu-id="6c16b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6c16b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6c16b-104">指示 [Recordset](recordset-object-ado.md) 对象中的记录数。</span><span class="sxs-lookup"><span data-stu-id="6c16b-104">Indicates the number of records in a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="6c16b-105">返回值</span><span class="sxs-lookup"><span data-stu-id="6c16b-105">Return Value</span></span>

<span data-ttu-id="6c16b-106">返回一个 **Long** 值，指示 **Recordset** 中的记录数。</span><span class="sxs-lookup"><span data-stu-id="6c16b-106">Returns a **Long** value that indicates the number of records in the **Recordset**.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c16b-107">备注</span><span class="sxs-lookup"><span data-stu-id="6c16b-107">Remarks</span></span>

<span data-ttu-id="6c16b-p101">使用 **RecordCount** 属性可了解 **Recordset** 对象中的记录数。如果提供程序或游标类型不支持 **RecordCount** ，而导致 ADO 无法确定记录数，则该属性返回 -1。读取已关闭的 **Recordset** 的 **RecordCount** 属性将导致错误。</span><span class="sxs-lookup"><span data-stu-id="6c16b-p101">Use the **RecordCount** property to find out how many records are in a **Recordset** object. The property returns -1 when ADO cannot determine the number of records or if the provider or cursor type does not support **RecordCount**. Reading the **RecordCount** property on a closed **Recordset** causes an error.</span></span>

<span data-ttu-id="6c16b-p102">如果 **Recordset** 对象支持近似定位或书签  即，分别为 **Supports (adApproxPosition)** 或 **Supports (adBookmark)** ，则返回 **True**  该值将是 **Recordset** 中的准确记录数，而不管是否已完全填充该记录集。如果 **Recordset** 对象不支持近似定位，由于不得不检索和计算所有记录以返回精确的 **RecordCount** 值，该属性将极大地耗费资源。</span><span class="sxs-lookup"><span data-stu-id="6c16b-p102">If the **Recordset** object supports approximate positioning or bookmarks — that is, **Supports (adApproxPosition)** or **Supports (adBookmark)**, respectively, return **True** — this value will be the exact number of records in the **Recordset**, regardless of whether it has been fully populated. If the **Recordset** object does not support approximate positioning, this property may be a significant drain on resources because all records will have to be retrieved and counted to return an accurate **RecordCount** value.</span></span>

<span data-ttu-id="6c16b-p103">**Recordset** 对象的游标类型决定是否能确定记录数。对于只进游标， **RecordCount** 属性将返回 -1 ；对于静态游标或键集游标，则返回实际记录数；而对于动态游标，则返回 -1 或实际记录数，具体情况视数据源而定。</span><span class="sxs-lookup"><span data-stu-id="6c16b-p103">The cursor type of the **Recordset** object affects whether the number of records can be determined. The **RecordCount** property will return -1 for a forward-only cursor; the actual count for a static or keyset cursor; and either -1 or the actual count for a dynamic cursor, depending on the data source.</span></span>

