---
title: Excel ������ͱ��ʽ��ֵ
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- expression evaluation [excel 2007],errors in worksheets [Excel 2007],long Unicode strings [Excel 2007],evaluating expressions [Excel 2007],evaluating worksheets [Excel 2007],worksheet evaluation [Excel 2007],worksheet errors [Excel 2007]
localization_priority: Normal
ms.assetid: 47b46a7d-6cfb-4f5b-946d-e0164d18512a
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 543ff7fcbc88253dafd7fc6e7000bf9657d8c258
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773723"
---
# <a name="excel-worksheet-and-expression-evaluation"></a><span data-ttu-id="51cd5-104">Excel ������ͱ��ʽ��ֵ</span><span class="sxs-lookup"><span data-stu-id="51cd5-104">Excel Worksheet and Expression Evaluation</span></span>

 <span data-ttu-id="51cd5-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51cd5-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="51cd5-106">Microsoft Excel ������ĵ�Ԫ�����ݽ���������ĸ���������������֮һ��</span><span class="sxs-lookup"><span data-stu-id="51cd5-106">Microsoft Excel worksheet cell contents are evaluated into one of four basic data types:</span></span>
  
- <span data-ttu-id="51cd5-107">**Numbers**</span><span class="sxs-lookup"><span data-stu-id="51cd5-107">**Numbers**</span></span>
    
- <span data-ttu-id="51cd5-108">**Boolean TRUE** �� **FALSE**</span><span class="sxs-lookup"><span data-stu-id="51cd5-108">**Boolean TRUE** or **FALSE**</span></span>
    
- <span data-ttu-id="51cd5-109">**Strings**</span><span class="sxs-lookup"><span data-stu-id="51cd5-109">**Strings**</span></span>
    
- <span data-ttu-id="51cd5-110">**Errors**</span><span class="sxs-lookup"><span data-stu-id="51cd5-110">**Errors**</span></span>
    
<span data-ttu-id="51cd5-111">��Щ���͵Ļ����������Ҳ������Ϊ�������뵽��ʽ�У�����Ϊ���鹫ʽ�п�Խ�����Ԫ���ֵ��</span><span class="sxs-lookup"><span data-stu-id="51cd5-111">Mixed-type arrays of these types can also be entered into formulas as arguments to functions or as values spanning more than one cell in an array formula.</span></span>
  
<span data-ttu-id="51cd5-112">当内容在单元格中输入用户 （或命令宏） 时，Excel 将尝试解释输入，并显示一条错误消息，如果它不能。</span><span class="sxs-lookup"><span data-stu-id="51cd5-112">When a user (or a command macro) enters something into a cell, Excel tries to interpret the input and displays an error message if it cannot.</span></span> <span data-ttu-id="51cd5-113">如果输入开头的字符串前缀 （单引号） Excel 将输入的所有字符都放在单元格，如附带没有任何修改。</span><span class="sxs-lookup"><span data-stu-id="51cd5-113">If the input starts with a string prefix (a single quotation mark) Excel places all the input characters in the cell as provided, with no modification.</span></span> <span data-ttu-id="51cd5-114">（不显示的字符串的前缀。）如果输入开头**=**， **+**，或**-**，Excel 尝试将公式作为输入解释。</span><span class="sxs-lookup"><span data-stu-id="51cd5-114">(The string prefix is not displayed.) If the input begins with **=**, **+**, or **-**, Excel tries to interpret the input as a formula.</span></span> <span data-ttu-id="51cd5-115">如果语法不正确或评估已停止，则显示错误，并且单元格置于编辑模式。</span><span class="sxs-lookup"><span data-stu-id="51cd5-115">If the syntax is incorrect or evaluation is stopped, an error is displayed, and the cell is put in edit mode.</span></span> <span data-ttu-id="51cd5-116">否则，Excel 尝试标识、 转换和评估运算符、 函数名称和它们的参数。</span><span class="sxs-lookup"><span data-stu-id="51cd5-116">Otherwise, Excel tries to identify, convert, and evaluate operators and function names and their arguments.</span></span> 
  
<span data-ttu-id="51cd5-p102">��Ӧ�������֮ǰ���Բ����������ҽ��м��㡣��������ȼ�������������ڲ㣨Ƕ����ࣩ��ʼ�Ժ������м��㡣������ܽ�������������������ת��ΪԤ�ڵ����ͣ������ʧ�ܣ������� **#VALUE!** ���󡣵�ϵͳ�������ƣ�������һ������ֵ��ʶ��Ϊ������������ƻ��ǩʱ�����㽫ʧ�ܣ����ᵼ�� **#NAME?** ����</span><span class="sxs-lookup"><span data-stu-id="51cd5-p102">Operands are evaluated from left to right before the operator is applied. Functions are evaluated starting with the highest-precedence operators and innermost (most nested). If function arguments or operands cannot be converted to the types expected, evaluation fails and results in a **#VALUE!** error. When a token (that is not a literal value) is not recognized as a function or defined name or label, evaluation fails and results in a **#NAME?** error.</span></span> 
  
<span data-ttu-id="51cd5-p103">������벻���κ���Щ���ݿ�ͷ��Excel �������������֪ģʽ�������ڡ�ʱ�䡢���ҽ��ٷֱȻ����֣����м�飬����Ӧ�ؽ��н��͡������ض����������ò�ȡ�Ĵ����ʽ�������Щ����û���κ����壬Excel ����ͷ���ǽ�������Ϊ�ַ��������������ڵ�Ԫ���б��ֲ��䡣</span><span class="sxs-lookup"><span data-stu-id="51cd5-p103">If the input does not start with any of these things, Excel checks against known patterns of input such as dates, times, currency amounts, percentages, or numbers, and interprets accordingly. This is done in a locale-specific way. If none of these interpretations makes sense, Excel reverts to considering the input as a string and places it in the cell unchanged.</span></span>
  
<span data-ttu-id="51cd5-p104">Excel ֧�������������ͣ������Ե��Ƿ�Χ���á������㲻ʹ�����ò�����������ͺ����Ĳ���ʱ���򵱵�Ԫ��ʽ�еı��ʽ����Ϊһ������ʱ��Excel ��������ת��Ϊ���õ���Ԫ���ֵ��</span><span class="sxs-lookup"><span data-stu-id="51cd5-p104">Excel supports other data types, the most visible of which is a range reference. Excel converts references to the values of the referred-to cells when evaluating arguments for operators and functions that do not take reference arguments, or when the expression in a cell formula reduces to a reference.</span></span>
  
<span data-ttu-id="51cd5-p105">Excel ͨ�� XLM ���� **EVALUATE** ���� C API ��Ч�� **xlfEvaluate**���ܹ����κ���Ч���ַ����ַ������ٵ��ĸ������Ĺ�������������֮һ������֮�⣬�˺����ṩ���� DLL �����е���������ļ򵥷������˺�����ǰ����ʾ������Ϣ�����õ�Ԫ��༭����Ϊ��ͬ��������ʽ����ʧ�ܣ��ú����� **#VALUE!** ����</span><span class="sxs-lookup"><span data-stu-id="51cd5-p105">Excel exposes the ability to reduce any valid character string to one of the basic four worksheet data types with the XLM function **EVALUATE** and its C API equivalent **xlfEvaluate**. This function provides, among other things, a simple way to evaluate named ranges in DLL code. This function differs from the behavior described earlier only in that instead of displaying error messages or enabling cell editing, it returns a **#VALUE!** error if the expression evaluation fails.</span></span> 
  
## <a name="numbers"></a><span data-ttu-id="51cd5-131">����</span><span class="sxs-lookup"><span data-stu-id="51cd5-131">Numbers</span></span>

<span data-ttu-id="51cd5-p106">Excel �е����й��������ڲ���ʾΪ 8 �ֽ�˫���ȸ��������������е����������ǣ��� Excel �е���Щ���ֵ�ʵ�ֲ�����ȫ��� IEEE�����±���ʾ��</span><span class="sxs-lookup"><span data-stu-id="51cd5-p106">All worksheet numbers in Excel are represented internally as 8-byte double-precision floating point, including all integers. However, the implementation of these numbers in Excel is not fully IEEE compliant, as shown in the following table.</span></span>
  
|<span data-ttu-id="51cd5-134">**����**</span><span class="sxs-lookup"><span data-stu-id="51cd5-134">**Type**</span></span>|<span data-ttu-id="51cd5-135">**���ֵ**</span><span class="sxs-lookup"><span data-stu-id="51cd5-135">**Maximum**</span></span>|<span data-ttu-id="51cd5-136">**��Сֵ**</span><span class="sxs-lookup"><span data-stu-id="51cd5-136">**Minimum**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="51cd5-137">IEEE 8 �ֽ�˫����ֵ</span><span class="sxs-lookup"><span data-stu-id="51cd5-137">IEEE 8-byte double</span></span>  <br/> |<span data-ttu-id="51cd5-138">1.7976931348623157 E + 308</span><span class="sxs-lookup"><span data-stu-id="51cd5-138">1.7976931348623157E+308</span></span>  <br/> |<span data-ttu-id="51cd5-139">2.2250738585072014 E-308</span><span class="sxs-lookup"><span data-stu-id="51cd5-139">2.2250738585072014E-308</span></span>  <br/> |
|<span data-ttu-id="51cd5-140">���������������ճ��ֵ���أ�</span><span class="sxs-lookup"><span data-stu-id="51cd5-140">Worksheet (returned by function or paste value)</span></span>  <br/> |<span data-ttu-id="51cd5-141">1.7976931348623157 E + 308</span><span class="sxs-lookup"><span data-stu-id="51cd5-141">1.7976931348623157E+308</span></span>  <br/> |<span data-ttu-id="51cd5-142">2.22507385850721 E-308</span><span class="sxs-lookup"><span data-stu-id="51cd5-142">2.22507385850721E-308</span></span>  <br/> |
|<span data-ttu-id="51cd5-143">��������ֶ����룩</span><span class="sxs-lookup"><span data-stu-id="51cd5-143">Worksheet (manual input)</span></span>  <br/> |<span data-ttu-id="51cd5-144">9.99999999999999 E + 307</span><span class="sxs-lookup"><span data-stu-id="51cd5-144">9.99999999999999E+307</span></span>  <br/> |<span data-ttu-id="51cd5-145">2.22507385850721 E-308</span><span class="sxs-lookup"><span data-stu-id="51cd5-145">2.22507385850721E-308</span></span>  <br/> |
   
<span data-ttu-id="51cd5-146">IEEE С������ֵ��Χ����ֵ������ 2.2250738585072009E�C308 �� 4.9406564584124654E�C324 ��Χ�ڵ���ֵ���� Excel �������ڲ���֧�֣����� VBA ˫����ֵ��֧�֡�</span><span class="sxs-lookup"><span data-stu-id="51cd5-146">IEEE subnormal numbers (that is, numbers in the range 2.2250738585072009E-308 to 4.9406564584124654E-324) are not supported in Excel worksheets but are supported by VBA Doubles.</span></span>
  
<span data-ttu-id="51cd5-147">如果 DLL 函数返回 + /-无穷大或无效的双 IEEE，Excel 将其转换为 **#NUM ！**。</span><span class="sxs-lookup"><span data-stu-id="51cd5-147">If a DLL function returns IEEE +/- infinity or an invalid double, Excel converts it to **#NUM!**.</span></span> <span data-ttu-id="51cd5-148">所有 subnormal 号码以及小于最小正普通在 Excel 中的号码转换为正零。</span><span class="sxs-lookup"><span data-stu-id="51cd5-148">All subnormal numbers and numbers smaller than the minimum positive normal in Excel are converted to positive zero.</span></span> <span data-ttu-id="51cd5-149">IEEE 负零都支持，即，它可以由 DLL 函数返回并显示为 **-0**。</span><span class="sxs-lookup"><span data-stu-id="51cd5-149">IEEE negative zero is supported, that is, it can be returned by a DLL function and is displayed as **-0**.</span></span> <span data-ttu-id="51cd5-150">(**\<** 运算符不会检查负零，因此 **= A1\<0**计算结果为**TRUE** ，如果 A1 包含负零)。</span><span class="sxs-lookup"><span data-stu-id="51cd5-150">(The **\<** operator does not check for negative zero, and so **=A1\<0** evaluates to **TRUE** if A1 contains negative zero).</span></span> 
  
<span data-ttu-id="51cd5-p108">��ע�⣬ĳЩ���ָ�ʽ����Щ�涨��ȣ����Ƹ�Ϊ�ϸ����磬���ں�ʱ�䡣��ʵ�ϣ������������Ǹ����������������ڼ�������¿��ܻ�������������������ȷ���ӦΪ������</span><span class="sxs-lookup"><span data-stu-id="51cd5-p108">Note that certain number formats have narrower limits than these, for example, dates and times. Integer division is, in fact, floating point division and might, in extreme cases, yield a non-integer result where the precise result should be an integer.</span></span>
  
## <a name="long-unicode-strings"></a><span data-ttu-id="51cd5-153">������ Unicode �ַ���</span><span class="sxs-lookup"><span data-stu-id="51cd5-153">Long Unicode Strings</span></span>

<span data-ttu-id="51cd5-p109">�û��� Excel �п��Կ����������ַ���Ŀǰ���ж���汾���ڲ��洢Ϊ Unicode �ַ�����Unicode �������ַ�������Ϊ 32767 (2<sup>15</sup>-1) ���ַ����ȣ����ҿ��԰����κ���Ч�� Unicode �ַ���</span><span class="sxs-lookup"><span data-stu-id="51cd5-p109">All strings the user sees in Excel have for many versions now been stored internally as Unicode strings. Unicode worksheet strings can be up to 32,767 (2<sup>15</sup> - 1) characters in length and can contain any valid Unicode character.</span></span> 
  
<span data-ttu-id="51cd5-p110">���״����� C API ʱ���������ַ������ֽ��ַ�������������Ϊ 255 ���ַ����ڣ����� C API �ɷ�ӳ��Щ���ơ�ͨ��ʹ�� Excel 2007��C API ���º󣬿ɴ��� Excel ������ Unicode �ַ���������ζ�Ų�����ȷ��ʽע��� DLL �������Խ��� Unicode ���������� Unicode �ַ�����</span><span class="sxs-lookup"><span data-stu-id="51cd5-p110">When the C API was first introduced, worksheet strings were byte strings limited in length to 255 characters, and the C API reflected these limitations. With Excel 2007, the C API is updated to handle Excel long Unicode strings. This means that DLL functions registered in the right way can accept Unicode arguments and return Unicode strings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="51cd5-159">Ϊ�������ݣ�C API ����Ȼ��ȫ֧���ֽ��ַ��������������Ծ���ͬ���� 255 ���ַ����ơ�</span><span class="sxs-lookup"><span data-stu-id="51cd5-159">Byte strings are still fully supported in the C API for backward compatibility; however they still have the same 255-character limit.</span></span> 
  
## <a name="returning-errors"></a><span data-ttu-id="51cd5-160">���ش���</span><span class="sxs-lookup"><span data-stu-id="51cd5-160">Returning Errors</span></span>

<span data-ttu-id="51cd5-p111">����޷������������������ת��Ϊ��ȷ�����ͣ���������޷�ʶ�������Ѷ�������ƣ�Excel �Ե�Ԫ��ļ�������������ַ���ǰ�涼�ѽ��ܹ���������ù����������������������ϣ�����Ҳ�ᵼ�³��������֪�û����ϵ����͡���Ӧ����������ӳ������������� Excel �е���Ϊһ�µĴ���</span><span class="sxs-lookup"><span data-stu-id="51cd5-p111">Excel evaluates cells to errors where it cannot convert function or operator arguments to the correct type, or if it does not recognize a function or defined name. Both of these scenarios were described earlier. When the built-in worksheet functions and operators fail, they also result in errors that inform the user of the type of failure. You should have your own add-in functions return errors that are consistent with the behavior in Excel.</span></span>
  
### <a name="null"></a><span data-ttu-id="51cd5-165">#NULL!</span><span class="sxs-lookup"><span data-stu-id="51cd5-165">#NULL!</span></span>

<span data-ttu-id="51cd5-p112">**#NULL!** ������һЩ XLM ��Ϣ�������ء����磬�����صĴ�����û�д�ӡ����װ���ʱ�����ô��в��� 78 �� **GET.DOCUMENT(78)** ���Ч�� C API ���� **xlfGetDocument**���ô��󻹿���ĳЩ�������أ����磬�ڼ�����ַ���ʱ����</span><span class="sxs-lookup"><span data-stu-id="51cd5-p112">The **#NULL!** error is returned by some XLM information functions. For example, calling **GET.DOCUMENT(78)**, or the equivalent C API function **xlfGetDocument** with argument 78, when there are no printers installed results in this error being returned. It can also be returned by some functions when, for example, they evaluate an empty string.</span></span> 
  
<span data-ttu-id="51cd5-170">��û���κ����������ƺ���ʱ����������Ҫ��������ӳ��������ش˴���</span><span class="sxs-lookup"><span data-stu-id="51cd5-170">You might want to return this error from your add-in function when none of the other errors seems appropriate.</span></span>
  
### <a name="div0"></a><span data-ttu-id="51cd5-171">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="51cd5-171">#DIV/0!</span></span>

<span data-ttu-id="51cd5-p113">�����ĸ�ļ�����Ϊ�����һ��С���޷��� Excel �б�ʾΪ�������ֵʱ��Excel ��������������� **#DIV/0!** ����ĳЩ���ݶ����漰�������ĺ��������ܷ��ش˴������磬��û���κ��������ת��Ϊ����ʱ�� **AVERAGE** �����ش˴���</span><span class="sxs-lookup"><span data-stu-id="51cd5-p113">The Excel division operator returns the **#DIV/0!** error when the denominator evaluates to zero or a number is too small to be represented as non-zero by Excel. Some functions that by definition involve a division can also return this error. For example, **AVERAGE** returns this error if none of the inputs can be converted to numbers.</span></span> 
  
<span data-ttu-id="51cd5-176">��ֻ�迼�Ǵ�������ӳ��������ص����ִ�����ָʾ��⵽���������ĳ�����</span><span class="sxs-lookup"><span data-stu-id="51cd5-176">You should only consider returning this error from your add-in function to indicate that a division by zero was detected.</span></span>
  
### <a name="value"></a><span data-ttu-id="51cd5-177">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="51cd5-177">#VALUE!</span></span>

<span data-ttu-id="51cd5-p114">����������������������ת��Ϊ��������ͣ�Excel ������ **#VALUE!** �������������������ת��������  `=LN("X")`����Excel �Ͳ�����ú������롣�ڱ�д�͵����Լ�����ӳ�����ʱ������μ���һ�㡣</span><span class="sxs-lookup"><span data-stu-id="51cd5-p114">Excel returns the **#VALUE!** error if a function or operator argument cannot be converted to the required type. In the case of function arguments that cannot be converted, for example  `=LN("X")`, Excel does not call the function code. This is an important point to remember when writing and debugging your own add-in functions.</span></span> 
  
<span data-ttu-id="51cd5-p115">������������ں���������ת����ĳЩ�����᷵�ش˴������磬���ܲ�����������ȷ�ģ� `DATEVALUE("30-Feb-2007")` Ҳ����˴��������ʧ�ܡ�����������£��ú���������������еĴ��󡣼�ʹֵ���ͺͷ�Χ��������ģ�ĳЩ�����Ի᷵�ش˴�������  `FIND("a","xyz")` �᷵�ش˴���</span><span class="sxs-lookup"><span data-stu-id="51cd5-p115">Some functions return this error if an argument cannot be converted within the function code. For example,  `DATEVALUE("30-Feb-2007")` fails with this error despite the argument being of the right type. In this case, it is the function that is returning the error from within its code. Some functions return this error even though the value types and ranges are allowable, for example  `FIND("a","xyz")` returns this error.</span></span> 
  
<span data-ttu-id="51cd5-p116">��Ӧ���Ǵ�������ӳ��������ش˴�����ָʾ�������������޷�������ת��Ϊ��ȷ�����ͻ򳬳��˷�Χ�Ĵ�����Ȼ��ҲӦ�ÿ��Ƿ�����ֵ����������Χ�� **#NUM!** ������Ӧ����������������������״���С����ʱ���ش˴���</span><span class="sxs-lookup"><span data-stu-id="51cd5-p116">You should consider returning this error from your add-in function to indicate that the arguments are of the wrong type, could not be converted to the right type, or are out of range, although you should consider returning **#NUM!** for numerical arguments out of range. You should also consider returning this error when range or array arguments are the wrong shape or size.</span></span> 
  
### <a name="ref"></a><span data-ttu-id="51cd5-189">#REF!</span><span class="sxs-lookup"><span data-stu-id="51cd5-189">#REF!</span></span>

<span data-ttu-id="51cd5-p117">�������ʽ���Ƶ����ɵ�������ó������Ƶ�λ��ʱ��Excel �ڸñ��ʽ������ **#REF!** �������磬�����Ԫ�� B2 �а�����ʽ  `=A1`�����˹�ʽ���Ƶ���Ԫ�� B1 �ᵼ�����ɹ�ʽ **=#REF!** ���˴���Ҳ������һЩ��ʽ�����а���ͨ��ʹ�ü��к�ճ���������ǵ����ã��������С��л�����ɾ����ɾ�������á���Щ�ܷ�����Щ���õĺ������Է��ش˴������磬 `OFFSET(A1,-1,-1)`�������а��������Ч���õĹ���������Ҳ����Դ˴����������</span><span class="sxs-lookup"><span data-stu-id="51cd5-p117">Excel generates the **#REF!** error within an expression when it is copied to a location where the resulting relative reference goes out of bounds. For example, if the cell B2 contains the formula  `=A1`, copying this to cell B1 results in a formula **=#REF!**. This error is also generated in formulas that contain a reference that is overwritten in a cut-and-paste operation or is deleted in a row, column, or worksheet deletion. Some functions that can return references can return this error, for example,  `OFFSET(A1,-1,-1)`. Worksheet names whose definitions contain references that become invalid are evaluated to this error.</span></span>
  
<span data-ttu-id="51cd5-p118">���������ӳ������������ò�������Ӧ�������������Ч����������յ������ô����践�ش˴���[Memory Management in Excel](memory-management-in-excel.md)���й� XLOPER/XLOPER12s �Ĳ��ֽ�������δ����ɽ��ܲ��������ò����ĺ�����</span><span class="sxs-lookup"><span data-stu-id="51cd5-p118">If your add-in function takes reference arguments, you should consider returning this error if the references are invalid, or if you are passed a reference error. The section on XLOPER/XLOPER12s in [Memory Management in Excel](memory-management-in-excel.md) describes how to create functions that can accept and return reference arguments.</span></span> 
  
### <a name="name"></a><span data-ttu-id="51cd5-198">#NAME?</span><span class="sxs-lookup"><span data-stu-id="51cd5-198">#NAME?</span></span>

<span data-ttu-id="51cd5-p119">�����ʽ�а���δ��ʶ��Ϊ������������Ƶ�����ʱ��Excel ���� **#NAME?** �������������ӳ��������Է����Ѷ�������ƣ�����ʵ��ȴ��δ���壬��Ӧ���Ƿ��ش˴���</span><span class="sxs-lookup"><span data-stu-id="51cd5-p119">Excel generates the **#NAME?** error when an expression contains a token that is not recognized as a function or defined name. If your add-in function tries to access a defined name and it is not defined, you should consider returning this error.</span></span> 
  
### <a name="num"></a><span data-ttu-id="51cd5-201">#NUM!</span><span class="sxs-lookup"><span data-stu-id="51cd5-201">#NUM!</span></span>

<span data-ttu-id="51cd5-p120">����ֵ���벻������ķ�Χ�����磬 **** ����Excel ��������������ֺ���ѧ�������᷵�� `LN(0)`����Ӧ�ÿ��Ǵ�������ӳ������з��ش˴�����ָʾ����������Ч�򳬳���Χ��</span><span class="sxs-lookup"><span data-stu-id="51cd5-p120">Many of the built-in numerical and mathematical functions in Excel return the **#NUM!** error when a numerical input is out of the permitted range, for example,  `LN(0)`. You should consider returning this error from your add-in function to indicate that a numerical input was invalid or out of range.</span></span>
  
### <a name="na"></a><span data-ttu-id="51cd5-205">#N/A</span><span class="sxs-lookup"><span data-stu-id="51cd5-205">#N/A</span></span>

<span data-ttu-id="51cd5-p121">ͨ������ **#N/A** ��������ָʾ�ɹ���������Ľ���ǲ����õġ����磬����Ҳ�����ȷƥ�������������������� MATCH �����ش˴��󡣴��⣬������ʹ�ú��� **NA** ���ɴ˴��󣬲�ʹ�ú��� **ISNA** ר�Ŷ�����м�⡣��ˣ��������г������ִ�����ָʾ�ض���Ӧ�ó����������Χ��</span><span class="sxs-lookup"><span data-stu-id="51cd5-p121">The **#N/A** error is often returned to signify a successful or meaningful result is not available. For example, MATCH with the third argument zero returns this error if an exact match cannot be found. This error can also be generated using the function **NA** and specifically detected with the function **ISNA**. It is therefore a commonly used error in worksheets to indicate a range of application-specific conditions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="51cd5-210">�������</span><span class="sxs-lookup"><span data-stu-id="51cd5-210">See also</span></span>



[<span data-ttu-id="51cd5-211">Excel Programming Concepts</span><span class="sxs-lookup"><span data-stu-id="51cd5-211">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
[<span data-ttu-id="51cd5-212">�� Excel ��ʹ�� C API ���б��</span><span class="sxs-lookup"><span data-stu-id="51cd5-212">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
  
[<span data-ttu-id="51cd5-213">Evaluating Names and Other Worksheet Formula Expressions</span><span class="sxs-lookup"><span data-stu-id="51cd5-213">Evaluating Names and Other Worksheet Formula Expressions</span></span>](evaluating-names-and-other-worksheet-formula-expressions.md)
  
[<span data-ttu-id="51cd5-214">Excel XLL SDK API Function Reference</span><span class="sxs-lookup"><span data-stu-id="51cd5-214">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)

