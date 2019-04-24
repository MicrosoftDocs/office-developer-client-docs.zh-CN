---
title: 在字符串比较中使用通配符
TOCTitle: Using wildcard characters in string comparisons
ms:assetid: 37dda2b8-c710-4f73-bb2a-76a1348c42fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192499(v=office.15)
ms:contentKeyID: 48544205
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e6a013865b9615701b1d99678fc2392e0a896c54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32305934"
---
# <a name="using-wildcard-characters-in-string-comparisons"></a><span data-ttu-id="6dfb0-102">在字符串比较中使用通配符</span><span class="sxs-lookup"><span data-stu-id="6dfb0-102">Using wildcard characters in string comparisons</span></span>

<span data-ttu-id="6dfb0-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6dfb0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6dfb0-p101">内置的模式匹配方法提供了一个用于字符串比较的通用工具。下表中展示了可以用于 **Like** 运算符的通配符，以及与它们匹配的数字和字符串。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-p101">Built-in pattern matching provides a versatile tool for making string comparisons. The following table shows the wildcard characters you can use with the **Like** operator and the number of digits or strings they match.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6dfb0-106"><em>pattern</em> 中的字符</span><span class="sxs-lookup"><span data-stu-id="6dfb0-106">Character(s) in <em>pattern</em></span></span></p></th>
<th><p><span data-ttu-id="6dfb0-107"><em>expression</em> 中的匹配项</span><span class="sxs-lookup"><span data-stu-id="6dfb0-107">Matches in <em>expression</em></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dfb0-p102">? 或  _（下划线）</span><span class="sxs-lookup"><span data-stu-id="6dfb0-p102">? or _ (underscore)</span></span></p></td>
<td><p><span data-ttu-id="6dfb0-110">任意单个字符</span><span class="sxs-lookup"><span data-stu-id="6dfb0-110">Any single character</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dfb0-111">\*和</span><span class="sxs-lookup"><span data-stu-id="6dfb0-111">\* or %</span></span></p></td>
<td><p><span data-ttu-id="6dfb0-112">零个或多个字符</span><span class="sxs-lookup"><span data-stu-id="6dfb0-112">Zero or more characters</span></span></p></td>
</tr>
<tr class="odd">
<td><p>#</p></td>
<td><p><span data-ttu-id="6dfb0-113">任何单个数字 (0 - 9)</span><span class="sxs-lookup"><span data-stu-id="6dfb0-113">Any single digit (0 – 9)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dfb0-114">[<em>charlist</em>]</span><span class="sxs-lookup"><span data-stu-id="6dfb0-114">[<em>charlist</em>]</span></span></p></td>
<td><p><span data-ttu-id="6dfb0-115">在 <em>charlist</em> 中的任何单个字符。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-115">Any single character in <em>charlist</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p>[!<em>charlist</em>]</p></td>
<td><p><span data-ttu-id="6dfb0-117">不在 <em>charlist</em> 中的任何单个字符。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-117">Any single character not in <em>charlist</em></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6dfb0-118">可以使用括在方括号 (\[ \]) 中的一个或多个字符 (*charlist*) 组成的组, 以匹配表达式中的任何单个字符 *,* 并且*charlist*可以包含 ANSI 字符集中的几乎所有字符, 包括进制.</span><span class="sxs-lookup"><span data-stu-id="6dfb0-118">You can use a group of one or more characters (*charlist*) enclosed in brackets (\[ \]) to match any single character in *expression,* and *charlist* can include almost any characters in the ANSI character set, including digits.</span></span> <span data-ttu-id="6dfb0-119">您可以使用左括号 (\[ )、问号 (?)、数字符号 (\#) 和星号 (\*) 等特殊字符仅当括在方括号中时才直接与自身匹配。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-119">You can use the special characters opening bracket (\[ ), question mark (?), number sign (\#), and asterisk (\*) to match themselves directly only if enclosed in brackets.</span></span> <span data-ttu-id="6dfb0-120">不能在组中使用右\]括号 () 来匹配自身, 但可以将其作为单个字符用于组之外。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-120">You cannot use the closing bracket ( \]) within a group to match itself, but you can use it outside a group as an individual character.</span></span>

<span data-ttu-id="6dfb0-121">除了括在方括号中的简单字符列表之外, *charlist*可以通过使用连字符 (-) 分隔范围的上限和下限来指定字符的范围。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-121">In addition to a simple list of characters enclosed in brackets, *charlist* can specify a range of characters by using a hyphen (-) to separate the upper and lower bounds of the range.</span></span> <span data-ttu-id="6dfb0-122">例如, 如果*表达式*中的对应\]字符位置包含从 A 到 Z 范围内的任何大写字母, 则在*模式*中使用\[a-z 将导致匹配。可以在括号中包含多个区域, 而无需界定区域。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-122">For example, using \[A-Z\] in *pattern* results in a match if the corresponding character position in *expression* contains any of the uppercase letters in the range A through Z. You can include multiple ranges within the brackets without delimiting the ranges.</span></span> <span data-ttu-id="6dfb0-123">例如, \[Z0-9\]匹配任何字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-123">For example, \[a-zA-Z0-9\] matches any alphanumeric character.</span></span>

<span data-ttu-id="6dfb0-124">需要注意的重要一点是, ANSI SQL 通配符 (%)和 (\_) 仅适用于 microsoft jet 版本 4. X 和 microsoft OLE DB Provider for Jet。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-124">It is important to note that the ANSI SQL wildcards (%) and (\_) are only available with Microsoft Jet version 4.X and the Microsoft OLE DB Provider for Jet.</span></span> <span data-ttu-id="6dfb0-125">如果用于 Microsoft Access 或 DAO，则被视为文本。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-125">They will be treated as literals if used through Microsoft Access or DAO.</span></span>

<span data-ttu-id="6dfb0-126">用于模式匹配的其他重要规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="6dfb0-126">Other important rules for pattern matching include the following:</span></span>

- <span data-ttu-id="6dfb0-127">*charlist*开头的感叹号\!() 表示在*expression*中发现除*charlist*中的字符之外的任何字符时进行匹配。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-127">An exclamation mark (\!) at the beginning of *charlist* means that a match is made if any character except those in *charlist* are found in *expression*.</span></span> <span data-ttu-id="6dfb0-128">感叹号用在方括号外面时，将与自身匹配。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-128">When used outside brackets, the exclamation mark matches itself.</span></span>

- <span data-ttu-id="6dfb0-p107">可以将连字符 (-) 用于 *charlist* 的开头（如果用了感叹号，则放在感叹号之后）或末尾以便与其自身匹配。如果用于任何其他位置，则标识 ANSI 字符的范围。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-p107">You can use the hyphen (-) either at the beginning (after an exclamation mark if one is used) or at the end of *charlist* to match itself. In any other location, the hyphen identifies a range of ANSI characters.</span></span>

- <span data-ttu-id="6dfb0-131">指定一系列字符时，这些字符必须以升序排序次序显示（A-Z 或 0-100）。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-131">When you specify a range of characters, the characters must appear in ascending sort order (A-Z or 0-100).</span></span> <span data-ttu-id="6dfb0-132">\[a-z\]是有效的模式, 但\[Z-a\]不是。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-132">\[A-Z\] is a valid pattern, but \[Z-A\] is not.</span></span>

- <span data-ttu-id="6dfb0-133">忽略该字符\[ \]序列;它被视为零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="6dfb0-133">The character sequence \[ \] is ignored; it is considered to be a zero-length string ("").</span></span>

