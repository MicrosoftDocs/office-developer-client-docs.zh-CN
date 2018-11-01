---
title: 在字符串比较中使用通配符
TOCTitle: Using Wildcard Characters in String Comparisons
ms:assetid: 37dda2b8-c710-4f73-bb2a-76a1348c42fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192499(v=office.15)
ms:contentKeyID: 48544205
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3c26b5e0a7e5448340cded61717ad27fb68aa827
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869622"
---
# <a name="using-wildcard-characters-in-string-comparisons"></a><span data-ttu-id="d6070-102">在字符串比较中使用通配符</span><span class="sxs-lookup"><span data-stu-id="d6070-102">Using Wildcard Characters in String Comparisons</span></span>


<span data-ttu-id="d6070-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d6070-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d6070-p101">内置的模式匹配方法提供了一个用于字符串比较的通用工具。下表中展示了可以用于 **Like** 运算符的通配符，以及与它们匹配的数字和字符串。</span><span class="sxs-lookup"><span data-stu-id="d6070-p101">Built-in pattern matching provides a versatile tool for making string comparisons. The following table shows the wildcard characters you can use with the **Like** operator and the number of digits or strings they match.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d6070-106">Pattern<em>中</em>的字符</span><span class="sxs-lookup"><span data-stu-id="d6070-106">Character(s) in <em>pattern</em></span></span></p></th>
<th><p><span data-ttu-id="d6070-107"><em>expression</em> 中的匹配项</span><span class="sxs-lookup"><span data-stu-id="d6070-107">Matches in <em>expression</em></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6070-p102">? 或  _（下划线）</span><span class="sxs-lookup"><span data-stu-id="d6070-p102">? or _ (underscore)</span></span></p></td>
<td><p><span data-ttu-id="d6070-110">任意单个字符</span><span class="sxs-lookup"><span data-stu-id="d6070-110">Any single character</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6070-111">\*或 %</span><span class="sxs-lookup"><span data-stu-id="d6070-111">\* or %</span></span></p></td>
<td><p><span data-ttu-id="d6070-112">零个或多个字符</span><span class="sxs-lookup"><span data-stu-id="d6070-112">Zero or more characters</span></span></p></td>
</tr>
<tr class="odd">
<td><p>#</p></td>
<td><p><span data-ttu-id="d6070-113">任何单个数字 (0 - 9)</span><span class="sxs-lookup"><span data-stu-id="d6070-113">Any single digit (0 – 9)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6070-114">[<em>charlist</em>]</span><span class="sxs-lookup"><span data-stu-id="d6070-114">[<em>charlist</em>]</span></span></p></td>
<td><p><span data-ttu-id="d6070-115"><em>charlist</em> 中的任何单个字符</span><span class="sxs-lookup"><span data-stu-id="d6070-115">Any single character in <em>charlist</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p>[!<em>charlist</em>]</p></td>
<td><p><span data-ttu-id="d6070-117">不在 <em>charlist</em> 中的任何单个字符</span><span class="sxs-lookup"><span data-stu-id="d6070-117">Any single character not in <em>charlist</em></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6070-118">您可以使用一组一个或多个字符 (*charlist*) 括在方括号 (\[ \]) 以匹配*表达式*和*charlist*中的任意单个字符可以包括几乎任何中字符的 ANSI 字符集字符设置，包括数字。</span><span class="sxs-lookup"><span data-stu-id="d6070-118">You can use a group of one or more characters (*charlist*) enclosed in brackets (\[ \]) to match any single character in *expression,* and *charlist* can include almost any characters in the ANSI character set, including digits.</span></span> <span data-ttu-id="d6070-119">您可以使用特殊字符打开括号 (\[ )、 问号 (?)、 数字记号 (\#)，和星号 (\*) 自身进行匹配直接才括在方括号内。</span><span class="sxs-lookup"><span data-stu-id="d6070-119">You can use the special characters opening bracket (\[ ), question mark (?), number sign (\#), and asterisk (\*) to match themselves directly only if enclosed in brackets.</span></span> <span data-ttu-id="d6070-120">不能使用右括号 ( \]) 在某个组将匹配本身，但您可以使用它在组外作为单个字符。</span><span class="sxs-lookup"><span data-stu-id="d6070-120">You cannot use the closing bracket ( \]) within a group to match itself, but you can use it outside a group as an individual character.</span></span>

<span data-ttu-id="d6070-121">括在方括号中的字符的简单列表，除了*charlist*可以通过使用连字符 （-） 分隔上限和下限范围的指定范围的字符。</span><span class="sxs-lookup"><span data-stu-id="d6070-121">In addition to a simple list of characters enclosed in brackets, *charlist* can specify a range of characters by using a hyphen (-) to separate the upper and lower bounds of the range.</span></span> <span data-ttu-id="d6070-122">例如，使用\[A-Z\] *模式*如果*表达式*中的相应字符位置包含任何范围 A 到 Z 中大写字母匹配的结果中。没有分隔的范围可以包含在方括号中的多个区域。</span><span class="sxs-lookup"><span data-stu-id="d6070-122">For example, using \[A-Z\] in *pattern* results in a match if the corresponding character position in *expression* contains any of the uppercase letters in the range A through Z. You can include multiple ranges within the brackets without delimiting the ranges.</span></span> <span data-ttu-id="d6070-123">例如， \[a-zA-Z0-9\]匹配任何字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="d6070-123">For example, \[a-zA-Z0-9\] matches any alphanumeric character.</span></span>

<span data-ttu-id="d6070-124">请注意，务必 ANSI SQL 通配符 （%） 和 (\_) 才可用与 Microsoft® jet 4.X 和 Microsoft OLE DB Provider for Jet。</span><span class="sxs-lookup"><span data-stu-id="d6070-124">It is important to note that the ANSI SQL wildcards (%) and (\_) are only available with Microsoft® Jet version 4.X and the Microsoft OLE DB Provider for Jet.</span></span> <span data-ttu-id="d6070-125">如果用于 Microsoft Access 或 DAO，则被视为文本。</span><span class="sxs-lookup"><span data-stu-id="d6070-125">They will be treated as literals if used through Microsoft Access or DAO.</span></span>

<span data-ttu-id="d6070-126">用于模式匹配的其他重要规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6070-126">Other important rules for pattern matching include the following:</span></span>

  - <span data-ttu-id="d6070-127">感叹号 (\!) *charlist*意味着除了*charlist 外*的那些*表达式*中发现的任何字符进行匹配的开头。</span><span class="sxs-lookup"><span data-stu-id="d6070-127">An exclamation mark (\!) at the beginning of *charlist* means that a match is made if any character except those in *charlist* are found in *expression*.</span></span> <span data-ttu-id="d6070-128">感叹号用在方括号外面时，将与自身匹配。</span><span class="sxs-lookup"><span data-stu-id="d6070-128">When used outside brackets, the exclamation mark matches itself.</span></span>

  - <span data-ttu-id="d6070-129">您可以使用连字符 （-） 开头 （感叹号之后如果使用了） 或末尾的*字符列表*匹配本身。</span><span class="sxs-lookup"><span data-stu-id="d6070-129">You can use the hyphen (-) either at the beginning (after an exclamation mark if one is used) or at the end of *charlist* to match itself.</span></span> <span data-ttu-id="d6070-130">如果用于任何其他位置，则标识 ANSI 字符的范围。</span><span class="sxs-lookup"><span data-stu-id="d6070-130">In any other location, the hyphen identifies a range of ANSI characters.</span></span>

  - <span data-ttu-id="d6070-131">指定一系列字符时，这些字符必须以升序排序次序显示（A-Z 或 0-100）。</span><span class="sxs-lookup"><span data-stu-id="d6070-131">When you specify a range of characters, the characters must appear in ascending sort order (A-Z or 0-100).</span></span> <span data-ttu-id="d6070-132">\[A 到 Z\]是有效的模式，但\[Z 到 A\]不是。</span><span class="sxs-lookup"><span data-stu-id="d6070-132">\[A-Z\] is a valid pattern, but \[Z-A\] is not.</span></span>

  - <span data-ttu-id="d6070-133">字符序列\[\]将被忽略;它被视为一个零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="d6070-133">The character sequence \[ \] is ignored; it is considered to be a zero-length string ("").</span></span>

