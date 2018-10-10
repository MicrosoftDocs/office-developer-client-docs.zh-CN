---
title: AbsolutePage 属性 (ADO)
TOCTitle: AbsolutePage Property (ADO)
ms:assetid: b6e5daac-cc21-0aa6-9119-a973595762bb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249881(v=office.15)
ms:contentKeyID: 48547288
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 60b7b58efaa6fb8686e4f43da9b9733f3629f1a7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467897"
---
# <a name="absolutepage-property-ado"></a><span data-ttu-id="946b9-102">AbsolutePage 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="946b9-102">AbsolutePage Property (ADO)</span></span>


<span data-ttu-id="946b9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="946b9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="946b9-104">指示当前记录驻留在哪一页。</span><span class="sxs-lookup"><span data-stu-id="946b9-104">Indicates on which page the current record resides.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="946b9-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="946b9-105">Settings and Return Values</span></span>

<span data-ttu-id="946b9-106">设置或返回一个 **Long** 值，该值的范围为 1 到 [Recordset](recordset-object-ado.md) 对象中的页数 ( [PageCount](pagecount-property-ado.md))；或返回 [PositionEnum](positionenum.md) 值之一。</span><span class="sxs-lookup"><span data-stu-id="946b9-106">Sets or returns a **Long** value from 1 to the number of pages in the [Recordset](recordset-object-ado.md) object ( [PageCount](pagecount-property-ado.md) ), or returns one of the [PositionEnum](positionenum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="946b9-107">备注</span><span class="sxs-lookup"><span data-stu-id="946b9-107">Remarks</span></span>

<span data-ttu-id="946b9-p101">此属性可用于标识当前记录所在的页的页码。它使用 [PageSize](pagesize-property-ado.md) 属性将 **Recordset** 对象的总行集计数逻辑划分为一系列页，每一页中都包含与 **PageSize** 相等的记录数（最后一页除外，该页的记录数可以小于这个数）。提供程序必须支持相应的功能，此属性才可用。</span><span class="sxs-lookup"><span data-stu-id="946b9-p101">This property can be used to identify the page number on which the current record is located. It uses the [PageSize](pagesize-property-ado.md) property to logically divide the total rowset count of the **Recordset** object into a series of pages, each of which has the number of records equal to **PageSize** (except for the last page, which may have fewer records). The provider must support the appropriate functionality for this property to be available.</span></span>

<span data-ttu-id="946b9-111">获取或设置 **AbsolutePage** 属性时，ADO 将根据以下情况将 [AbsolutePosition](absoluteposition-property-ado.md) 属性与 [PageSize](pagesize-property-ado.md) 属性结合使用：</span><span class="sxs-lookup"><span data-stu-id="946b9-111">When getting or setting the **AbsolutePage** property, ADO uses the [AbsolutePosition](absoluteposition-property-ado.md) property and the [PageSize](pagesize-property-ado.md) property together as follows:</span></span>

  - <span data-ttu-id="946b9-112">若要获取 **AbsolutePage** ，ADO 将首先检索 **AbsolutePosition** ，然后用它除以 **PageSize** 。</span><span class="sxs-lookup"><span data-stu-id="946b9-112">To get the **AbsolutePage**, ADO first retrieves the **AbsolutePosition**, and then divides it by the **PageSize**.</span></span>

  - <span data-ttu-id="946b9-p102">若要设置 **AbsolutePage** ，ADO 将按照以下方式移动 **AbsolutePosition** ：它将 **PageSize** 乘以新 **AbsolutePage** 值，然后向该值加 1。这样，成功设置 **AbsolutePage** 后， **Recordset** 中的当前位置就位于该页的第一条记录处。</span><span class="sxs-lookup"><span data-stu-id="946b9-p102">To set the **AbsolutePage**, ADO moves the **AbsolutePosition** as follows: it multiplies the **PageSize** by the new **AbsolutePage** value and then adds 1 to the value. As a result, the current position in the **Recordset** after successfully setting **AbsolutePage** is, the first record in that page.</span></span>

<span data-ttu-id="946b9-p103">和 **AbsolutePosition** 属性一样， **AbsolutePage** 将从 1 开始，当前记录为 **Recordset** 中的第一条记录时，它等于 1。设置此属性，可以移动到特定页的第一条记录处。可从 **PageCount** 属性获得总页数。</span><span class="sxs-lookup"><span data-stu-id="946b9-p103">Like the **AbsolutePosition** property, **AbsolutePage** is 1-based and equals 1 when the current record is the first record in the **Recordset**. Set this property to move to the first record of a particular page. Obtain the total number of pages from the **PageCount** property.</span></span>

