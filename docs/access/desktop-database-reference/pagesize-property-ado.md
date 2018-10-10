---
title: PageSize 属性 (ADO)
TOCTitle: PageSize Property (ADO)
ms:assetid: da56edd8-8947-aeff-2ef5-a8535c66575b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250099(v=office.15)
ms:contentKeyID: 48548079
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 89b28e382f1597ff6466aa323565eaf2ff068605
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465923"
---
# <a name="pagesize-property-ado"></a><span data-ttu-id="5bf8b-102">PageSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5bf8b-102">PageSize Property (ADO)</span></span>


<span data-ttu-id="5bf8b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5bf8b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5bf8b-104">指示由多少记录构成 [Recordset](recordset-object-ado.md) 中的一页。</span><span class="sxs-lookup"><span data-stu-id="5bf8b-104">Indicates how many records constitute one page in the [Recordset](recordset-object-ado.md).</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="5bf8b-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="5bf8b-105">Settings and Return Values</span></span>

<span data-ttu-id="5bf8b-p101">设置或返回一个 **Long** 值，指示页上的记录数。默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="5bf8b-p101">Sets or returns a **Long** value that indicates how many records are on a page. The default is 10.</span></span>

## <a name="remarks"></a><span data-ttu-id="5bf8b-108">备注</span><span class="sxs-lookup"><span data-stu-id="5bf8b-108">Remarks</span></span>

<span data-ttu-id="5bf8b-p102">使用 **PageSize** 属性可确定组成数据逻辑页的记录数。建立页大小后就可以使用 [AbsolutePage](absolutepage-property-ado.md) 属性移至特定页的首条记录。在 Web 服务器方案中，若要允许用户分页浏览数据，每次查看特定数量的记录，该属性将非常有用。</span><span class="sxs-lookup"><span data-stu-id="5bf8b-p102">Use the **PageSize** property to determine how many records make up a logical page of data. Establishing a page size allows you to use the [AbsolutePage](absolutepage-property-ado.md) property to move to the first record of a particular page. This is useful in Web server scenarios when you want to allow the user to page through data, viewing a certain number of records at a time.</span></span>

<span data-ttu-id="5bf8b-112">可随时设置此属性，并将其值用于计算特定页的首条记录的位置。</span><span class="sxs-lookup"><span data-stu-id="5bf8b-112">This property can be set at any time, and its value will be used for calculating the location of the first record of a particular page.</span></span>

