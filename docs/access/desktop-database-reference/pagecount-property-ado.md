---
title: PageCount 属性 (ADO)
TOCTitle: PageCount property (ADO)
ms:assetid: 9cd8bf5c-b1e7-a453-4629-9cba7e408f53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249712(v=office.15)
ms:contentKeyID: 48546609
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ef5179f44a2c7c153411ae33566f3806f1e93573
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867368"
---
# <a name="pagecount-property-ado"></a><span data-ttu-id="b6821-102">PageCount 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b6821-102">PageCount property (ADO)</span></span>


<span data-ttu-id="b6821-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b6821-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b6821-104">指示 [Recordset](recordset-object-ado.md) 对象包含的数据页数。</span><span class="sxs-lookup"><span data-stu-id="b6821-104">Indicates how many pages of data the [Recordset](recordset-object-ado.md) object contains.</span></span>

## <a name="return-value"></a><span data-ttu-id="b6821-105">返回值</span><span class="sxs-lookup"><span data-stu-id="b6821-105">Return value</span></span>

<span data-ttu-id="b6821-106">返回一个 **Long** 值，指示 **Recordset** 中的页数。</span><span class="sxs-lookup"><span data-stu-id="b6821-106">Returns a **Long** value that indicates the number of pages in the **Recordset**.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6821-107">备注</span><span class="sxs-lookup"><span data-stu-id="b6821-107">Remarks</span></span>

<span data-ttu-id="b6821-108">使用 **PageCount** 属性可确定 **Recordset** 对象中的数据页数。</span><span class="sxs-lookup"><span data-stu-id="b6821-108">Use the **PageCount** property to determine how many pages of data are in the **Recordset** object.</span></span> <span data-ttu-id="b6821-109">*页面*是其大小等于[PageSize](pagesize-property-ado.md)属性设置的记录组。</span><span class="sxs-lookup"><span data-stu-id="b6821-109">*Pages* are groups of records whose size equals the [PageSize](pagesize-property-ado.md) property setting.</span></span> <span data-ttu-id="b6821-110">即使最后一页由于记录数小于 **PageSize** 值而无法组成完整的一页，也仍将其算作 **PageCount** 值中的附加页。</span><span class="sxs-lookup"><span data-stu-id="b6821-110">Even if the last page is incomplete because there are fewer records than the **PageSize** value, it counts as an additional page in the **PageCount** value.</span></span> <span data-ttu-id="b6821-111">如果 **Recordset** 对象不支持此属性，则该值为 -1，指示 **PageCount** 不可确定。</span><span class="sxs-lookup"><span data-stu-id="b6821-111">If the **Recordset** object does not support this property, the value will be -1 to indicate that the **PageCount** is indeterminable.</span></span>

<span data-ttu-id="b6821-112">有关页功能的详细信息，请参阅 **PageSize** 和 [AbsolutePage](absolutepage-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="b6821-112">See the **PageSize** and [AbsolutePage](absolutepage-property-ado.md) properties for more on page functionality.</span></span>

