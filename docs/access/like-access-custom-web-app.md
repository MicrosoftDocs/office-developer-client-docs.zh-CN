---
title: 像 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: decdd8fc-2184-4d97-b918-3ef6ab1ab40b
description: 确定特定字符串是否与指定的模式匹配。 模式可以包含常规字符和通配符。 模式匹配时，常规字符必须完全匹配字符串中指定的字符。 但是，通配符可以与字符串的任意部分相匹配。 使用通配符可使 LIKE 运算符比使用 = 更灵活和 ！ = 字符串比较运算符。
ms.openlocfilehash: d3224647c621b05a08bdc863939d0cccae214463
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773487"
---
# <a name="like-access-custom-web-app"></a><span data-ttu-id="22a80-107">像 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="22a80-107">LIKE (Access custom web app)</span></span>

<span data-ttu-id="22a80-108">确定特定字符串是否与指定的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="22a80-108">Determines whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="22a80-109">模式可以包含常规字符和通配符。</span><span class="sxs-lookup"><span data-stu-id="22a80-109">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="22a80-110">模式匹配时，常规字符必须完全匹配字符串中指定的字符。</span><span class="sxs-lookup"><span data-stu-id="22a80-110">During pattern matching, regular characters must exactly match the characters specified in the character string.</span></span> <span data-ttu-id="22a80-111">但是，通配符可以与字符串的任意部分相匹配。</span><span class="sxs-lookup"><span data-stu-id="22a80-111">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="22a80-112">使用通配符可使**LIKE**运算符比使用 = 更灵活和 ！ = 字符串比较运算符。</span><span class="sxs-lookup"><span data-stu-id="22a80-112">Using wildcard characters makes the **LIKE** operator more flexible than using the = and != string comparison operators.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="22a80-p103">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="22a80-p103">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="22a80-115">语法</span><span class="sxs-lookup"><span data-stu-id="22a80-115">Syntax</span></span>

 <span data-ttu-id="22a80-116">*表达式* [NOT]**像***模式* [转义*EscapeChar* ]</span><span class="sxs-lookup"><span data-stu-id="22a80-116">*Expression*  [ NOT ] **LIKE** *Pattern*  [ ESCAPE  *EscapeChar*  ]</span></span> 
  
<span data-ttu-id="22a80-117">**LIKE**运算符包含以下参数</span><span class="sxs-lookup"><span data-stu-id="22a80-117">The **LIKE** operator contains the following arguments</span></span> 
  
|<span data-ttu-id="22a80-118">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="22a80-118">**Argument name**</span></span>|<span data-ttu-id="22a80-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="22a80-119">**Required**</span></span>|<span data-ttu-id="22a80-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="22a80-120">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="22a80-121">*Expression*</span><span class="sxs-lookup"><span data-stu-id="22a80-121">*Expression*</span></span>  <br/> |<span data-ttu-id="22a80-122">是</span><span class="sxs-lookup"><span data-stu-id="22a80-122">Yes</span></span>  <br/> |<span data-ttu-id="22a80-123">一个有效表达式。</span><span class="sxs-lookup"><span data-stu-id="22a80-123">A valid expression.</span></span>  <br/> |
| <span data-ttu-id="22a80-124">*Pattern*</span><span class="sxs-lookup"><span data-stu-id="22a80-124">*Pattern*</span></span>  <br/> |<span data-ttu-id="22a80-125">是</span><span class="sxs-lookup"><span data-stu-id="22a80-125">Yes</span></span>  <br/> |<span data-ttu-id="22a80-126">要在*表达式*中搜索特定字符串。</span><span class="sxs-lookup"><span data-stu-id="22a80-126">The specific string of characters to search for in  *Expression*  .</span></span> <span data-ttu-id="22a80-127">可以包含通配符字符。</span><span class="sxs-lookup"><span data-stu-id="22a80-127">Can include wildcard characters.</span></span> <span data-ttu-id="22a80-128">引用一组有效通配符字符的备注。</span><span class="sxs-lookup"><span data-stu-id="22a80-128">Refer to the Remarks for a list of valid wildcard characters.</span></span>  <br/> |
| <span data-ttu-id="22a80-129">*EscapeChar*</span><span class="sxs-lookup"><span data-stu-id="22a80-129">*EscapeChar*</span></span>  <br/> |<span data-ttu-id="22a80-130">否</span><span class="sxs-lookup"><span data-stu-id="22a80-130">No</span></span>  <br/> |<span data-ttu-id="22a80-131">应解释通配符放置通配符来指示前面的字符，为常规字符，而不是通配符。</span><span class="sxs-lookup"><span data-stu-id="22a80-131">A character that is put in front of a wildcard character to indicate that the wildcard should be interpreted as a regular character and not as a wildcard.</span></span>  <span data-ttu-id="22a80-132">*EscapeChar*是没有默认值和计算结果必须为只有一个字符的字符表达式。</span><span class="sxs-lookup"><span data-stu-id="22a80-132">*EscapeChar*  is a character expression that has no default and must evaluate to only one character.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="22a80-133">备注</span><span class="sxs-lookup"><span data-stu-id="22a80-133">Remarks</span></span>

<span data-ttu-id="22a80-134">下表包含有效的*模式*参数中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="22a80-134">The following table contains the wildcard characters that are valid for use in the  *Pattern*  argument.</span></span> 
  
|<span data-ttu-id="22a80-135">**通配符**</span><span class="sxs-lookup"><span data-stu-id="22a80-135">**Wildcard character**</span></span>|<span data-ttu-id="22a80-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="22a80-136">**Description**</span></span>|<span data-ttu-id="22a80-137">**示例**</span><span class="sxs-lookup"><span data-stu-id="22a80-137">**Example**</span></span>|
|:-----|:-----|:-----|
|%  <br/> |<span data-ttu-id="22a80-138">零个或多个字符的任意字符串。</span><span class="sxs-lookup"><span data-stu-id="22a80-138">Any string of zero or more characters.</span></span>  <br/> | <span data-ttu-id="22a80-139">*其中 title '%计算机 %' 像*查找的单词计算机的所有书名任意位置中书籍标题。</span><span class="sxs-lookup"><span data-stu-id="22a80-139">*WHERE title LIKE '%computer%'*  finds all book titles with the word 'computer' anywhere in the book title.</span></span>  <br/> |
|<span data-ttu-id="22a80-140">_（下划线字符）</span><span class="sxs-lookup"><span data-stu-id="22a80-140">_ (underscore)</span></span>  <br/> |<span data-ttu-id="22a80-141">任意单个字符。</span><span class="sxs-lookup"><span data-stu-id="22a80-141">Any single character.</span></span>  <br/> | <span data-ttu-id="22a80-142">*像 _ean WHERE au_fname*查找 ean （Dean、 Sean，等等） 结尾的所有四个字母第一个名称。</span><span class="sxs-lookup"><span data-stu-id="22a80-142">*WHERE au_fname LIKE '_ean'*  finds all four-letter first names that end with ean (Dean, Sean, and so on).</span></span>  <br/> |
|<span data-ttu-id="22a80-143">[]</span><span class="sxs-lookup"><span data-stu-id="22a80-143"></span></span>  <br/> |<span data-ttu-id="22a80-144">任何单个字符指定区域 ([a-f]) 中或设置 (例如 [abcdef])。</span><span class="sxs-lookup"><span data-stu-id="22a80-144">Any single character within the specified range ([a-f]) or set ([abcdef]).</span></span>  <br/> | <span data-ttu-id="22a80-145">*位置 au_lname 类似 [C-P] arsen*查找创作姓氏结尾 arsen 和启动之间有任意单个字符 C 和 P，例如 Carsen，Larsen，Karsen，等等。</span><span class="sxs-lookup"><span data-stu-id="22a80-145">*WHERE au_lname LIKE '[C-P]arsen'*  finds author last names ending with arsen and starting with any single character between C and P, for example Carsen, Larsen, Karsen, and so on.</span></span>  <br/> |
|<span data-ttu-id="22a80-146">[^]</span><span class="sxs-lookup"><span data-stu-id="22a80-146">[^]</span></span>  <br/> |<span data-ttu-id="22a80-147">任何单个字符不在指定范围内的 ([^ 为 a-f]) 或设置 ([^ abcdef])。</span><span class="sxs-lookup"><span data-stu-id="22a80-147">Any single character not within the specified range ([^a-f]) or set ([^abcdef]).</span></span>  <br/> | <span data-ttu-id="22a80-148">*如位置 au_lname de [^ l] %'* 所有作者开头 de 和以下号不 l 的最后一个姓名。</span><span class="sxs-lookup"><span data-stu-id="22a80-148">*WHERE au_lname LIKE 'de[^l]%'*  all author last names starting with de and where the following letter is not l.</span></span>  <br/> |
   
<span data-ttu-id="22a80-149">时使用**如**执行字符串比较，模式字符串中的所有字符都都有意义。</span><span class="sxs-lookup"><span data-stu-id="22a80-149">When you perform string comparisons by using **LIKE**, all characters in the pattern string are significant.</span></span> <span data-ttu-id="22a80-150">这包括前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="22a80-150">This includes leading or trailing spaces.</span></span> <span data-ttu-id="22a80-151">如果要在查询中的比较返回所有行，**如**字符串 abc (abc 跟一个空格)，则不返回的行顺序的列的值是 abc (abc 后没有空格)。</span><span class="sxs-lookup"><span data-stu-id="22a80-151">If a comparison in a query is to return all rows with a string **LIKE** 'abc ' (abc followed by a single space), a row in which the value of that column is abc (abc without a space) is not returned.</span></span> <span data-ttu-id="22a80-152">但是，向其匹配模式，该表达式中的尾随空格将被忽略。</span><span class="sxs-lookup"><span data-stu-id="22a80-152">However, trailing blanks, in the expression to which the pattern is matched, are ignored.</span></span> <span data-ttu-id="22a80-153">如果在查询中的比较是所有一起返回行**类似**的字符串 abc (不带空格的 abc)，则返回所有行的开头 abc 和具有零个或多个尾随空格。</span><span class="sxs-lookup"><span data-stu-id="22a80-153">If a comparison in a query is to return all rows with the string **LIKE** 'abc' (abc without a space), all rows that start with abc and have zero or more trailing blanks are returned.</span></span> 
  
<span data-ttu-id="22a80-154">如果任一参数不是字符串数据类型，它转换为 string 数据类型，如果可能。</span><span class="sxs-lookup"><span data-stu-id="22a80-154">If any one of the arguments is not of a string data type, it is converted to a string data type, if it is possible.</span></span>
  

