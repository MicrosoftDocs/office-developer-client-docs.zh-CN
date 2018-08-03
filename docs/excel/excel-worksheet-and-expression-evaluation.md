---
title: Excel 工作表和表达式计算
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- expression evaluation [excel 2007],errors in worksheets [Excel 2007],long Unicode strings [Excel 2007],evaluating expressions [Excel 2007],evaluating worksheets [Excel 2007],worksheet evaluation [Excel 2007],worksheet errors [Excel 2007]
localization_priority: Normal
ms.assetid: 47b46a7d-6cfb-4f5b-946d-e0164d18512a
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 543ff7fcbc88253dafd7fc6e7000bf9657d8c258
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773723"
---
# <a name="excel-worksheet-and-expression-evaluation"></a><span data-ttu-id="7d3df-104">Excel 工作表和表达式计算</span><span class="sxs-lookup"><span data-stu-id="7d3df-104">Excel Worksheet and Expression Evaluation</span></span>

 <span data-ttu-id="7d3df-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d3df-105">Applies to: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="7d3df-106">Microsoft Excel 工作表单元格内容计算为以下四种基本数据类型之一：</span><span class="sxs-lookup"><span data-stu-id="7d3df-106">Microsoft Excel worksheet cell contents are evaluated into one of four basic data types:</span></span>
  
- <span data-ttu-id="7d3df-107">**Numbers**</span><span class="sxs-lookup"><span data-stu-id="7d3df-107">**Numbers**</span></span>
    
- <span data-ttu-id="7d3df-108">**布尔值 TRUE** 或 **FALSE**</span><span class="sxs-lookup"><span data-stu-id="7d3df-108">**Boolean TRUE** or **FALSE**</span></span>
    
- <span data-ttu-id="7d3df-109">**Strings**</span><span class="sxs-lookup"><span data-stu-id="7d3df-109">**Strings**</span></span>
    
- <span data-ttu-id="7d3df-110">**Errors**</span><span class="sxs-lookup"><span data-stu-id="7d3df-110">**Errors**</span></span>
    
<span data-ttu-id="7d3df-111">包含这些类型的混合类型数组也可以作为函数的自变量输入到公式中，或者作为跨越多个单元格的值输入到数组公式中。</span><span class="sxs-lookup"><span data-stu-id="7d3df-111">Mixed-type arrays of these types can also be entered into formulas as arguments to functions or as values spanning more than one cell in an array formula.</span></span>
  
<span data-ttu-id="7d3df-112">当用户（或命令宏）在单元格中输入内容时，Excel 会尝试解释输入内容，在无法解释的情况下将显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="7d3df-112">When a user (or a command macro) enters something into a cell, Excel tries to interpret the input and displays an error message if it cannot.</span></span> <span data-ttu-id="7d3df-113">如果输入内容以字符串前缀（单引号）开头，Excel 会将所有输入字符按提供时的原样放入单元格中，不进行任何修改。</span><span class="sxs-lookup"><span data-stu-id="7d3df-113">If the input starts with a string prefix (a single quotation mark) Excel places all the input characters in the cell as provided, with no modification.</span></span> <span data-ttu-id="7d3df-114">（此字符串前缀不显示）。如果输入内容以 **=**、**+** 或 **-** 开头，Excel 会尝试将输入内容解释为公式。</span><span class="sxs-lookup"><span data-stu-id="7d3df-114">(The string prefix is not displayed.) If the input begins with **=**, **+**, or **-**, Excel tries to interpret the input as a formula.</span></span> <span data-ttu-id="7d3df-115">如果语法不正确或计算停止，则会显示错误，并将单元格置于编辑模式。</span><span class="sxs-lookup"><span data-stu-id="7d3df-115">If the syntax is incorrect or evaluation is stopped, an error is displayed, and the cell is put in edit mode.</span></span> <span data-ttu-id="7d3df-116">否则，Excel 会尝试识别、转换和计算运算符和函数名称及其自变量。</span><span class="sxs-lookup"><span data-stu-id="7d3df-116">Otherwise, Excel tries to identify, convert, and evaluate operators and function names and their arguments.</span></span> 
  
<span data-ttu-id="7d3df-p102">在应用运算符之前，先从左到右对操作数进行计算。从最高优先级运算符和最内层（嵌套最深处）开始计算函数。如果函数自变量或操作数无法转换为预期的类型，则计算将失败并导致 **#VALUE!** 错误。未将标记（不是文字值）识别为函数或已定义名称或标签时，计算将失败并导致 **#NAME?** 错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p102">Operands are evaluated from left to right before the operator is applied. Functions are evaluated starting with the highest-precedence operators and innermost (most nested). If function arguments or operands cannot be converted to the types expected, evaluation fails and results in a **#VALUE!** error. When a token (that is not a literal value) is not recognized as a function or defined name or label, evaluation fails and results in a **#NAME?** error.</span></span> 
  
<span data-ttu-id="7d3df-p103">如果输入内容不是以上述任何字符开头，Excel 会根据已知的输入模式（例如日期、时间、货币金额、百分比或数字）进行检查，并进行相应解释。此过程是根据具体区域设置完成的。如果这些解释均无意义，Excel 回归到将输入视为字符串并按原样将其放入单元格中。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p103">If the input does not start with any of these things, Excel checks against known patterns of input such as dates, times, currency amounts, percentages, or numbers, and interprets accordingly. This is done in a locale-specific way. If none of these interpretations makes sense, Excel reverts to considering the input as a string and places it in the cell unchanged.</span></span>
  
<span data-ttu-id="7d3df-p104">Excel 支持其他数据类型，其中最明显的是范围引用。在计算不接受引用自变量的运算符和函数的自变量时，或者当单元格公式中的表达式归类为引用时，Excel 会把引用转换为引用目标单元格的值。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p104">Excel supports other data types, the most visible of which is a range reference. Excel converts references to the values of the referred-to cells when evaluating arguments for operators and functions that do not take reference arguments, or when the expression in a cell formula reduces to a reference.</span></span>
  
<span data-ttu-id="7d3df-p105">Excel 公开了一项功能，即使用 XLM 函数 **EVALUATE** 及其 C API 等效函数 **xlfEvaluate** 将任何有效字符串归类为这四种基本工作表数据类型之一。除其他功能外，此函数提供了一种在 DLL 代码中计算指定范围的简单方法。此函数与先前所述的行为的不同之处仅在于，如果表达式求值失败，此返回返回 **#VALUE!** 错误，而不是显示错误消息或启用单元格编辑。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p105">Excel exposes the ability to reduce any valid character string to one of the basic four worksheet data types with the XLM function **EVALUATE** and its C API equivalent **xlfEvaluate**. This function provides, among other things, a simple way to evaluate named ranges in DLL code. This function differs from the behavior described earlier only in that instead of displaying error messages or enabling cell editing, it returns a **#VALUE!** error if the expression evaluation fails.</span></span> 
  
## <a name="numbers"></a><span data-ttu-id="7d3df-131">数字</span><span class="sxs-lookup"><span data-stu-id="7d3df-131">Numbers</span></span>

<span data-ttu-id="7d3df-p106">Excel 中的所有工作表数字在内部表示为 8 字节双精度浮点数，包括所有整数。但是，这些数字在 Excel 中的实现方式并不完全符合 IEEE 标准，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p106">All worksheet numbers in Excel are represented internally as 8-byte double-precision floating point, including all integers. However, the implementation of these numbers in Excel is not fully IEEE compliant, as shown in the following table.</span></span>
  
|<span data-ttu-id="7d3df-134">**类型**</span><span class="sxs-lookup"><span data-stu-id="7d3df-134">**Type**</span></span>|<span data-ttu-id="7d3df-135">**最大值**</span><span class="sxs-lookup"><span data-stu-id="7d3df-135">**Maximum**</span></span>|<span data-ttu-id="7d3df-136">**最小值**</span><span class="sxs-lookup"><span data-stu-id="7d3df-136">**Minimum**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7d3df-137">IEEE 8 字节双精度值</span><span class="sxs-lookup"><span data-stu-id="7d3df-137">IEEE 8-byte double</span></span>  <br/> |<span data-ttu-id="7d3df-138">1.7976931348623157E+308</span><span class="sxs-lookup"><span data-stu-id="7d3df-138">1.7976931348623157E+308</span></span>  <br/> |<span data-ttu-id="7d3df-139">2.2250738585072014E-308</span><span class="sxs-lookup"><span data-stu-id="7d3df-139">2.2250738585072014E-308</span></span>  <br/> |
|<span data-ttu-id="7d3df-140">工作表（由函数返回的值或粘贴值）</span><span class="sxs-lookup"><span data-stu-id="7d3df-140">Worksheet (returned by function or paste value)</span></span>  <br/> |<span data-ttu-id="7d3df-141">1.7976931348623157E+308</span><span class="sxs-lookup"><span data-stu-id="7d3df-141">1.7976931348623157E+308</span></span>  <br/> |<span data-ttu-id="7d3df-142">2.22507385850721E-308</span><span class="sxs-lookup"><span data-stu-id="7d3df-142">2.22507385850721E-308</span></span>  <br/> |
|<span data-ttu-id="7d3df-143">工作表（手动输入）</span><span class="sxs-lookup"><span data-stu-id="7d3df-143">Worksheet (manual input)</span></span>  <br/> |<span data-ttu-id="7d3df-144">9.99999999999999E+307</span><span class="sxs-lookup"><span data-stu-id="7d3df-144">9.99999999999999E+307</span></span>  <br/> |<span data-ttu-id="7d3df-145">2.22507385850721E-308</span><span class="sxs-lookup"><span data-stu-id="7d3df-145">2.22507385850721E-308</span></span>  <br/> |
   
<span data-ttu-id="7d3df-146">Excel 工作表不支持 IEEE 次正规数（即 2.2250738585072009E-308 到 4.9406564584124654E-324 范围内的数字），但 VBA 双精度类型则支持这类数字。</span><span class="sxs-lookup"><span data-stu-id="7d3df-146">IEEE subnormal numbers (that is, numbers in the range 2.2250738585072009E-308 to 4.9406564584124654E-324) are not supported in Excel worksheets but are supported by VBA Doubles.</span></span>
  
<span data-ttu-id="7d3df-147">如果 DLL 函数返回 IEEE +/- 无穷大值或无效双精度值，则 Excel 会将其转换为 **#NUM!**。</span><span class="sxs-lookup"><span data-stu-id="7d3df-147">If a DLL function returns IEEE +/- infinity or an invalid double, Excel converts it to **#NUM!**.</span></span> <span data-ttu-id="7d3df-148">所有次正规数和小于 Excel 最小正正规数的数字都将转换为正零。</span><span class="sxs-lookup"><span data-stu-id="7d3df-148">All subnormal numbers and numbers smaller than the minimum positive normal in Excel are converted to positive zero.</span></span> <span data-ttu-id="7d3df-149">IEEE 负零受支持，即可由 DLL 函数返回并显示为 **-0**。</span><span class="sxs-lookup"><span data-stu-id="7d3df-149">IEEE negative zero is supported, that is, it can be returned by a DLL function and is displayed as **-0**.</span></span> <span data-ttu-id="7d3df-150">（**\<** 运算符不会检查负零，因此，如果 A1 包含负零，**=A1\<0** 计算结果为 **TRUE**）。</span><span class="sxs-lookup"><span data-stu-id="7d3df-150">(The **\<** operator does not check for negative zero, and so **=A1\<0** evaluates to **TRUE** if A1 contains negative zero).</span></span> 
  
<span data-ttu-id="7d3df-p108">请注意，某些数字格式的限制比上述情况更严格，例如日期和时间。实际上，整数除法为浮点除法，在极端情况下可能产生非整数结果，此时的精确结果应为整数。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p108">Note that certain number formats have narrower limits than these, for example, dates and times. Integer division is, in fact, floating point division and might, in extreme cases, yield a non-integer result where the precise result should be an integer.</span></span>
  
## <a name="long-unicode-strings"></a><span data-ttu-id="7d3df-153">长型 Unicode 字符串</span><span class="sxs-lookup"><span data-stu-id="7d3df-153">Long Unicode Strings</span></span>

<span data-ttu-id="7d3df-p109">对于许多 Excel 版本而言，用户在 Excel 中看到的所有字符串现在都在内部存储为 Unicode 字符串。Unicode 工作表字符串的长度最多为 32,767 (2<sup>15</sup> - 1) 个字符，并可包含任何有效的 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p109">All strings the user sees in Excel have for many versions now been stored internally as Unicode strings. Unicode worksheet strings can be up to 32,767 (2<sup>15</sup> - 1) characters in length and can contain any valid Unicode character.</span></span> 
  
<span data-ttu-id="7d3df-p110">首次引入 C API 时，工作表字符串为长度限制为 255 个字符的字节字符串，而 C API 反映了这些限制。从 Excel 2007 开始，C API 进行了更新，可以处理 Excel 长型 Unicode 字符串。这意味着，以正确方式注册的 DLL 函数可以接受 Unicode 自变量并返回 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p110">When the C API was first introduced, worksheet strings were byte strings limited in length to 255 characters, and the C API reflected these limitations. With Excel 2007, the C API is updated to handle Excel long Unicode strings. This means that DLL functions registered in the right way can accept Unicode arguments and return Unicode strings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7d3df-159">为了实现向后兼容，C API 现在仍然完全支持字节字符串，但是这些字符串仍然具有同样的 255 字符限制。</span><span class="sxs-lookup"><span data-stu-id="7d3df-159">Byte strings are still fully supported in the C API for backward compatibility; however they still have the same 255-character limit.</span></span> 
  
## <a name="returning-errors"></a><span data-ttu-id="7d3df-160">返回错误</span><span class="sxs-lookup"><span data-stu-id="7d3df-160">Returning Errors</span></span>

<span data-ttu-id="7d3df-p111">Excel 无法将函数或运算符自变量转换为正确的类型时，或无法识别函数或已定义名称时，会将单元格算为错误。前文已介绍了这两种情况。内置的工作表函数和运算符失败时，也会导致错误，同时会告知用户失败类型。你应该让自己的加载项函数返回的错误与 Excel 中的行为一致。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p111">Excel evaluates cells to errors where it cannot convert function or operator arguments to the correct type, or if it does not recognize a function or defined name. Both of these scenarios were described earlier. When the built-in worksheet functions and operators fail, they also result in errors that inform the user of the type of failure. You should have your own add-in functions return errors that are consistent with the behavior in Excel.</span></span>
  
### <a name="null"></a><span data-ttu-id="7d3df-165">#NULL!</span><span class="sxs-lookup"><span data-stu-id="7d3df-165">#NULL!</span></span>

<span data-ttu-id="7d3df-p112">有些 XLM 信息函数返回 **#NULL!** 错误。例如，在未安装打印机的情况下，调用函数 **GET.DOCUMENT(78)** 或带自变量 78 的等效 C API 函数 **xlfGetDocument**，便会导致返回此错误。在其他一些情况下，有些函数也会返回此错误（例如这些函数计算出空字符串时）。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p112">The **#NULL!** error is returned by some XLM information functions. For example, calling **GET.DOCUMENT(78)**, or the equivalent C API function **xlfGetDocument** with argument 78, when there are no printers installed results in this error being returned. It can also be returned by some functions when, for example, they evaluate an empty string.</span></span> 
  
<span data-ttu-id="7d3df-170">当其他任何错误看起来都不合适时，你可能希望从自己的加载项函数返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-170">You might want to return this error from your add-in function when none of the other errors seems appropriate.</span></span>
  
### <a name="div0"></a><span data-ttu-id="7d3df-171">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="7d3df-171">#DIV/0!</span></span>

<span data-ttu-id="7d3df-p113">当分母计算结果为零或数字太小而无法由 Excel 表示为非零时，Excel 除法运算符返回 **#DIV/0!** 错误。根据定义涉及除法的某些函数也可能返回此错误。例如，如果没有任何输入可以转换为数字，则 **AVERAGE** 将返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p113">The Excel division operator returns the **#DIV/0!** error when the denominator evaluates to zero or a number is too small to be represented as non-zero by Excel. Some functions that by definition involve a division can also return this error. For example, **AVERAGE** returns this error if none of the inputs can be converted to numbers.</span></span> 
  
<span data-ttu-id="7d3df-176">仅当需要指示检测到除零情况时，才应考虑从加载项函数返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-176">You should only consider returning this error from your add-in function to indicate that a division by zero was detected.</span></span>
  
### <a name="value"></a><span data-ttu-id="7d3df-177">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="7d3df-177">#VALUE!</span></span>

<span data-ttu-id="7d3df-p114">如果无法将函数或运算符自变量转换为所需类型，Excel 将返回 **#VALUE!** 错误。对于无法转换的函数自变量，例如 `=LN("X")`，Excel 不会调用函数代码。在编写和调试自己的加载项函数时，这一点非常重要，务必注意。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p114">Excel returns the **#VALUE!** error if a function or operator argument cannot be converted to the required type. In the case of function arguments that cannot be converted, for example  `=LN("X")`, Excel does not call the function code. This is an important point to remember when writing and debugging your own add-in functions.</span></span> 
  
<span data-ttu-id="7d3df-p115">有些函数无法在函数代码中转换自变量的情况下会返回此错误。例如，尽管自变量类型正确，但 `DATEVALUE("30-Feb-2007")` 仍然会失败并显示此错误。在这种情况下，该函数便会从其代码中返回此错误。即使值类型和范围都是允许的，有些函数也会返回此错误，例如 `FIND("a","xyz")` 就会返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p115">Some functions return this error if an argument cannot be converted within the function code. For example,  `DATEVALUE("30-Feb-2007")` fails with this error despite the argument being of the right type. In this case, it is the function that is returning the error from within its code. Some functions return this error even though the value types and ranges are allowable, for example  `FIND("a","xyz")` returns this error.</span></span> 
  
<span data-ttu-id="7d3df-p116">如果需要指示自变量的类型出错、无法转换为正确类型或超出范围，应考虑从加载项函数返回此错误，但对于数字自变量超出范围的情况，应考虑返回 **#NUM!**。当范围或数组自变量的形状或大小出错时，也应考虑返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p116">You should consider returning this error from your add-in function to indicate that the arguments are of the wrong type, could not be converted to the right type, or are out of range, although you should consider returning **#NUM!** for numerical arguments out of range. You should also consider returning this error when range or array arguments are the wrong shape or size.</span></span> 
  
### <a name="ref"></a><span data-ttu-id="7d3df-189">#REF!</span><span class="sxs-lookup"><span data-stu-id="7d3df-189">#REF!</span></span>

<span data-ttu-id="7d3df-p117">将表达式复制到某个位置时，如果产生的相对引用超出范围，Excel 会在该表达式中生成 **#REF!** 错误。例如，如果单元格 B2 包含公式 `=A1`，则将其复制到单元格 B1 会生成公式 **=#REF!**。如果公式包含的引用在剪切和粘贴操作中遭到覆盖或者在行、列或工作表删除操作中遭到删除，这些公式中也会生成此错误。有些可以返回引用的函数可能会返回此错误，例如 `OFFSET(A1,-1,-1)`。如果工作表名称在定义中包含的引用变为无效状态，这些工作表名称将计算出此错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p117">Excel generates the **#REF!** error within an expression when it is copied to a location where the resulting relative reference goes out of bounds. For example, if the cell B2 contains the formula  `=A1`, copying this to cell B1 results in a formula **=#REF!**. This error is also generated in formulas that contain a reference that is overwritten in a cut-and-paste operation or is deleted in a row, column, or worksheet deletion. Some functions that can return references can return this error, for example,  `OFFSET(A1,-1,-1)`. Worksheet names whose definitions contain references that become invalid are evaluated to this error.</span></span>
  
<span data-ttu-id="7d3df-p118">如果加载项函数接受引用自变量，应考虑在引用无效时或收到引用错误时返回此错误。[Excel 中的内存管理](memory-management-in-excel.md)中有关 XLOPER/XLOPER12 的部分介绍了如何创建可接受和返回引用自变量的函数。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p118">If your add-in function takes reference arguments, you should consider returning this error if the references are invalid, or if you are passed a reference error. The section on XLOPER/XLOPER12s in [Memory Management in Excel](memory-management-in-excel.md) describes how to create functions that can accept and return reference arguments.</span></span> 
  
### <a name="name"></a><span data-ttu-id="7d3df-198">#NAME?</span><span class="sxs-lookup"><span data-stu-id="7d3df-198">#NAME?</span></span>

<span data-ttu-id="7d3df-p119">当表达式包含的标记未被识别为函数或已定义名称时，Excel 会生成 **#NAME?** 错误。如果加载项函数尝试访问已定义名称但该名称未定义，则应考虑返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p119">Excel generates the **#NAME?** error when an expression contains a token that is not recognized as a function or defined name. If your add-in function tries to access a defined name and it is not defined, you should consider returning this error.</span></span> 
  
### <a name="num"></a><span data-ttu-id="7d3df-201">#NUM!</span><span class="sxs-lookup"><span data-stu-id="7d3df-201">#NUM!</span></span>

<span data-ttu-id="7d3df-p120">当数字输入超出允许范围时，Excel 中的许多内置数字函数和数学函数都会返回 **#NUM!** 错误，例如 `LN(0)`。如果需要指示数字输入无效或超出范围，应考虑从加载项函数返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p120">Many of the built-in numerical and mathematical functions in Excel return the **#NUM!** error when a numerical input is out of the permitted range, for example,  `LN(0)`. You should consider returning this error from your add-in function to indicate that a numerical input was invalid or out of range.</span></span>
  
### <a name="na"></a><span data-ttu-id="7d3df-205">#N/A</span><span class="sxs-lookup"><span data-stu-id="7d3df-205">#N/A</span></span>

<span data-ttu-id="7d3df-p121">通常会返回 **#N/A** 错误来表示无法获得成功或有意义的结果。例如，带有第三个参数零的 MATCH 函数在无法找到完全匹配项时，便会返回此错误。此外，也可以使用函数 **NA** 生成此错误，并可使用函数 **ISNA** 专门检测此错误。因此，这是工作表中常用于指示一系列应用程序特定情况的错误。</span><span class="sxs-lookup"><span data-stu-id="7d3df-p121">The **#N/A** error is often returned to signify a successful or meaningful result is not available. For example, MATCH with the third argument zero returns this error if an exact match cannot be found. This error can also be generated using the function **NA** and specifically detected with the function **ISNA**. It is therefore a commonly used error in worksheets to indicate a range of application-specific conditions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d3df-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d3df-210">See also</span></span>



[<span data-ttu-id="7d3df-211">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="7d3df-211">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
[<span data-ttu-id="7d3df-212">在 Excel 中使用 C API 进行编程</span><span class="sxs-lookup"><span data-stu-id="7d3df-212">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
  
[<span data-ttu-id="7d3df-213">评估名称和其他工作表公式表达式</span><span class="sxs-lookup"><span data-stu-id="7d3df-213">Evaluating Names and Other Worksheet Formula Expressions</span></span>](evaluating-names-and-other-worksheet-formula-expressions.md)
  
[<span data-ttu-id="7d3df-214">Excel XLL SDK API 函数引用</span><span class="sxs-lookup"><span data-stu-id="7d3df-214">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)

