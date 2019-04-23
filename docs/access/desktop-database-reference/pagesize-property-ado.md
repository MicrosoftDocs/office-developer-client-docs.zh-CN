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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288131"
---
# <a name="pagesize-property-ado"></a><span data-ttu-id="62b79-102">PageSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="62b79-102">PageSize property (ADO)</span></span>


<span data-ttu-id="62b79-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="62b79-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="62b79-104">指示由多少记录构成 [Recordset](recordset-object-ado.md) 中的一页。</span><span class="sxs-lookup"><span data-stu-id="62b79-104">Indicates how many records constitute one page in the [Recordset](recordset-object-ado.md).</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="62b79-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="62b79-105">Settings and return values</span></span>

<span data-ttu-id="62b79-106">设置或返回一个 **Long** 值，指示页上的记录数。</span><span class="sxs-lookup"><span data-stu-id="62b79-106">Sets or returns a **Long** value that indicates how many records are on a page.</span></span> <span data-ttu-id="62b79-107">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="62b79-107">The default is 10.</span></span>

## <a name="remarks"></a><span data-ttu-id="62b79-108">注解</span><span class="sxs-lookup"><span data-stu-id="62b79-108">Remarks</span></span>

<span data-ttu-id="62b79-109">使用 **PageSize** 属性可确定组成数据逻辑页的记录数。</span><span class="sxs-lookup"><span data-stu-id="62b79-109">Use the **PageSize** property to determine how many records make up a logical page of data.</span></span> <span data-ttu-id="62b79-110">建立页大小后就可以使用 [AbsolutePage](absolutepage-property-ado.md) 属性移至特定页的首条记录。</span><span class="sxs-lookup"><span data-stu-id="62b79-110">Establishing a page size allows you to use the [AbsolutePage](absolutepage-property-ado.md) property to move to the first record of a particular page.</span></span> <span data-ttu-id="62b79-111">当您希望允许用户逐页浏览数据, 并一次查看特定数量的记录时, 这在 web 服务器方案中非常有用。</span><span class="sxs-lookup"><span data-stu-id="62b79-111">This is useful in web server scenarios when you want to allow the user to page through data, viewing a certain number of records at a time.</span></span>

<span data-ttu-id="62b79-112">可随时设置此属性，并将其值用于计算特定页的首条记录的位置。</span><span class="sxs-lookup"><span data-stu-id="62b79-112">This property can be set at any time, and its value will be used for calculating the location of the first record of a particular page.</span></span>

