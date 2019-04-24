---
title: Formal Shape语法
TOCTitle: Formal shape grammar
ms:assetid: a3220569-8804-3dc3-7f9f-b4f8cdab1316
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249752(v=office.15)
ms:contentKeyID: 48546774
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d30ff9146146bb0457a5aa383b2b720a4fdaeb78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292319"
---
# <a name="formal-shape-grammar"></a><span data-ttu-id="e2e73-102">Formal Shape语法</span><span class="sxs-lookup"><span data-stu-id="e2e73-102">Formal shape grammar</span></span>

<span data-ttu-id="e2e73-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e2e73-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e2e73-104">以下是创建任何 Shape 命令的正式语法：</span><span class="sxs-lookup"><span data-stu-id="e2e73-104">This is the formal grammar for creating any shape command:</span></span>

  - <span data-ttu-id="e2e73-105">必需的语法术语是以尖括号（"\<\>"）分隔的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="e2e73-105">Required grammatical terms are text strings delimited by angle brackets ("\<\>").</span></span>

  - <span data-ttu-id="e2e73-106">可选的术语以方括号 ("\[ \]") 分隔。</span><span class="sxs-lookup"><span data-stu-id="e2e73-106">Optional terms are delimited by square brackets ("\[ \]").</span></span>

  - <span data-ttu-id="e2e73-107">替代项以竖线（"|"）指示。</span><span class="sxs-lookup"><span data-stu-id="e2e73-107">Alternatives are indicated by a virgule ("|").</span></span>

  - <span data-ttu-id="e2e73-108">重复替代项以省略号（“...”）指示。</span><span class="sxs-lookup"><span data-stu-id="e2e73-108">Repeating alternatives are indicated by an ellipsis ("...").</span></span>

  - <span data-ttu-id="e2e73-109">*Alpha* 指示字母字符串。</span><span class="sxs-lookup"><span data-stu-id="e2e73-109">*Alpha* indicates a string of alphabetical letters.</span></span>

  - <span data-ttu-id="e2e73-110">*Digit* 指示数字字符串。</span><span class="sxs-lookup"><span data-stu-id="e2e73-110">*Digit* indicates a string of numbers.</span></span>

  - <span data-ttu-id="e2e73-111">*Unicode-digit* 指示 unicode 数字的字符串。</span><span class="sxs-lookup"><span data-stu-id="e2e73-111">*Unicode-digit* indicates a string of unicode digits.</span></span>

<span data-ttu-id="e2e73-112">所有其他术语是文字。</span><span class="sxs-lookup"><span data-stu-id="e2e73-112">All other terms are literals.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e2e73-113">术语</span><span class="sxs-lookup"><span data-stu-id="e2e73-113">Term</span></span></p></th>
<th><p><span data-ttu-id="e2e73-114">定义</span><span class="sxs-lookup"><span data-stu-id="e2e73-114">Definition</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-115">&lt;shape 命令&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-115">&lt;shape-command&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-116">SHAPE [&lt;表-exp&gt; [[AS] &lt;别名&gt;]] [&lt;形状-操作&gt;]</span><span class="sxs-lookup"><span data-stu-id="e2e73-116">SHAPE [&lt;table-exp&gt; [[AS] &lt;alias&gt;]][&lt;shape-action&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-117">&lt;表-exp&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-117">&lt;table-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-118">{&lt;provider-command-text&gt;} |</span><span class="sxs-lookup"><span data-stu-id="e2e73-118">{&lt;provider-command-text&gt;} |</span></span><br />
<span data-ttu-id="e2e73-119">(&lt;形状-命令&gt;) |</span><span class="sxs-lookup"><span data-stu-id="e2e73-119">(&lt;shape-command&gt;) |</span></span><br />
<span data-ttu-id="e2e73-120">引用&lt;的表-名称&gt; |</span><span class="sxs-lookup"><span data-stu-id="e2e73-120">TABLE &lt;quoted-name&gt; |</span></span><br />
<span data-ttu-id="e2e73-121">&lt;带引号的名称&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-121">&lt;quoted-name&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-122">&lt;形状-操作&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-122">&lt;shape-action&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-123">追加&lt;别名字段列表&gt; |</span><span class="sxs-lookup"><span data-stu-id="e2e73-123">APPEND &lt;aliased-field-list&gt; |</span></span></p>
<p><span data-ttu-id="e2e73-124">计算&lt;别名字段列表&gt; [按&lt;字段列表]&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-124">COMPUTE &lt;aliased-field-list&gt; [BY &lt;field-list&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-125">&lt;别名字段列表&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-125">&lt;aliased-field-list&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-126">&lt;别名字段&gt; [, &lt;别名字段 .。。&gt;]</span><span class="sxs-lookup"><span data-stu-id="e2e73-126">&lt;aliased-field&gt; [, &lt;aliased-field...&gt;]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-127">&lt;别名字段&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-127">&lt;aliased-field&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-128">&lt;字段 exp&gt; [[AS] &lt;别名]&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-128">&lt;field-exp&gt; [[AS] &lt;alias&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-129">&lt;字段-exp&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-129">&lt;field-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-130">(&lt;关系-exp&gt;) |</span><span class="sxs-lookup"><span data-stu-id="e2e73-130">(&lt;relation-exp&gt;) |</span></span></p>
<p><span data-ttu-id="e2e73-131">&lt;计算-exp&gt; |</span><span class="sxs-lookup"><span data-stu-id="e2e73-131">&lt;calculated-exp&gt; |</span></span></p>
<p><span data-ttu-id="e2e73-132">&lt;聚合-exp&gt; |</span><span class="sxs-lookup"><span data-stu-id="e2e73-132">&lt;aggregate-exp&gt; |</span></span></p>
<p><span data-ttu-id="e2e73-133">&lt;new-exp&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-133">&lt;new-exp&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-134">&lt;relation_exp&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-134">&lt;relation_exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-135">&lt;表-exp&gt; [[AS] &lt;别名&gt;]</span><span class="sxs-lookup"><span data-stu-id="e2e73-135">&lt;table-exp&gt; [[AS] &lt;alias&gt;]</span></span></p>
<p><span data-ttu-id="e2e73-136">&lt;表-exp&gt; [[AS] &lt;别名&gt;]</span><span class="sxs-lookup"><span data-stu-id="e2e73-136">&lt;table-exp&gt; [[AS] &lt;alias&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-137">&lt;关系--列表&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-137">&lt;relation-cond-list&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-138">&lt;关系-导线&gt; [, &lt;关系-导线&gt;...]</span><span class="sxs-lookup"><span data-stu-id="e2e73-138">&lt;relation-cond&gt; [, &lt;relation-cond&gt;...]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-139">&lt;关系-导线&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-139">&lt;relation-cond&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-140">&lt;field-名称&gt;到&lt;子引用&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-140">&lt;field-name&gt; TO &lt;child-ref&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-141">&lt;子引用&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-141">&lt;child-ref&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-142">&lt;域名称&gt; |</span><span class="sxs-lookup"><span data-stu-id="e2e73-142">&lt;field-name&gt; |</span></span></p>
<p><span data-ttu-id="e2e73-143">参数&lt;参数-ref&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-143">PARAMETER &lt;param-ref&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-144">&lt;param-ref&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-144">&lt;param-ref&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-145">&lt;多种&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-145">&lt;number&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-146">&lt;字段-列表&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-146">&lt;field-list&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-147">&lt;field-name&gt; [, &lt;field-name&gt;]</span><span class="sxs-lookup"><span data-stu-id="e2e73-147">&lt;field-name&gt; [, &lt;field-name&gt;]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-148">&lt;聚合-exp&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-148">&lt;aggregate-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-149">SUM (&lt;限定字段名称&gt;) |</span><span class="sxs-lookup"><span data-stu-id="e2e73-149">SUM(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="e2e73-150">AVG (&lt;限定字段名称&gt;) |</span><span class="sxs-lookup"><span data-stu-id="e2e73-150">AVG(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="e2e73-151">MIN (&lt;限定字段名称&gt;) |</span><span class="sxs-lookup"><span data-stu-id="e2e73-151">MIN(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="e2e73-152">MAX (&lt;限定字段名称&gt;) |</span><span class="sxs-lookup"><span data-stu-id="e2e73-152">MAX(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="e2e73-153">COUNT (&lt;限定别名&gt; | &lt;限定名称&gt;) |</span><span class="sxs-lookup"><span data-stu-id="e2e73-153">COUNT(&lt;qualified-alias&gt; | &lt;qualified-name&gt;) |</span></span></p>
<p><span data-ttu-id="e2e73-154">STDEV (&lt;限定字段名称&gt;) |</span><span class="sxs-lookup"><span data-stu-id="e2e73-154">STDEV(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="e2e73-155">ANY (&lt;限定字段名称&gt;)</span><span class="sxs-lookup"><span data-stu-id="e2e73-155">ANY(&lt;qualified-field-name&gt;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-156">&lt;计算-exp&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-156">&lt;calculated-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-157">CALC (&lt;表达式&gt;)</span><span class="sxs-lookup"><span data-stu-id="e2e73-157">CALC(&lt;expression&gt;)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-158">&lt;限定字段名称&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-158">&lt;qualified-field-name&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-159">&lt;别名&gt;。[&lt;别名&gt;...]&lt;域名称&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-159">&lt;alias&gt;.[&lt;alias&gt;...]&lt;field-name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-160">&lt;alias&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-160">&lt;alias&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-161">&lt;带引号的名称&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-161">&lt;quoted-name&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-162">&lt;域名称&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-162">&lt;field-name&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-163">&lt;带引号的&gt;名称 [[AS &lt;]&gt;别名]</span><span class="sxs-lookup"><span data-stu-id="e2e73-163">&lt;quoted-name&gt; [[AS] &lt;alias&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-164">&lt;带引号的名称&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-164">&lt;quoted-name&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-165">&quot;&lt;类似&gt;&quot; |</span><span class="sxs-lookup"><span data-stu-id="e2e73-165">&quot;&lt;string&gt;&quot; |</span></span></p>
<p><span data-ttu-id="e2e73-166">"&lt;string&gt;" |</span><span class="sxs-lookup"><span data-stu-id="e2e73-166">'&lt;string&gt;' |</span></span></p>
<p><span data-ttu-id="e2e73-167">[&lt;string&gt;] |</span><span class="sxs-lookup"><span data-stu-id="e2e73-167">[&lt;string&gt;] |</span></span></p>
<p><span data-ttu-id="e2e73-168">&lt;别名&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-168">&lt;name&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-169">&lt;限定名称&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-169">&lt;qualified-name&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-170">别名 [. 别名 ...]</span><span class="sxs-lookup"><span data-stu-id="e2e73-170">alias[.alias...]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-171">&lt;别名&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-171">&lt;name&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-172">alpha [alpha | 数字 | _ | # |: | ...]</span><span class="sxs-lookup"><span data-stu-id="e2e73-172">alpha [ alpha | digit | _ | # | : | ...]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-173">&lt;多种&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-173">&lt;number&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-174">数字 [数字 ...]</span><span class="sxs-lookup"><span data-stu-id="e2e73-174">digit [digit...]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-175">&lt;new-exp&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-175">&lt;new-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-176">新&lt;字段-type&gt; [(&lt;number&gt; [, &lt;number&gt;])]</span><span class="sxs-lookup"><span data-stu-id="e2e73-176">NEW &lt;field-type&gt; [(&lt;number&gt; [, &lt;number&gt;])]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-177">&lt;field 类型&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-177">&lt;field-type&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-178">OLE DB 或 ADO 数据类型。</span><span class="sxs-lookup"><span data-stu-id="e2e73-178">An OLE DB or ADO data type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2e73-179">&lt;类似&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-179">&lt;string&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-180">unicode 字符 [unicode-字符 ...]</span><span class="sxs-lookup"><span data-stu-id="e2e73-180">unicode-char [unicode-char...]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2e73-181">&lt;表达式&gt;</span><span class="sxs-lookup"><span data-stu-id="e2e73-181">&lt;expression&gt;</span></span></p></td>
<td><p><span data-ttu-id="e2e73-182">Visual Basic for Applications 表达式，其操作数是在相同行中的其他非 CALC 列。</span><span class="sxs-lookup"><span data-stu-id="e2e73-182">A Visual Basic for Applications expression whose operands are other non-CALC columns in the same row.</span></span></p></td>
</tr>
</tbody>
</table>

