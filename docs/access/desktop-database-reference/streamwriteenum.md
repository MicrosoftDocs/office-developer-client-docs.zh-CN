---
title: StreamWriteEnum （访问桌面数据库参考 （英文）
TOCTitle: StreamWriteEnum
ms:assetid: b4356999-d7a8-abfa-f6a8-6c2dd04b9257
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249861(v=office.15)
ms:contentKeyID: 48547216
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 87144e5409fb54cf0cb8f59ad4d593ab05d694a4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706168"
---
# <a name="streamwriteenum"></a><span data-ttu-id="2bed7-102">StreamWriteEnum</span><span class="sxs-lookup"><span data-stu-id="2bed7-102">StreamWriteEnum</span></span>

<span data-ttu-id="2bed7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2bed7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2bed7-104">用于指定是否将行分隔符追加到写入 [Stream](stream-object-ado.md) 对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="2bed7-104">Specifies whether a line separator is appended to the string written to a [Stream](stream-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2bed7-105">常量</span><span class="sxs-lookup"><span data-stu-id="2bed7-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="2bed7-106">值</span><span class="sxs-lookup"><span data-stu-id="2bed7-106">Value</span></span></p></th>
<th><p><span data-ttu-id="2bed7-107">说明</span><span class="sxs-lookup"><span data-stu-id="2bed7-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bed7-108"><strong>adWriteChar</strong></span><span class="sxs-lookup"><span data-stu-id="2bed7-108"><strong>adWriteChar</strong></span></span></p></td>
<td><p><span data-ttu-id="2bed7-109">0</span><span class="sxs-lookup"><span data-stu-id="2bed7-109">0</span></span></p></td>
<td><p><span data-ttu-id="2bed7-p101">默认值。将指定的文本字符串（由 <em>Data</em> 参数指定）写入 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="2bed7-p101">Default. Writes the specified text string (specified by the <em>Data</em> parameter) to the <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bed7-112"><strong>adWriteLine</strong></span><span class="sxs-lookup"><span data-stu-id="2bed7-112"><strong>adWriteLine</strong></span></span></p></td>
<td><p><span data-ttu-id="2bed7-113">1</span><span class="sxs-lookup"><span data-stu-id="2bed7-113">1</span></span></p></td>
<td><p><span data-ttu-id="2bed7-p102">将文本字符串和行分隔符写入 <strong>Stream</strong> 对象。如果未定义 <a href="lineseparator-property-ado.md">LineSeparator</a> 属性，此常量将返回一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="2bed7-p102">Writes a text string and a line separator character to a <strong>Stream</strong> object. If the <a href="lineseparator-property-ado.md">LineSeparator</a> property is not defined, then this returns a run-time error.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="2bed7-116">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="2bed7-116">ADO/WFC equivalent</span></span>

<span data-ttu-id="2bed7-117">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="2bed7-117">These constants do not have ADO/WFC equivalents.</span></span>

