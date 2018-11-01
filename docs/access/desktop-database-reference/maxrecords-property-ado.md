---
title: MaxRecords 属性 (ADO)
TOCTitle: MaxRecords property (ADO)
ms:assetid: 424b2d41-073a-3fbe-30aa-99fac94f9a81
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249195(v=office.15)
ms:contentKeyID: 48544475
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7d66a26cffb14220670643c5b6b5aafe94e8fcb5
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870084"
---
# <a name="maxrecords-property-ado"></a><span data-ttu-id="d535d-102">MaxRecords 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="d535d-102">MaxRecords property (ADO)</span></span>


<span data-ttu-id="d535d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d535d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d535d-104">指示通过查询返回到 [Recordset](recordset-object-ado.md) 的最大记录数。</span><span class="sxs-lookup"><span data-stu-id="d535d-104">Indicates the maximum number of records to return to a [Recordset](recordset-object-ado.md) from a query.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="d535d-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="d535d-105">Settings and return values</span></span>

<span data-ttu-id="d535d-p101">设置或返回一个 **Long** 值，指示要返回的最大记录数。默认值为 0（没有限制）。</span><span class="sxs-lookup"><span data-stu-id="d535d-p101">Sets or returns a **Long** value that indicates the maximum number of records to return. Default is zero (no limit).</span></span>

## <a name="remarks"></a><span data-ttu-id="d535d-108">备注</span><span class="sxs-lookup"><span data-stu-id="d535d-108">Remarks</span></span>

<span data-ttu-id="d535d-p102">使用 **MaxRecords** 属性可限制提供程序从数据源返回的记录数。此属性的默认设置为 0，表示提供程序可返回所有请求的记录。</span><span class="sxs-lookup"><span data-stu-id="d535d-p102">Use the **MaxRecords** property to limit the number of records that the provider returns from the data source. The default setting of this property is zero, which means the provider returns all requested records.</span></span>

<span data-ttu-id="d535d-111">**Recordset** 关闭时 **MaxRecords** 属性为可读/写属性，打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="d535d-111">The **MaxRecords** property is read/write when the **Recordset** is closed and read-only when it is open.</span></span>

