---
title: 使用页面 （访问桌面数据库参考 （英文）
TOCTitle: Using Pages
ms:assetid: 516fb7c2-c7a2-385b-83e7-2091c7283ea2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249261(v=office.15)
ms:contentKeyID: 48544817
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b25123698f39e602b59a2f5cd6bd9a2f0595addb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468731"
---
# <a name="using-pages"></a><span data-ttu-id="6ae29-102">使用页</span><span class="sxs-lookup"><span data-stu-id="6ae29-102">Using Pages</span></span>


<span data-ttu-id="6ae29-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6ae29-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6ae29-104">使用 **PageCount** 属性可以确定 **Recordset** 对象中的数据页数。</span><span class="sxs-lookup"><span data-stu-id="6ae29-104">Use the **PageCount** property to determine how many pages of data are in the **Recordset** object.</span></span> <span data-ttu-id="6ae29-105">*页面*是其大小等于**PageSize**属性设置的记录组。</span><span class="sxs-lookup"><span data-stu-id="6ae29-105">*Pages* are groups of records whose size equals the **PageSize** property setting.</span></span> <span data-ttu-id="6ae29-106">即使最后一页由于记录数小于 **PageSize** 值而不完整，它也被视作 **PageCount** 值中的另一页。</span><span class="sxs-lookup"><span data-stu-id="6ae29-106">Even if the last page is incomplete because there are fewer records than the **PageSize** value, it counts as an additional page in the **PageCount** value.</span></span> <span data-ttu-id="6ae29-107">如果 **Recordset** 对象不支持此属性， **PageCount** 将为 -1，这指示 **PageCount** 是不可确定的。</span><span class="sxs-lookup"><span data-stu-id="6ae29-107">If the **Recordset** object does not support this property, **PageCount** will be -1 to indicate that the **PageCount** is indeterminable.</span></span>

<span data-ttu-id="6ae29-p102">使用 **PageSize** 属性可以确定逻辑数据页由多少记录组成。建立页大小允许您使用 **AbsolutePage** 属性来移到特定页的第一个记录。这对于 Web 服务器方案非常有用，此时您希望允许用户逐页浏览数据，并一次查看特定数量的记录。</span><span class="sxs-lookup"><span data-stu-id="6ae29-p102">Use the **PageSize** property to determine how many records make up a logical page of data. Establishing a page size allows you to use the **AbsolutePage** property to move to the first record of a particular page. This is useful in Web-server scenarios when you want to allow the user to page through data, viewing a certain number of records at a time.</span></span>

<span data-ttu-id="6ae29-111">可随时设置此属性，并将其值用于计算特定页的首条记录的位置。</span><span class="sxs-lookup"><span data-stu-id="6ae29-111">This property can be set at any time, and its value will be used for calculating the location of the first record of a particular page.</span></span>

<span data-ttu-id="6ae29-p103">使用 **AbsolutePage** 属性可以确定当前记录所在页的页码。另外，提供程序必须支持相应的功能，才能使该属性可用。</span><span class="sxs-lookup"><span data-stu-id="6ae29-p103">Use the **AbsolutePage** property to identify the page number on which the current record is located. Again, the provider must support the appropriate functionality for this property to be available.</span></span>

<span data-ttu-id="6ae29-p104">**AbsolutePage** 从 1 开始，如果当前的记录是 **Recordset** 中的第一个记录时，此属性将等于 1。设置此属性可以移到特定页的第一个记录。可以从 **PageCount** 属性获取总页数。</span><span class="sxs-lookup"><span data-stu-id="6ae29-p104">**AbsolutePage** is 1-based and equals 1 when the current record is the first record in the **Recordset**. Set this property to move to the first record of a particular page. Obtain the total number of pages from the **PageCount** property.</span></span>
