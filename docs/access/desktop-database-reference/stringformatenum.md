---
title: StringFormatEnum (Access desktop database reference)
TOCTitle: StringFormatEnum
ms:assetid: ab069d67-d983-f390-5d45-876a9f9d9691
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249794(v=office.15)
ms:contentKeyID: 48546964
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 89eb3e9c972b19bc9908f29ce5ec5e42c8974d54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314460"
---
# <a name="stringformatenum"></a><span data-ttu-id="57bbc-102">StringFormatEnum</span><span class="sxs-lookup"><span data-stu-id="57bbc-102">StringFormatEnum</span></span>

<span data-ttu-id="57bbc-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="57bbc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="57bbc-104">用于将检索 [Recordset](recordset-object-ado.md) 时使用的格式指定为字符串。</span><span class="sxs-lookup"><span data-stu-id="57bbc-104">Specifies the format when retrieving a [Recordset](recordset-object-ado.md) as a string.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="57bbc-105">常量</span><span class="sxs-lookup"><span data-stu-id="57bbc-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="57bbc-106">值</span><span class="sxs-lookup"><span data-stu-id="57bbc-106">Value</span></span></p></th>
<th><p><span data-ttu-id="57bbc-107">说明</span><span class="sxs-lookup"><span data-stu-id="57bbc-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57bbc-108"><strong>adClipString</strong></span><span class="sxs-lookup"><span data-stu-id="57bbc-108"><strong>adClipString</strong></span></span></p></td>
<td><p><span data-ttu-id="57bbc-109">双面</span><span class="sxs-lookup"><span data-stu-id="57bbc-109">2</span></span></p></td>
<td><p><span data-ttu-id="57bbc-p101">用 <em>RowDelimiter</em> 分隔行，用 <em>ColumnDelimiter</em> 分隔列，用 <em>NullExpr</em> 分隔空值。<a href="getstring-method-ado.md">GetString</a> 方法的这三个参数仅在与 <strong>adClipString</strong> 的 <em>StringFormat</em> 一起使用时有效。</span><span class="sxs-lookup"><span data-stu-id="57bbc-p101">Delimits rows by <em>RowDelimiter</em>, columns by <em>ColumnDelimiter</em>, and null values by <em>NullExpr</em>. These three parameters of the <a href="getstring-method-ado.md">GetString</a> method are valid only with a <em>StringFormat</em> of <strong>adClipString</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="57bbc-112">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="57bbc-112">ADO/WFC equivalent</span></span>

<span data-ttu-id="57bbc-113">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="57bbc-113">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="57bbc-114">常量</span><span class="sxs-lookup"><span data-stu-id="57bbc-114">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57bbc-115">AdoEnums adclipstring</span><span class="sxs-lookup"><span data-stu-id="57bbc-115">AdoEnums.StringFormat.CLIPSTRING</span></span></p></td>
</tr>
</tbody>
</table>

