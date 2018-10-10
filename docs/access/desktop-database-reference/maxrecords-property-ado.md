---
title: MaxRecords 属性 (ADO)
TOCTitle: MaxRecords Property (ADO)
ms:assetid: 424b2d41-073a-3fbe-30aa-99fac94f9a81
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249195(v=office.15)
ms:contentKeyID: 48544475
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d8753bf09655371042e97ead083c6849f1736b8b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467054"
---
# <a name="maxrecords-property-ado"></a><span data-ttu-id="a9c6c-102">MaxRecords 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a9c6c-102">MaxRecords Property (ADO)</span></span>


<span data-ttu-id="a9c6c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a9c6c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a9c6c-104">指示通过查询返回到 [Recordset](recordset-object-ado.md) 的最大记录数。</span><span class="sxs-lookup"><span data-stu-id="a9c6c-104">Indicates the maximum number of records to return to a [Recordset](recordset-object-ado.md) from a query.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="a9c6c-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="a9c6c-105">Settings and Return Values</span></span>

<span data-ttu-id="a9c6c-p101">设置或返回一个 **Long** 值，指示要返回的最大记录数。默认值为 0（没有限制）。</span><span class="sxs-lookup"><span data-stu-id="a9c6c-p101">Sets or returns a **Long** value that indicates the maximum number of records to return. Default is zero (no limit).</span></span>

## <a name="remarks"></a><span data-ttu-id="a9c6c-108">备注</span><span class="sxs-lookup"><span data-stu-id="a9c6c-108">Remarks</span></span>

<span data-ttu-id="a9c6c-p102">使用 **MaxRecords** 属性可限制提供程序从数据源返回的记录数。此属性的默认设置为 0，表示提供程序可返回所有请求的记录。</span><span class="sxs-lookup"><span data-stu-id="a9c6c-p102">Use the **MaxRecords** property to limit the number of records that the provider returns from the data source. The default setting of this property is zero, which means the provider returns all requested records.</span></span>

<span data-ttu-id="a9c6c-111">**Recordset** 关闭时 **MaxRecords** 属性为可读/写属性，打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="a9c6c-111">The **MaxRecords** property is read/write when the **Recordset** is closed and read-only when it is open.</span></span>

