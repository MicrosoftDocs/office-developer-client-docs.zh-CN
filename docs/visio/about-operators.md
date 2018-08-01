---
title: 关于运算符
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251824
localization_priority: Normal
ms.assetid: 43128ea2-c0d9-c45f-31e6-768a80ae59b2
description: 您可以在公式中使用运算符来执行算术运算（加、减、乘等）或逻辑比较（大于、小于、等于等）。还可以使用括号括起表达式，以控制公式的求值顺序。使用运算符可以组合（连接）字符串。
ms.openlocfilehash: 3a14993ab317d19d0e4a8983e4714f587c235d57
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779608"
---
# <a name="about-operators"></a><span data-ttu-id="6d93d-105">关于运算符</span><span class="sxs-lookup"><span data-stu-id="6d93d-105">About Operators</span></span>

<span data-ttu-id="6d93d-p102">您可以在公式中使用运算符来执行算术运算（加、减、乘等）或逻辑比较（大于、小于、等于等）。还可以使用括号括起表达式，以控制公式的求值顺序。使用运算符可以组合（连接）字符串。</span><span class="sxs-lookup"><span data-stu-id="6d93d-p102">You can use operators in formulas to perform arithmetic operations (addition, subtraction, multiplication, and so on) or logical comparisons (greater than, less than, equal to, and so on). You also can control the order of evaluation in a formula by enclosing expressions in parentheses. Use the ampersand operator to combine (concatenate) character strings.</span></span>
  
<span data-ttu-id="6d93d-p103">当运算或函数需要特定的数据类型时，Microsoft Visio 会自动尝试转换数据类型。例如，乘法运算符需要数值参数，而 &（字符串连接）运算符需要字符串参数。如果参数不能被转换为所需的数据类型，Visio 会提供一个默认值。这种情况下各类型的默认值分别为：对数字而言是零，对布尔值而言是 FALSE，对字符串而言是 ""，等等。</span><span class="sxs-lookup"><span data-stu-id="6d93d-p103">Microsoft Visio automatically attempts to convert data types when an operation or function requires a specific type of data. For example, the multiplication operator requires numeric arguments, and the ampersand (string concatenation) operator requires string arguments. If the argument cannot be converted to the required data type, a default value is provided. The default value is the typed equivalent of nothing: zero for numbers, FALSE for Boolean values, "" for strings, and so on.</span></span>
  
<span data-ttu-id="6d93d-113">下表举例说明了表达式及其结果。</span><span class="sxs-lookup"><span data-stu-id="6d93d-113">The following table shows examples of expressions and their results.</span></span>
  
|<span data-ttu-id="6d93d-114">**Expression**</span><span class="sxs-lookup"><span data-stu-id="6d93d-114">**Expression**</span></span>|<span data-ttu-id="6d93d-115">**结果**</span><span class="sxs-lookup"><span data-stu-id="6d93d-115">**Result**</span></span>|<span data-ttu-id="6d93d-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="6d93d-116">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="6d93d-117">2 \* 5 &amp; "分"</span><span class="sxs-lookup"><span data-stu-id="6d93d-117">2 \* 5 &amp; " cents"</span></span>  <br/> | <span data-ttu-id="6d93d-118">"10 cents"</span><span class="sxs-lookup"><span data-stu-id="6d93d-118">"10 cents"</span></span>  <br/> | <span data-ttu-id="6d93d-119">&amp;运算符 （字符串连接） 需要字符串参数，因此 2 的数值计算结果\*5 被自动转换为字符串"10"。</span><span class="sxs-lookup"><span data-stu-id="6d93d-119">The &amp; operator (string concatenation) requires string arguments, so the numeric result of 2 \* 5 is automatically converted to the string "10".</span></span>  <br/> |
| <span data-ttu-id="6d93d-120">5 \* "2"</span><span class="sxs-lookup"><span data-stu-id="6d93d-120">5 \* "2"</span></span>  <br/> | <span data-ttu-id="6d93d-121">10</span><span class="sxs-lookup"><span data-stu-id="6d93d-121">10</span></span>  <br/> | <span data-ttu-id="6d93d-122">\*运算符 （乘法） 需要数值参数，所以字符串"2"被自动转换为等价的数字 2。</span><span class="sxs-lookup"><span data-stu-id="6d93d-122">The \* operator (multiplication) requires numeric arguments, so the string "2" is automatically converted to the equivalent number 2.</span></span>  <br/> |
| <span data-ttu-id="6d93d-123">5 \* "sheep"</span><span class="sxs-lookup"><span data-stu-id="6d93d-123">5 \* "sheep"</span></span>  <br/> | <span data-ttu-id="6d93d-124">0</span><span class="sxs-lookup"><span data-stu-id="6d93d-124">0</span></span>  <br/> | <span data-ttu-id="6d93d-125">\*运算符 （乘法） 需要数值参数，因此因为字符串"sheep"不能转换为数字，因此使用零作为其等价数值。</span><span class="sxs-lookup"><span data-stu-id="6d93d-125">The \* operator (multiplication) requires numeric arguments, so because the string "sheep" cannot be converted to a number, zero is used as its numeric equivalent.</span></span>  <br/> |
   
## <a name="arithmetic-operators"></a><span data-ttu-id="6d93d-126">算术运算符</span><span class="sxs-lookup"><span data-stu-id="6d93d-126">Arithmetic operators</span></span>

<span data-ttu-id="6d93d-p104">算术运算符对数字执行运算。加号 (+) 和减号 (-) 运算符可以作为单目运算符单独构成数字的符号。百分号运算符 (%) 也是一个单目运算符，它标识数字是一个百分比。</span><span class="sxs-lookup"><span data-stu-id="6d93d-p104">Arithmetic operators perform operations on numbers. The plus (+) and minus (-) operators can be used alone as unary operators to establish the sign of a number. The percent (%) operator is also a unary operator and identifies the number as a percentage.</span></span>
  
|<span data-ttu-id="6d93d-130">**运算符**</span><span class="sxs-lookup"><span data-stu-id="6d93d-130">**Operator**</span></span>|<span data-ttu-id="6d93d-131">**操作**</span><span class="sxs-lookup"><span data-stu-id="6d93d-131">**Action**</span></span>|<span data-ttu-id="6d93d-132">**示例**</span><span class="sxs-lookup"><span data-stu-id="6d93d-132">**Example**</span></span>|<span data-ttu-id="6d93d-133">**结果**</span><span class="sxs-lookup"><span data-stu-id="6d93d-133">**Result**</span></span>|
|:-----|:-----|:-----|:-----|
| +  <br/> | <span data-ttu-id="6d93d-134">单目加</span><span class="sxs-lookup"><span data-stu-id="6d93d-134">Unary plus</span></span>  <br/> | <span data-ttu-id="6d93d-135">+37</span><span class="sxs-lookup"><span data-stu-id="6d93d-135">+37</span></span>  <br/> | <span data-ttu-id="6d93d-136">37</span><span class="sxs-lookup"><span data-stu-id="6d93d-136">37</span></span>  <br/> |
| -  <br/> | <span data-ttu-id="6d93d-137">单目减</span><span class="sxs-lookup"><span data-stu-id="6d93d-137">Unary minus</span></span>  <br/> | <span data-ttu-id="6d93d-138">-37</span><span class="sxs-lookup"><span data-stu-id="6d93d-138">-37</span></span>  <br/> | <span data-ttu-id="6d93d-139">-37</span><span class="sxs-lookup"><span data-stu-id="6d93d-139">-37</span></span>  <br/> |
| %  <br/> | <span data-ttu-id="6d93d-140">单目百分比</span><span class="sxs-lookup"><span data-stu-id="6d93d-140">Unary percentage</span></span>  <br/> | <span data-ttu-id="6d93d-141">37%</span><span class="sxs-lookup"><span data-stu-id="6d93d-141">37%</span></span>  <br/> | <span data-ttu-id="6d93d-142">.37</span><span class="sxs-lookup"><span data-stu-id="6d93d-142">.37</span></span>  <br/> |
| ^  <br/> | <span data-ttu-id="6d93d-143">求幂</span><span class="sxs-lookup"><span data-stu-id="6d93d-143">Exponentiation</span></span>  <br/> | <span data-ttu-id="6d93d-144">5 ^ 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-144">5 ^ 2</span></span>  <br/> | <span data-ttu-id="6d93d-145">25</span><span class="sxs-lookup"><span data-stu-id="6d93d-145">25</span></span>  <br/> |
| \*  <br/> | <span data-ttu-id="6d93d-146">乘</span><span class="sxs-lookup"><span data-stu-id="6d93d-146">Multiplication</span></span>  <br/> | <span data-ttu-id="6d93d-147">5 \* 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-147">5 \* 2</span></span>  <br/> | <span data-ttu-id="6d93d-148">10</span><span class="sxs-lookup"><span data-stu-id="6d93d-148">10</span></span>  <br/> |
| /  <br/> | <span data-ttu-id="6d93d-149">除</span><span class="sxs-lookup"><span data-stu-id="6d93d-149">Division</span></span>  <br/> | <span data-ttu-id="6d93d-150">5 / 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-150">5 / 2</span></span>  <br/> | <span data-ttu-id="6d93d-151">2.5</span><span class="sxs-lookup"><span data-stu-id="6d93d-151">2.5</span></span>  <br/> |
| +  <br/> | <span data-ttu-id="6d93d-152">加</span><span class="sxs-lookup"><span data-stu-id="6d93d-152">Addition</span></span>  <br/> | <span data-ttu-id="6d93d-153">5 + 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-153">5 + 2</span></span>  <br/> | <span data-ttu-id="6d93d-154">7</span><span class="sxs-lookup"><span data-stu-id="6d93d-154">7</span></span>  <br/> |
| -  <br/> | <span data-ttu-id="6d93d-155">减</span><span class="sxs-lookup"><span data-stu-id="6d93d-155">Subtraction</span></span>  <br/> | <span data-ttu-id="6d93d-156">5-2</span><span class="sxs-lookup"><span data-stu-id="6d93d-156">5 - 2</span></span>  <br/> | <span data-ttu-id="6d93d-157">3</span><span class="sxs-lookup"><span data-stu-id="6d93d-157">3</span></span>  <br/> |
   
## <a name="comparison-operators"></a><span data-ttu-id="6d93d-158">比较运算符</span><span class="sxs-lookup"><span data-stu-id="6d93d-158">Comparison operators</span></span>

<span data-ttu-id="6d93d-p105">比较关系运算符用来建立逻辑表达式。逻辑表达式的结果为 TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="6d93d-p105">Comparison operators are used to construct logical expressions. A logical expression evaluates to either TRUE or FALSE.</span></span>
  
|<span data-ttu-id="6d93d-161">**运算符**</span><span class="sxs-lookup"><span data-stu-id="6d93d-161">**Operator**</span></span>|<span data-ttu-id="6d93d-162">**替代方法**</span><span class="sxs-lookup"><span data-stu-id="6d93d-162">**Alternative**</span></span>|<span data-ttu-id="6d93d-163">**操作**</span><span class="sxs-lookup"><span data-stu-id="6d93d-163">**Action**</span></span>|<span data-ttu-id="6d93d-164">**示例**</span><span class="sxs-lookup"><span data-stu-id="6d93d-164">**Example**</span></span>|<span data-ttu-id="6d93d-165">**结果**</span><span class="sxs-lookup"><span data-stu-id="6d93d-165">**Result**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
| \>  <br/> | <span data-ttu-id="6d93d-166">_GT_</span><span class="sxs-lookup"><span data-stu-id="6d93d-166">_GT_</span></span>  <br/> | <span data-ttu-id="6d93d-167">大于</span><span class="sxs-lookup"><span data-stu-id="6d93d-167">Greater than</span></span>  <br/> | <span data-ttu-id="6d93d-168">5 \> 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-168">5 \> 2</span></span>  <br/> | <span data-ttu-id="6d93d-169">TRUE</span><span class="sxs-lookup"><span data-stu-id="6d93d-169">TRUE</span></span>  <br/> |
| \<  <br/> | <span data-ttu-id="6d93d-170">_LT_</span><span class="sxs-lookup"><span data-stu-id="6d93d-170">_LT_</span></span>  <br/> | <span data-ttu-id="6d93d-171">小于</span><span class="sxs-lookup"><span data-stu-id="6d93d-171">Less than</span></span>  <br/> | <span data-ttu-id="6d93d-172">5 \< 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-172">5 \< 2</span></span>  <br/> | <span data-ttu-id="6d93d-173">FALSE</span><span class="sxs-lookup"><span data-stu-id="6d93d-173">FALSE</span></span>  <br/> |
| \>=  <br/> | <span data-ttu-id="6d93d-174">_GE_</span><span class="sxs-lookup"><span data-stu-id="6d93d-174">_GE_</span></span>  <br/> | <span data-ttu-id="6d93d-175">大于或等于</span><span class="sxs-lookup"><span data-stu-id="6d93d-175">Greater than or equal to</span></span>  <br/> | <span data-ttu-id="6d93d-176">5 \>= 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-176">5 \>= 2</span></span>  <br/> | <span data-ttu-id="6d93d-177">TRUE</span><span class="sxs-lookup"><span data-stu-id="6d93d-177">TRUE</span></span>  <br/> |
| \<=  <br/> | <span data-ttu-id="6d93d-178">_LE_</span><span class="sxs-lookup"><span data-stu-id="6d93d-178">_LE_</span></span>  <br/> | <span data-ttu-id="6d93d-179">小于或等于</span><span class="sxs-lookup"><span data-stu-id="6d93d-179">Less than or equal to</span></span>  <br/> | <span data-ttu-id="6d93d-180">5 \<= 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-180">5 \<= 2</span></span>  <br/> | <span data-ttu-id="6d93d-181">FALSE</span><span class="sxs-lookup"><span data-stu-id="6d93d-181">FALSE</span></span>  <br/> |
| =  <br/> | <span data-ttu-id="6d93d-182">_EQ_</span><span class="sxs-lookup"><span data-stu-id="6d93d-182">_EQ_</span></span>  <br/> | <span data-ttu-id="6d93d-183">等于</span><span class="sxs-lookup"><span data-stu-id="6d93d-183">Equal to</span></span>  <br/> | <span data-ttu-id="6d93d-184">5 = 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-184">5 = 2</span></span>  <br/> | <span data-ttu-id="6d93d-185">FALSE</span><span class="sxs-lookup"><span data-stu-id="6d93d-185">FALSE</span></span>  <br/> |
| \<\>  <br/> | <span data-ttu-id="6d93d-186">_NE_</span><span class="sxs-lookup"><span data-stu-id="6d93d-186">_NE_</span></span>  <br/> | <span data-ttu-id="6d93d-187">不等于</span><span class="sxs-lookup"><span data-stu-id="6d93d-187">Not equal to</span></span>  <br/> | <span data-ttu-id="6d93d-188">5 \< \> 2</span><span class="sxs-lookup"><span data-stu-id="6d93d-188">5 \<\> 2</span></span>  <br/> | <span data-ttu-id="6d93d-189">TRUE</span><span class="sxs-lookup"><span data-stu-id="6d93d-189">TRUE</span></span>  <br/> |
   
<span data-ttu-id="6d93d-190">符号的比较运算符 (\>， \<，依此类推) 是用于大多数比较的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="6d93d-190">The symbolic comparison operators (\>, \<, and so forth) are the best choice for most comparisons.</span></span> <span data-ttu-id="6d93d-191">替代运算符 （_GT_、 _LT_，等等） 执行确切比较 Visio 使用内部存储值的精度的完整 15 位数字。</span><span class="sxs-lookup"><span data-stu-id="6d93d-191">The alternative operators (_GT_, _LT_, and so forth) perform an exact comparison to the full 15 digits of precision that Visio uses to store values internally.</span></span>
  
<span data-ttu-id="6d93d-192">用替代运算符比较舍入后的或计算出的值时，在所有实际情况下计算结果都应为 TRUE 的表达式可能会返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="6d93d-192">When you compare rounded or calculated values by using the alternative operators, FALSE might be returned, when for all practical purposes the expression should evaluate to TRUE.</span></span>
  
<span data-ttu-id="6d93d-p107">用比较运算符比较文本字符串时，字符串首先被转换成数值。不能转换的文本字符串返回 0 值。因此，比较结果会发生变化，并可能得出意外结果。要执行标准的字符串比较，请使用 STRSAME 或 STRSAMEEX 函数。</span><span class="sxs-lookup"><span data-stu-id="6d93d-p107">When you use comparison operators to compare text strings, the strings are first converted into numeric values. Text strings that cannot be converted return a value of 0; therefore, comparisons vary and might not produce the results you expect. To do a standard string comparison, use the function STRSAME or STRSAMEEX.</span></span>
  
## <a name="order-of-evaluation"></a><span data-ttu-id="6d93d-196">求值顺序</span><span class="sxs-lookup"><span data-stu-id="6d93d-196">Order of evaluation</span></span>

<span data-ttu-id="6d93d-p108">当一个公式包含多个表达式时，按照运算执行的顺序对这些表达式求值。下表显示了 Visio 中运算符的求值顺序。</span><span class="sxs-lookup"><span data-stu-id="6d93d-p108">When a formula contains more than one expression, the expressions are evaluated in order according to the operation being performed. This table shows the order of evaluation of operators in Visio.</span></span>
  
|<span data-ttu-id="6d93d-199">**Order**</span><span class="sxs-lookup"><span data-stu-id="6d93d-199">**Order**</span></span>|<span data-ttu-id="6d93d-200">**操作**</span><span class="sxs-lookup"><span data-stu-id="6d93d-200">**Action**</span></span>|<span data-ttu-id="6d93d-201">**运算符**</span><span class="sxs-lookup"><span data-stu-id="6d93d-201">**Operator**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d93d-202">第一</span><span class="sxs-lookup"><span data-stu-id="6d93d-202">First</span></span>  <br/> |<span data-ttu-id="6d93d-203">取正</span><span class="sxs-lookup"><span data-stu-id="6d93d-203">Positive</span></span>  <br/> |<span data-ttu-id="6d93d-204">+（单目）</span><span class="sxs-lookup"><span data-stu-id="6d93d-204">+ (unary)</span></span>  <br/> |
||<span data-ttu-id="6d93d-205">取负</span><span class="sxs-lookup"><span data-stu-id="6d93d-205">Negative</span></span>  <br/> |<span data-ttu-id="6d93d-206">-（单目）</span><span class="sxs-lookup"><span data-stu-id="6d93d-206">- (unary)</span></span>  <br/> |
||<span data-ttu-id="6d93d-207">百分比</span><span class="sxs-lookup"><span data-stu-id="6d93d-207">Percent</span></span>  <br/> |<span data-ttu-id="6d93d-208">%（单目）</span><span class="sxs-lookup"><span data-stu-id="6d93d-208">% (unary)</span></span>  <br/> |
|<span data-ttu-id="6d93d-209">第二</span><span class="sxs-lookup"><span data-stu-id="6d93d-209">Second</span></span>  <br/> |<span data-ttu-id="6d93d-210">求幂</span><span class="sxs-lookup"><span data-stu-id="6d93d-210">Exponentiation</span></span>  <br/> |^  <br/> |
|<span data-ttu-id="6d93d-211">第三</span><span class="sxs-lookup"><span data-stu-id="6d93d-211">Third</span></span>  <br/> |<span data-ttu-id="6d93d-212">乘</span><span class="sxs-lookup"><span data-stu-id="6d93d-212">Multiplication</span></span>  <br/> |\*  <br/> |
||<span data-ttu-id="6d93d-213">部门</span><span class="sxs-lookup"><span data-stu-id="6d93d-213">Division</span></span>  <br/> |/  <br/> |
|<span data-ttu-id="6d93d-214">第四</span><span class="sxs-lookup"><span data-stu-id="6d93d-214">Fourth</span></span>  <br/> |<span data-ttu-id="6d93d-215">加</span><span class="sxs-lookup"><span data-stu-id="6d93d-215">Addition</span></span>  <br/> |+  <br/> |
||<span data-ttu-id="6d93d-216">减</span><span class="sxs-lookup"><span data-stu-id="6d93d-216">Subtraction</span></span>  <br/> |-  <br/> |
|<span data-ttu-id="6d93d-217">第五</span><span class="sxs-lookup"><span data-stu-id="6d93d-217">Fifth</span></span>  <br/> |<span data-ttu-id="6d93d-218">字符串连接</span><span class="sxs-lookup"><span data-stu-id="6d93d-218">String concatenation</span></span>  <br/> |&amp;  <br/> |
|<span data-ttu-id="6d93d-219">第六</span><span class="sxs-lookup"><span data-stu-id="6d93d-219">Sixth</span></span>  <br/> |<span data-ttu-id="6d93d-220">大于</span><span class="sxs-lookup"><span data-stu-id="6d93d-220">Greater than</span></span>  <br/> |<span data-ttu-id="6d93d-221">\>或 GT</span><span class="sxs-lookup"><span data-stu-id="6d93d-221">\> or GT</span></span>  <br/> |
||<span data-ttu-id="6d93d-222">大于或等于</span><span class="sxs-lookup"><span data-stu-id="6d93d-222">Greater than or equal to</span></span>  <br/> |<span data-ttu-id="6d93d-223">\>= 或 GE</span><span class="sxs-lookup"><span data-stu-id="6d93d-223">\>= or GE</span></span>  <br/> |
||<span data-ttu-id="6d93d-224">小于</span><span class="sxs-lookup"><span data-stu-id="6d93d-224">Less than</span></span>  <br/> |<span data-ttu-id="6d93d-225">\<或 LT</span><span class="sxs-lookup"><span data-stu-id="6d93d-225">\< or LT</span></span>  <br/> |
||<span data-ttu-id="6d93d-226">小于或等于</span><span class="sxs-lookup"><span data-stu-id="6d93d-226">Less than or equal to</span></span>  <br/> |<span data-ttu-id="6d93d-227">\<= 或 LE</span><span class="sxs-lookup"><span data-stu-id="6d93d-227">\<= or LE</span></span>  <br/> |
|<span data-ttu-id="6d93d-228">第七</span><span class="sxs-lookup"><span data-stu-id="6d93d-228">Seventh</span></span>  <br/> |<span data-ttu-id="6d93d-229">等于</span><span class="sxs-lookup"><span data-stu-id="6d93d-229">Equal</span></span>  <br/> |<span data-ttu-id="6d93d-230">= 或 EQ</span><span class="sxs-lookup"><span data-stu-id="6d93d-230">= or EQ</span></span>  <br/> |
||<span data-ttu-id="6d93d-231">不等于</span><span class="sxs-lookup"><span data-stu-id="6d93d-231">Not equal</span></span>  <br/> |<span data-ttu-id="6d93d-232">\<\>或 NE</span><span class="sxs-lookup"><span data-stu-id="6d93d-232">\<\> or NE</span></span>  <br/> |
   
<span data-ttu-id="6d93d-p109">您可以使用括号将表达式括起来以改变求值顺序。Visio 首先从左至右对括号内的表达式求值。例如：</span><span class="sxs-lookup"><span data-stu-id="6d93d-p109">You can change the order of evaluation by enclosing expressions in parentheses. Visio evaluates expressions within parentheses first, from left to right. For example:</span></span>
  
<span data-ttu-id="6d93d-236">4 + 5 \* 6 = 4 + 30 = 34</span><span class="sxs-lookup"><span data-stu-id="6d93d-236">4 + 5 \* 6 = 4 + 30 = 34</span></span>
  
<span data-ttu-id="6d93d-237">(4 + 5)\* 6 = 9 \* 6 = 54</span><span class="sxs-lookup"><span data-stu-id="6d93d-237">(4 + 5) \* 6 = 9 \* 6 = 54</span></span>
  
<span data-ttu-id="6d93d-238">如果括号中的表达式是嵌套的，则最先计算最里层括号内的表达式。</span><span class="sxs-lookup"><span data-stu-id="6d93d-238">If expressions in parentheses are nested, the expression in the innermost set of parentheses is evaluated first.</span></span>
  
## <a name="ampersand-operator"></a><span data-ttu-id="6d93d-239">& 运算符</span><span class="sxs-lookup"><span data-stu-id="6d93d-239">Ampersand operator</span></span>

<span data-ttu-id="6d93d-p110">& 运算符返回一个新的字符串。您可以用 & 运算符创建复合词或短语。语法如下：</span><span class="sxs-lookup"><span data-stu-id="6d93d-p110">The ampersand operator returns a new character string. You can create compound words and phrases using the ampersand operator. Use the following syntax:</span></span>
  
<span data-ttu-id="6d93d-243">"string1" &amp; "string2"</span><span class="sxs-lookup"><span data-stu-id="6d93d-243">"string1" &amp; "string2"</span></span>
  
 <span data-ttu-id="6d93d-244">**示例**</span><span class="sxs-lookup"><span data-stu-id="6d93d-244">**Example**</span></span>
  
<span data-ttu-id="6d93d-245">"dog" &amp; "house"返回"doghouse"</span><span class="sxs-lookup"><span data-stu-id="6d93d-245">"dog" &amp; "house" returns "doghouse"</span></span>
  

