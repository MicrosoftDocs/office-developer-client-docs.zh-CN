---
title: StringFormatEnum （访问桌面数据库参考 （英文）
TOCTitle: StringFormatEnum
ms:assetid: ab069d67-d983-f390-5d45-876a9f9d9691
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249794(v=office.15)
ms:contentKeyID: 48546964
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 0e673c7ae5a7e0c6e2ffa2120ed52a4b726a834d
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881144"
---
# <a name="stringformatenum"></a><span data-ttu-id="30266-102">StringFormatEnum</span><span class="sxs-lookup"><span data-stu-id="30266-102">StringFormatEnum</span></span>

<span data-ttu-id="30266-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="30266-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="30266-104">用于将检索 [Recordset](recordset-object-ado.md) 时使用的格式指定为字符串。</span><span class="sxs-lookup"><span data-stu-id="30266-104">Specifies the format when retrieving a [Recordset](recordset-object-ado.md) as a string.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="30266-105">常量</span><span class="sxs-lookup"><span data-stu-id="30266-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="30266-106">值</span><span class="sxs-lookup"><span data-stu-id="30266-106">Value</span></span></p></th>
<th><p><span data-ttu-id="30266-107">说明</span><span class="sxs-lookup"><span data-stu-id="30266-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30266-108"><strong>adClipString</strong></span><span class="sxs-lookup"><span data-stu-id="30266-108"><strong>adClipString</strong></span></span></p></td>
<td><p><span data-ttu-id="30266-109">2</span><span class="sxs-lookup"><span data-stu-id="30266-109">2</span></span></p></td>
<td><p><span data-ttu-id="30266-p101">用 <em>RowDelimiter</em> 分隔行，用 <em>ColumnDelimiter</em> 分隔列，用 <em>NullExpr</em> 分隔空值。<a href="getstring-method-ado.md">GetString</a> 方法的这三个参数仅在与 <strong>adClipString</strong> 的 <em>StringFormat</em> 一起使用时有效。</span><span class="sxs-lookup"><span data-stu-id="30266-p101">Delimits rows by <em>RowDelimiter</em>, columns by <em>ColumnDelimiter</em>, and null values by <em>NullExpr</em>. These three parameters of the <a href="getstring-method-ado.md">GetString</a> method are valid only with a <em>StringFormat</em> of <strong>adClipString</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="30266-112">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="30266-112">ADO/WFC equivalent</span></span>

<span data-ttu-id="30266-113">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="30266-113">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="30266-114">常量</span><span class="sxs-lookup"><span data-stu-id="30266-114">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30266-115">AdoEnums.StringFormat.CLIPSTRING</span><span class="sxs-lookup"><span data-stu-id="30266-115">AdoEnums.StringFormat.CLIPSTRING</span></span></p></td>
</tr>
</tbody>
</table>

