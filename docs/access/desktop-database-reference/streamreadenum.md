---
title: StreamReadEnum (Access desktop database reference)
TOCTitle: StreamReadEnum
ms:assetid: 12432c0d-dc2e-10ea-13db-0c07b6ba29bc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248895(v=office.15)
ms:contentKeyID: 48543336
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e4d9c96a7bb34fe0ab3512a316a92e1f7a01ef4b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314719"
---
# <a name="streamreadenum"></a><span data-ttu-id="73da8-102">StreamReadEnum</span><span class="sxs-lookup"><span data-stu-id="73da8-102">StreamReadEnum</span></span>

<span data-ttu-id="73da8-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="73da8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="73da8-104">用于指定应从 [Stream](stream-object-ado.md) 对象读取整个流还是下一行。</span><span class="sxs-lookup"><span data-stu-id="73da8-104">Specifies whether the whole stream or the next line should be read from a [Stream](stream-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="73da8-105">常量</span><span class="sxs-lookup"><span data-stu-id="73da8-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="73da8-106">值</span><span class="sxs-lookup"><span data-stu-id="73da8-106">Value</span></span></p></th>
<th><p><span data-ttu-id="73da8-107">说明</span><span class="sxs-lookup"><span data-stu-id="73da8-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73da8-108"><strong>adReadAll</strong></span><span class="sxs-lookup"><span data-stu-id="73da8-108"><strong>adReadAll</strong></span></span></p></td>
<td><p><span data-ttu-id="73da8-109">-1</span><span class="sxs-lookup"><span data-stu-id="73da8-109">-1</span></span></p></td>
<td><p><span data-ttu-id="73da8-p101">默认值。读取流中从当前位置向前直到 <a href="eos-property-ado.md">EOS</a> 标记之间的所有字节。这是用于二进制流（<a href="type-property-ado-stream.md">Type 属性 (ADO Stream) </a><strong>adTypeBinary</strong>）的唯一有效的 <strong>StreamReadEnum</strong> 值。</span><span class="sxs-lookup"><span data-stu-id="73da8-p101">Default. Reads all bytes from the stream, from the current position onwards to the <a href="eos-property-ado.md">EOS</a> marker. This is the only valid <strong>StreamReadEnum</strong> value with binary streams (<a href="type-property-ado-stream.md">Type</a> is <strong>adTypeBinary</strong>).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73da8-113"><strong>adReadLine</strong></span><span class="sxs-lookup"><span data-stu-id="73da8-113"><strong>adReadLine</strong></span></span></p></td>
<td><p><span data-ttu-id="73da8-114">-2</span><span class="sxs-lookup"><span data-stu-id="73da8-114">-2</span></span></p></td>
<td><p><span data-ttu-id="73da8-115">读取流中的下一行（由 <a href="lineseparator-property-ado.md">LineSeparator</a> 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="73da8-115">Reads the next line from the stream (designated by the <a href="lineseparator-property-ado.md">LineSeparator</a> property).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="73da8-116">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="73da8-116">ADO/WFC equivalent</span></span>

<span data-ttu-id="73da8-117">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="73da8-117">These constants do not have ADO/WFC equivalents.</span></span>

