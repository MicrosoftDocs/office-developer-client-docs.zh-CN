---
title: PageSize 属性 (ADO)
TOCTitle: PageSize property (ADO)
ms:assetid: da56edd8-8947-aeff-2ef5-a8535c66575b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250099(v=office.15)
ms:contentKeyID: 48548079
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9365acb13820f898c053d4c90fc252bfd3b228c4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709549"
---
# <a name="pagesize-property-ado"></a><span data-ttu-id="02e98-102">PageSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="02e98-102">PageSize property (ADO)</span></span>


<span data-ttu-id="02e98-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="02e98-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="02e98-104">指示由多少记录构成 [Recordset](recordset-object-ado.md) 中的一页。</span><span class="sxs-lookup"><span data-stu-id="02e98-104">Indicates how many records constitute one page in the [Recordset](recordset-object-ado.md).</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="02e98-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="02e98-105">Settings and return values</span></span>

<span data-ttu-id="02e98-p101">设置或返回一个 **Long** 值，指示页上的记录数。默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="02e98-p101">Sets or returns a **Long** value that indicates how many records are on a page. The default is 10.</span></span>

## <a name="remarks"></a><span data-ttu-id="02e98-108">备注</span><span class="sxs-lookup"><span data-stu-id="02e98-108">Remarks</span></span>

<span data-ttu-id="02e98-109">使用 **PageSize** 属性可确定组成数据逻辑页的记录数。</span><span class="sxs-lookup"><span data-stu-id="02e98-109">Use the **PageSize** property to determine how many records make up a logical page of data.</span></span> <span data-ttu-id="02e98-110">建立页大小允许您使用 [AbsolutePage](absolutepage-property-ado.md) 属性来移到特定页的第一个记录。</span><span class="sxs-lookup"><span data-stu-id="02e98-110">Establishing a page size allows you to use the [AbsolutePage](absolutepage-property-ado.md) property to move to the first record of a particular page.</span></span> <span data-ttu-id="02e98-111">当您希望允许逐页浏览数据，用户一次查看一定数量的记录时，这很有用在 web 服务器方案。</span><span class="sxs-lookup"><span data-stu-id="02e98-111">This is useful in web server scenarios when you want to allow the user to page through data, viewing a certain number of records at a time.</span></span>

<span data-ttu-id="02e98-112">可随时设置此属性，并将其值用于计算特定页的首条记录的位置。</span><span class="sxs-lookup"><span data-stu-id="02e98-112">This property can be set at any time, and its value will be used for calculating the location of the first record of a particular page.</span></span>

