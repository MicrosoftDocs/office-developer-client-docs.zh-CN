---
title: PageCount 属性 (ADO)
TOCTitle: PageCount property (ADO)
ms:assetid: 9cd8bf5c-b1e7-a453-4629-9cba7e408f53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249712(v=office.15)
ms:contentKeyID: 48546609
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b37ccc0c9a61e00b3c2e8f5eb3367831e5ddea43
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288117"
---
# <a name="pagecount-property-ado"></a><span data-ttu-id="489bf-102">PageCount 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="489bf-102">PageCount property (ADO)</span></span>


<span data-ttu-id="489bf-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="489bf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="489bf-104">指示 [Recordset](recordset-object-ado.md) 对象包含的数据页数。</span><span class="sxs-lookup"><span data-stu-id="489bf-104">Indicates how many pages of data the [Recordset](recordset-object-ado.md) object contains.</span></span>

## <a name="return-value"></a><span data-ttu-id="489bf-105">返回值</span><span class="sxs-lookup"><span data-stu-id="489bf-105">Return value</span></span>

<span data-ttu-id="489bf-106">返回一个 **Long** 值，指示 **Recordset** 中的页数。</span><span class="sxs-lookup"><span data-stu-id="489bf-106">Returns a **Long** value that indicates the number of pages in the **Recordset**.</span></span>

## <a name="remarks"></a><span data-ttu-id="489bf-107">注解</span><span class="sxs-lookup"><span data-stu-id="489bf-107">Remarks</span></span>

<span data-ttu-id="489bf-p101">使用 **PageCount** 属性可确定 **Recordset** 对象中的数据页数。*Pages* 是若干组记录，其大小与 [PageSize](pagesize-property-ado.md) 属性设置相等。即使最后一页由于记录数小于 **PageSize** 值而无法组成完整的一页，也仍将其算作 **PageCount** 值中的附加页。如果 **Recordset** 对象不支持此属性，则该值为 -1，指示 **PageCount** 不可确定。</span><span class="sxs-lookup"><span data-stu-id="489bf-p101">Use the **PageCount** property to determine how many pages of data are in the **Recordset** object. *Pages* are groups of records whose size equals the [PageSize](pagesize-property-ado.md) property setting. Even if the last page is incomplete because there are fewer records than the **PageSize** value, it counts as an additional page in the **PageCount** value. If the **Recordset** object does not support this property, the value will be -1 to indicate that the **PageCount** is indeterminable.</span></span>

<span data-ttu-id="489bf-112">有关页功能的详细信息，请参阅 **PageSize** 和 [AbsolutePage](absolutepage-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="489bf-112">See the **PageSize** and [AbsolutePage](absolutepage-property-ado.md) properties for more on page functionality.</span></span>

