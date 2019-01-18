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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708044"
---
# <a name="formal-shape-grammar"></a><span data-ttu-id="82bf1-102">Formal Shape语法</span><span class="sxs-lookup"><span data-stu-id="82bf1-102">Formal shape grammar</span></span>

<span data-ttu-id="82bf1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="82bf1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="82bf1-104">以下是创建任何 Shape 命令的正式语法：</span><span class="sxs-lookup"><span data-stu-id="82bf1-104">This is the formal grammar for creating any shape command:</span></span>

  - <span data-ttu-id="82bf1-105">必需的语法术语是以尖括号（"\<\>"）分隔的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="82bf1-105">Required grammatical terms are text strings delimited by angle brackets ("\<\>").</span></span>

  - <span data-ttu-id="82bf1-106">可选的术语分隔方括号 ("\[ \]")。</span><span class="sxs-lookup"><span data-stu-id="82bf1-106">Optional terms are delimited by square brackets ("\[ \]").</span></span>

  - <span data-ttu-id="82bf1-107">替代项以竖线（"|"）指示。</span><span class="sxs-lookup"><span data-stu-id="82bf1-107">Alternatives are indicated by a virgule ("|").</span></span>

  - <span data-ttu-id="82bf1-108">重复替代项以省略号（"..."）指示。</span><span class="sxs-lookup"><span data-stu-id="82bf1-108">Repeating alternatives are indicated by an ellipsis ("...").</span></span>

  - <span data-ttu-id="82bf1-109">*Alpha*指示字母字符串。</span><span class="sxs-lookup"><span data-stu-id="82bf1-109">*Alpha* indicates a string of alphabetical letters.</span></span>

  - <span data-ttu-id="82bf1-110">*Digit*指示数字字符串。</span><span class="sxs-lookup"><span data-stu-id="82bf1-110">*Digit* indicates a string of numbers.</span></span>

  - <span data-ttu-id="82bf1-111">*Unicode-digit*指示 unicode 数字的字符串。</span><span class="sxs-lookup"><span data-stu-id="82bf1-111">*Unicode-digit* indicates a string of unicode digits.</span></span>

<span data-ttu-id="82bf1-112">所有其他术语是文字。</span><span class="sxs-lookup"><span data-stu-id="82bf1-112">All other terms are literals.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="82bf1-113">术语</span><span class="sxs-lookup"><span data-stu-id="82bf1-113">Term</span></span></p></th>
<th><p><span data-ttu-id="82bf1-114">定义</span><span class="sxs-lookup"><span data-stu-id="82bf1-114">Definition</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-115">&lt;shape 命令&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-115">&lt;shape-command&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-116">形状 [&lt;表 exp&gt; [[AS]&lt;别名&gt;]] [&lt;形状动作&gt;]</span><span class="sxs-lookup"><span data-stu-id="82bf1-116">SHAPE [&lt;table-exp&gt; [[AS] &lt;alias&gt;]][&lt;shape-action&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-117">&lt;表 exp&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-117">&lt;table-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-118">{&lt;提供程序命令文本&gt;} |</span><span class="sxs-lookup"><span data-stu-id="82bf1-118">{&lt;provider-command-text&gt;} |</span></span><br />
<span data-ttu-id="82bf1-119">(&lt;shape 命令&gt;) |</span><span class="sxs-lookup"><span data-stu-id="82bf1-119">(&lt;shape-command&gt;) |</span></span><br />
<span data-ttu-id="82bf1-120">表&lt;带引号的名称&gt; |</span><span class="sxs-lookup"><span data-stu-id="82bf1-120">TABLE &lt;quoted-name&gt; |</span></span><br />
<span data-ttu-id="82bf1-121">&lt;带引号的名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-121">&lt;quoted-name&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-122">&lt;形状操作&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-122">&lt;shape-action&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-123">APPEND&lt;失真字段列表&gt; |</span><span class="sxs-lookup"><span data-stu-id="82bf1-123">APPEND &lt;aliased-field-list&gt; |</span></span></p>
<p><span data-ttu-id="82bf1-124">计算&lt;失真字段列表&gt;[BY&lt;字段列表&gt;]</span><span class="sxs-lookup"><span data-stu-id="82bf1-124">COMPUTE &lt;aliased-field-list&gt; [BY &lt;field-list&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-125">&lt;失真字段列表&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-125">&lt;aliased-field-list&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-126">&lt;失真字段&gt;[， &lt;...失真字段&gt;]</span><span class="sxs-lookup"><span data-stu-id="82bf1-126">&lt;aliased-field&gt; [, &lt;aliased-field...&gt;]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-127">&lt;失真字段&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-127">&lt;aliased-field&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-128">&lt;字段 exp&gt; [[AS]&lt;别名&gt;]</span><span class="sxs-lookup"><span data-stu-id="82bf1-128">&lt;field-exp&gt; [[AS] &lt;alias&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-129">&lt;字段 exp&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-129">&lt;field-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-130">(&lt;关系 exp&gt;) |</span><span class="sxs-lookup"><span data-stu-id="82bf1-130">(&lt;relation-exp&gt;) |</span></span></p>
<p><span data-ttu-id="82bf1-131">&lt;计算 exp&gt; |</span><span class="sxs-lookup"><span data-stu-id="82bf1-131">&lt;calculated-exp&gt; |</span></span></p>
<p><span data-ttu-id="82bf1-132">&lt;聚合 exp&gt; |</span><span class="sxs-lookup"><span data-stu-id="82bf1-132">&lt;aggregate-exp&gt; |</span></span></p>
<p><span data-ttu-id="82bf1-133">&lt;新 exp&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-133">&lt;new-exp&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-134">&lt;relation_exp&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-134">&lt;relation_exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-135">&lt;表 exp&gt; [[AS]&lt;别名&gt;]</span><span class="sxs-lookup"><span data-stu-id="82bf1-135">&lt;table-exp&gt; [[AS] &lt;alias&gt;]</span></span></p>
<p><span data-ttu-id="82bf1-136">&lt;表 exp&gt; [[AS]&lt;别名&gt;]</span><span class="sxs-lookup"><span data-stu-id="82bf1-136">&lt;table-exp&gt; [[AS] &lt;alias&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-137">&lt;关系黑列表&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-137">&lt;relation-cond-list&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-138">&lt;关系黑&gt;[，&lt;关系黑&gt;...]</span><span class="sxs-lookup"><span data-stu-id="82bf1-138">&lt;relation-cond&gt; [, &lt;relation-cond&gt;...]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-139">&lt;关系黑&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-139">&lt;relation-cond&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-140">&lt;字段名称&gt;收件人&lt;子 ref&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-140">&lt;field-name&gt; TO &lt;child-ref&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-141">&lt;子 ref&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-141">&lt;child-ref&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-142">&lt;字段名称&gt; |</span><span class="sxs-lookup"><span data-stu-id="82bf1-142">&lt;field-name&gt; |</span></span></p>
<p><span data-ttu-id="82bf1-143">参数&lt;param ref&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-143">PARAMETER &lt;param-ref&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-144">&lt;param ref&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-144">&lt;param-ref&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-145">&lt;号码&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-145">&lt;number&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-146">&lt;字段列表&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-146">&lt;field-list&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-147">&lt;字段名称&gt;[，&lt;字段名称&gt;]</span><span class="sxs-lookup"><span data-stu-id="82bf1-147">&lt;field-name&gt; [, &lt;field-name&gt;]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-148">&lt;聚合 exp&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-148">&lt;aggregate-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-149">SUM (&lt;限定-字段-name&gt;) |</span><span class="sxs-lookup"><span data-stu-id="82bf1-149">SUM(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="82bf1-150">平均 (&lt;限定-字段-name&gt;) |</span><span class="sxs-lookup"><span data-stu-id="82bf1-150">AVG(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="82bf1-151">MIN (&lt;限定-字段-name&gt;) |</span><span class="sxs-lookup"><span data-stu-id="82bf1-151">MIN(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="82bf1-152">最大值 (&lt;限定-字段-name&gt;) |</span><span class="sxs-lookup"><span data-stu-id="82bf1-152">MAX(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="82bf1-153">计数 (&lt;限定别名&gt; | &lt;限定名称&gt;) |</span><span class="sxs-lookup"><span data-stu-id="82bf1-153">COUNT(&lt;qualified-alias&gt; | &lt;qualified-name&gt;) |</span></span></p>
<p><span data-ttu-id="82bf1-154">STDEV (&lt;限定-字段-name&gt;) |</span><span class="sxs-lookup"><span data-stu-id="82bf1-154">STDEV(&lt;qualified-field-name&gt;) |</span></span></p>
<p><span data-ttu-id="82bf1-155">任何 (&lt;限定-字段-name&gt;)</span><span class="sxs-lookup"><span data-stu-id="82bf1-155">ANY(&lt;qualified-field-name&gt;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-156">&lt;计算 exp&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-156">&lt;calculated-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-157">CALC(&lt;expression&gt;)</span><span class="sxs-lookup"><span data-stu-id="82bf1-157">CALC(&lt;expression&gt;)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-158">&lt;限定字段名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-158">&lt;qualified-field-name&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-159">&lt;别名&gt;。[&lt;别名&gt;...]&lt;字段名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-159">&lt;alias&gt;.[&lt;alias&gt;...]&lt;field-name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-160">&lt;别名&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-160">&lt;alias&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-161">&lt;带引号的名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-161">&lt;quoted-name&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-162">&lt;字段名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-162">&lt;field-name&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-163">&lt;用引号括起来-name&gt; [[AS]&lt;别名&gt;]</span><span class="sxs-lookup"><span data-stu-id="82bf1-163">&lt;quoted-name&gt; [[AS] &lt;alias&gt;]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-164">&lt;带引号的名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-164">&lt;quoted-name&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-165">&quot;&lt;字符串&gt;&quot; |</span><span class="sxs-lookup"><span data-stu-id="82bf1-165">&quot;&lt;string&gt;&quot; |</span></span></p>
<p><span data-ttu-id="82bf1-166">&lt;字符串&gt;|</span><span class="sxs-lookup"><span data-stu-id="82bf1-166">'&lt;string&gt;' |</span></span></p>
<p><span data-ttu-id="82bf1-167">[&lt;字符串&gt;] |</span><span class="sxs-lookup"><span data-stu-id="82bf1-167">[&lt;string&gt;] |</span></span></p>
<p><span data-ttu-id="82bf1-168">&lt;名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-168">&lt;name&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-169">&lt;限定名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-169">&lt;qualified-name&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-170">别名 [.alias...]</span><span class="sxs-lookup"><span data-stu-id="82bf1-170">alias[.alias...]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-171">&lt;名称&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-171">&lt;name&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-172">alpha [alpha | 数字 | _ | # |: |...]</span><span class="sxs-lookup"><span data-stu-id="82bf1-172">alpha [ alpha | digit | _ | # | : | ...]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-173">&lt;号码&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-173">&lt;number&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-174">位数 [...数字]</span><span class="sxs-lookup"><span data-stu-id="82bf1-174">digit [digit...]</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-175">&lt;新 exp&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-175">&lt;new-exp&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-176">新&lt;字段类型&gt;[(&lt;号码&gt;[，&lt;号码&gt;])]</span><span class="sxs-lookup"><span data-stu-id="82bf1-176">NEW &lt;field-type&gt; [(&lt;number&gt; [, &lt;number&gt;])]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-177">&lt;字段类型&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-177">&lt;field-type&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-178">OLE DB 或 ADO 数据类型。</span><span class="sxs-lookup"><span data-stu-id="82bf1-178">An OLE DB or ADO data type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82bf1-179">&lt;字符串&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-179">&lt;string&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-180">unicode 字符 [unicode char。..]</span><span class="sxs-lookup"><span data-stu-id="82bf1-180">unicode-char [unicode-char...]</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82bf1-181">&lt;expression&gt;</span><span class="sxs-lookup"><span data-stu-id="82bf1-181">&lt;expression&gt;</span></span></p></td>
<td><p><span data-ttu-id="82bf1-182">Visual Basic for Applications 表达式，其操作数是在相同行中的其他非 CALC 列。</span><span class="sxs-lookup"><span data-stu-id="82bf1-182">A Visual Basic for Applications expression whose operands are other non-CALC columns in the same row.</span></span></p></td>
</tr>
</tbody>
</table>

