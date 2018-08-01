---
title: 在 Excel 中访问 DLL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- 访问 [excel 2007] 的 dll，在 Excel 中访问 Dll [Excel 2007]
localization_priority: Normal
ms.assetid: e2bfd6ea-efa3-45c1-a5b8-2ccb8650c6ab
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: bfb562b6bbe824124c6b5a691745d076720ee004
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773753"
---
# <a name="access-dlls-in-excel"></a><span data-ttu-id="db9dd-104">在 Excel 中访问 DLL</span><span class="sxs-lookup"><span data-stu-id="db9dd-104">Access DLLs in Excel</span></span>

<span data-ttu-id="db9dd-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="db9dd-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="db9dd-106">您可以访问的 DLL 函数或几种方式在 Microsoft Excel 中的命令：</span><span class="sxs-lookup"><span data-stu-id="db9dd-106">You can access a DLL function or command in Microsoft Excel in several ways:</span></span>
  
- <span data-ttu-id="db9dd-107">通过 Microsoft Visual Basic for Applications (VBA) 代码模块中的函数或命令进行了可使用**Declare**语句。</span><span class="sxs-lookup"><span data-stu-id="db9dd-107">Through a Microsoft Visual Basic for Applications (VBA) code module in which the function or command has been made available using a **Declare** statement.</span></span> 
    
- <span data-ttu-id="db9dd-108">通过使用**呼叫**或**注册**函数 XLM 宏表。</span><span class="sxs-lookup"><span data-stu-id="db9dd-108">Through an XLM macro sheet by using the **CALL** or **REGISTER** functions.</span></span> 
    
- <span data-ttu-id="db9dd-109">直接从工作表或从自定义项中用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="db9dd-109">Directly from the worksheet or from a customized item in the user interface (UI).</span></span>
    
<span data-ttu-id="db9dd-110">本文档不适用于 XLM 函数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-110">This documentation does not cover XLM functions.</span></span> <span data-ttu-id="db9dd-111">建议您将使用其他两种方法。</span><span class="sxs-lookup"><span data-stu-id="db9dd-111">It is recommended that you use either of the other two approaches.</span></span>
  
<span data-ttu-id="db9dd-112">要访问直接从工作表或在 UI 中的自定义项，函数或命令必须首先注册使用 Excel。</span><span class="sxs-lookup"><span data-stu-id="db9dd-112">To be accessed directly from the worksheet or from a customized item in the UI, the function or command must first be registered with Excel.</span></span> <span data-ttu-id="db9dd-113">有关注册命令和函数的信息，请参阅[在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="db9dd-113">For information about registering commands and functions, see [Accessing XLL Code in Excel](accessing-xll-code-in-excel.md).</span></span>
  
## <a name="calling-dll-functions-and-commands-from-vba"></a><span data-ttu-id="db9dd-114">从 VBA 中调用的 DLL 函数和命令</span><span class="sxs-lookup"><span data-stu-id="db9dd-114">Calling DLL functions and commands from VBA</span></span>

<span data-ttu-id="db9dd-115">可以使用**Declare**语句中访问 DLL 函数和 VBA 中的命令。</span><span class="sxs-lookup"><span data-stu-id="db9dd-115">You can access DLL functions and commands in VBA by using the **Declare** statement.</span></span> <span data-ttu-id="db9dd-116">此语句包含一个语法的命令，另一个用于函数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-116">This statement has one syntax for commands and one for functions.</span></span> 
  
- <span data-ttu-id="db9dd-117">**语法 1-命令**</span><span class="sxs-lookup"><span data-stu-id="db9dd-117">**Syntax 1 - commands**</span></span>
    
  ```vb
  [Public | Private] Declare Sub name Lib "libname" [Alias "aliasname"] [([arglist])]
  ```

- <span data-ttu-id="db9dd-118">**语法 2-函数**</span><span class="sxs-lookup"><span data-stu-id="db9dd-118">**Syntax 2 - functions**</span></span>
    
  ```vb
  [Public | Private] Declare Function name Lib "libname" [Alias "aliasname"] [([arglist])] [As type]
  ```

<span data-ttu-id="db9dd-119">可选的**公用**和**专用**关键字指定导入函数的作用域： 整个 Visual Basic 项目或只是 Visual Basic 模块，分别。</span><span class="sxs-lookup"><span data-stu-id="db9dd-119">The optional **Public** and **Private** keywords specify the scope of the imported function: the entire Visual Basic project or just the Visual Basic module, respectively.</span></span> <span data-ttu-id="db9dd-120">名称是想要在 VBA 代码中使用的名称。</span><span class="sxs-lookup"><span data-stu-id="db9dd-120">The name is the name that you want to use in the VBA code.</span></span> <span data-ttu-id="db9dd-121">如果这与在 DLL 中的名称，您必须使用别名"aliasname"说明符，并应授予函数的名称，如 DLL 导出。</span><span class="sxs-lookup"><span data-stu-id="db9dd-121">If this differs from the name in the DLL, you must use the Alias "aliasname" specifier, and you should give the name of the function as exported by the DLL.</span></span> <span data-ttu-id="db9dd-122">如果您想要访问的 DLL 函数引用一个 DLL 的序号，必须提供别名，即序号前缀**#**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-122">If you want to access a DLL function by reference to a DLL ordinal number, you must provide an alias name, which is the ordinal prefixed by **#**.</span></span>
  
<span data-ttu-id="db9dd-123">命令应返回**void**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-123">Commands should return **void**.</span></span> <span data-ttu-id="db9dd-124">函数的 VBA 应返回类型可以识别**ByVal**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-124">Functions should return types that VBA can recognize **ByVal**.</span></span> <span data-ttu-id="db9dd-125">这意味着，更轻松地通过修改就地参数返回某些类型： 字符串、 数组、 用户定义类型和对象。</span><span class="sxs-lookup"><span data-stu-id="db9dd-125">This means that some types are more easily returned by modifying arguments in place: strings, arrays, user-defined types, and objects.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db9dd-126">VBA 无法检查参数列表和 Visual Basic 模块中所述的返回在 DLL 中编码的相同。</span><span class="sxs-lookup"><span data-stu-id="db9dd-126">VBA cannot check that the argument list and return stated in the Visual Basic module are the same as coded in the DLL.</span></span> <span data-ttu-id="db9dd-127">由于错误可能导致 Excel 崩溃，您应从仔细，检查此自己。</span><span class="sxs-lookup"><span data-stu-id="db9dd-127">You should check this yourself very carefully, because a mistake could cause Excel to crash.</span></span> 
  
<span data-ttu-id="db9dd-128">不通过引用或指针传递函数或命令的参数，当他们前面必须有**arglist**声明中的**ByVal**关键字。</span><span class="sxs-lookup"><span data-stu-id="db9dd-128">When the function or command's arguments are not passed by reference or pointer, they must be preceded by the **ByVal** keyword in the **arglist** declaration.</span></span> <span data-ttu-id="db9dd-129">在 C/c + + 函数采用指针参数或 c + + 函数采用引用参数时，应将它们传递**ByRef**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-129">When a C/C++ function takes pointer arguments, or a C++ function takes reference arguments, they should be passed **ByRef**.</span></span> <span data-ttu-id="db9dd-130">可以从参数省略**ByRef**关键字列出因为它是 VBA 中的默认值。</span><span class="sxs-lookup"><span data-stu-id="db9dd-130">The keyword **ByRef** can be omitted from argument lists because it is the default in VBA.</span></span> 
  
### <a name="argument-types-in-cc-and-vba"></a><span data-ttu-id="db9dd-131">C/c + + 和 VBA 中的参数类型</span><span class="sxs-lookup"><span data-stu-id="db9dd-131">Argument types in C/C++ and VBA</span></span>

<span data-ttu-id="db9dd-132">比较 C/c + + 和 VBA 中的参数类型的声明时，您应注意以下。</span><span class="sxs-lookup"><span data-stu-id="db9dd-132">You should note the following when you compare the declarations of argument types in C/C++ and VBA.</span></span>
  
- <span data-ttu-id="db9dd-133">VBA**字符串**作为指针传递到字节字符串 BSTR 结构时传递 ByVal，和为指向时传递的指针的指针**ByRef**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-133">A VBA **String** is passed as a pointer to a byte-string BSTR structure when passed ByVal, and as a pointer to a pointer when passed **ByRef**.</span></span>
    
- <span data-ttu-id="db9dd-134">VBA**变量**包含字符串作为指针传递到 Unicode 宽字符字符串 BSTR 结构时传递**ByVal**，和为指向时传递的指针的指针**ByRef**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-134">A VBA **Variant** that contains a string is passed as a pointer to a Unicode wide-character string BSTR structure when passed **ByVal**, and as a pointer to a pointer when passed **ByRef**.</span></span>
    
- <span data-ttu-id="db9dd-135">VBA**整数**是等价于签名 short C/c + + 中一个 16 位类型。</span><span class="sxs-lookup"><span data-stu-id="db9dd-135">The VBA **Integer** is a 16-bit type equivalent to a signed short in C/C++.</span></span> 
    
- <span data-ttu-id="db9dd-136">VBA**长**是等价于签名 int C/c + + 中的 32 位类型。</span><span class="sxs-lookup"><span data-stu-id="db9dd-136">The VBA **Long** is a 32-bit type equivalent to a signed int in C/C++.</span></span> 
    
- <span data-ttu-id="db9dd-137">VBA 和 C/c + + 允许用户定义的数据类型的定义分别使用**类型**和**结构**语句。</span><span class="sxs-lookup"><span data-stu-id="db9dd-137">Both VBA and C/C++ allow the definition of user-defined data types, using the **Type** and **struct** statements respectively.</span></span> 
    
- <span data-ttu-id="db9dd-138">VBA 和 C/c + + 支持为 C/c + + 为 VARIANT Windows OLE/COM 头文件中定义的**Variant**数据类型。</span><span class="sxs-lookup"><span data-stu-id="db9dd-138">Both VBA and C/C++ support the **Variant** data type, defined for C/C++ in the Windows OLE/COM header files as VARIANT.</span></span> 
    
- <span data-ttu-id="db9dd-139">VBA 数组是 OLE **SafeArrays**，定义 C/c + + Windows OLE/COM 头文件中为**SAFEARRAY**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-139">VBA arrays are OLE **SafeArrays**, defined for C/C++ in the Windows OLE/COM header files as **SAFEARRAY**.</span></span>
    
- <span data-ttu-id="db9dd-140">作为类型**CY**，在 Windows 标头文件 wtypes.h 中, 定义的结构传递 VBA**货币**数据类型时传递**ByVal**，并作为一个指向此时传递**ByRef**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-140">The VBA **Currency** data type is passed as a structure of type **CY**, defined in the Windows header file wtypes.h, when passed **ByVal**, and as a pointer to this when passed **ByRef**.</span></span>
    
<span data-ttu-id="db9dd-141">在 VBA 中，在用户定义的数据类型的数据元素而在 Visual Studio 中，默认情况下，它们被打包到 8 字节边界至 4 字节边界，打包。</span><span class="sxs-lookup"><span data-stu-id="db9dd-141">In VBA, data elements in user-defined data types are packed to 4-byte boundaries, whereas in Visual Studio, by default, they are packed to 8-byte boundaries.</span></span> <span data-ttu-id="db9dd-142">因此，则必须将中的 C/c + + 结构定义`#pragma pack(4) … #pragma pack()`块，以避免要对齐的元素。</span><span class="sxs-lookup"><span data-stu-id="db9dd-142">Therefore you must enclose the C/C++ structure definition in a `#pragma pack(4) … #pragma pack()` block to avoid elements being misaligned.</span></span> 
  
<span data-ttu-id="db9dd-143">下面是等效的用户类型定义的示例。</span><span class="sxs-lookup"><span data-stu-id="db9dd-143">The following is an example of equivalent user type definitions.</span></span>
  
```vb
Type VB_User_Type
    i As Integer
    d As Double
    s As String
End Type

```

```cpp
#pragma pack(4)
struct C_user_type
{
    short iVal;
    double dVal;
    BSTR bstr; // VBA String type is a byte string
}
#pragma pack() // restore default

```

<span data-ttu-id="db9dd-144">VBA 支持更大的范围的值在某些情况下不是 Excel 支持。</span><span class="sxs-lookup"><span data-stu-id="db9dd-144">VBA supports a greater range of values in some cases than Excel supports.</span></span> <span data-ttu-id="db9dd-145">双 VBA 为 IEEE 兼容，支持 subnormal 是当前向下舍入为工作表上零的数字。</span><span class="sxs-lookup"><span data-stu-id="db9dd-145">The VBA double is IEEE compliant, supporting subnormal numbers that are currently rounded down to zero on the worksheet.</span></span> <span data-ttu-id="db9dd-146">VBA**日期**类型可以表示为使用负序列化的日期的 1-Jan-0100年早日期。</span><span class="sxs-lookup"><span data-stu-id="db9dd-146">The VBA **Date** type can represent dates as early as 1-Jan-0100 using negative serialized dates.</span></span> <span data-ttu-id="db9dd-147">大于或等于零，则 Excel 将只允许序列化的日期。</span><span class="sxs-lookup"><span data-stu-id="db9dd-147">Excel only allows serialized dates greater than or equal to zero.</span></span> <span data-ttu-id="db9dd-148">VBA**货币**类型 — 扩展的 64 位整数 — 可以实现准确性不支持 8 字节双精度数，并因此不匹配工作表中。</span><span class="sxs-lookup"><span data-stu-id="db9dd-148">The VBA **Currency** type—a scaled 64-bit integer—can achieve accuracy not supported in 8-byte doubles, and so is not matched in the worksheet.</span></span> 
  
<span data-ttu-id="db9dd-149">Excel 仅将下列类型的变量传递到 VBA 用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-149">Excel only passes Variants of the following types to a VBA user-defined function.</span></span>
  
|<span data-ttu-id="db9dd-150">**VBA 数据类型**</span><span class="sxs-lookup"><span data-stu-id="db9dd-150">**VBA data type**</span></span>|<span data-ttu-id="db9dd-151">**C/c + + 变量类型的位标志**</span><span class="sxs-lookup"><span data-stu-id="db9dd-151">**C/C++ Variant type bit flags**</span></span>|<span data-ttu-id="db9dd-152">**说明**</span><span class="sxs-lookup"><span data-stu-id="db9dd-152">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="db9dd-153">双精度数</span><span class="sxs-lookup"><span data-stu-id="db9dd-153">Double</span></span>  <br/> |<span data-ttu-id="db9dd-154">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="db9dd-154">**VT_R8**</span></span> <br/> ||
|<span data-ttu-id="db9dd-155">Boolean</span><span class="sxs-lookup"><span data-stu-id="db9dd-155">Boolean</span></span>  <br/> |<span data-ttu-id="db9dd-156">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="db9dd-156">**VT_BOOL**</span></span> <br/> ||
|<span data-ttu-id="db9dd-157">Date</span><span class="sxs-lookup"><span data-stu-id="db9dd-157">Date</span></span>  <br/> |<span data-ttu-id="db9dd-158">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="db9dd-158">**VT_DATE**</span></span> <br/> ||
|<span data-ttu-id="db9dd-159">字符串</span><span class="sxs-lookup"><span data-stu-id="db9dd-159">String</span></span>  <br/> |<span data-ttu-id="db9dd-160">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="db9dd-160">**VT_BSTR**</span></span> <br/> |<span data-ttu-id="db9dd-161">OLE Bstr 字节字符串</span><span class="sxs-lookup"><span data-stu-id="db9dd-161">OLE Bstr byte string</span></span>  <br/> |
|<span data-ttu-id="db9dd-162">Range</span><span class="sxs-lookup"><span data-stu-id="db9dd-162">Range</span></span>  <br/> |<span data-ttu-id="db9dd-163">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="db9dd-163">**VT_DISPATCH**</span></span> <br/> |<span data-ttu-id="db9dd-164">范围和单元格引用</span><span class="sxs-lookup"><span data-stu-id="db9dd-164">Range and cell references</span></span>  <br/> |
|<span data-ttu-id="db9dd-165">包含数组的 variant</span><span class="sxs-lookup"><span data-stu-id="db9dd-165">Variant containing an array</span></span>  <br/> |<span data-ttu-id="db9dd-166">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="db9dd-166">**VT_ARRAY**</span></span> | <span data-ttu-id="db9dd-167">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="db9dd-167">**VT_VARIANT**</span></span> <br/> |<span data-ttu-id="db9dd-168">字面数组</span><span class="sxs-lookup"><span data-stu-id="db9dd-168">Literal arrays</span></span>  <br/> |
|<span data-ttu-id="db9dd-169">Ccy</span><span class="sxs-lookup"><span data-stu-id="db9dd-169">Ccy</span></span>  <br/> |<span data-ttu-id="db9dd-170">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="db9dd-170">**VT_CY**</span></span> <br/> |<span data-ttu-id="db9dd-171">扩展允许的准确性的 4 个小数位的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-171">64-bit integer scaled to permit 4 decimal places of accuracy.</span></span>  <br/> |
|<span data-ttu-id="db9dd-172">包含错误的 variant</span><span class="sxs-lookup"><span data-stu-id="db9dd-172">Variant containing an error</span></span>  <br/> |<span data-ttu-id="db9dd-173">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="db9dd-173">**VT_ERROR**</span></span> <br/> ||
||<span data-ttu-id="db9dd-174">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="db9dd-174">**VT_EMPTY**</span></span> <br/> |<span data-ttu-id="db9dd-175">空单元格或省略的参数</span><span class="sxs-lookup"><span data-stu-id="db9dd-175">Empty cells or omitted arguments</span></span>  <br/> |
   
<span data-ttu-id="db9dd-176">之处在于此函数返回的范围的值，如果调用时带有引用的类型，您可以检查在 VBA 中使用**VarType**，传入的 Variant 的类型。</span><span class="sxs-lookup"><span data-stu-id="db9dd-176">You can check the type of a passed-in Variant in VBA using the **VarType**, except that the function returns the type of the range's values when called with references.</span></span> <span data-ttu-id="db9dd-177">若要确定**变量****范围**reference 对象，您可以使用**IsObject**函数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-177">To determine if a **Variant** is a **Range** reference object, you can use the **IsObject** function.</span></span> 
  
<span data-ttu-id="db9dd-178">您可以创建通过将其**Value**属性分配给**Variant**包含在**范围**中的 VBA 变量型数组的**变量**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-178">You can create **Variants** that contain arrays of variants in VBA from a **Range** by assigning its **Value** property to a **Variant**.</span></span> <span data-ttu-id="db9dd-179">任何源区域中的单元格时使用的区域设置中强制标准的货币格式设置格式转换为**货币**类型的数组元素。</span><span class="sxs-lookup"><span data-stu-id="db9dd-179">Any cells in the source range that are formatted using the standard currency format for the regional settings in force at the time are converted to array elements of type **Currency**.</span></span> <span data-ttu-id="db9dd-180">任何格式设置为日期转换为**日期**类型的数组元素的单元格。</span><span class="sxs-lookup"><span data-stu-id="db9dd-180">Any cells formatted as dates are converted to array elements of type **Date**.</span></span> <span data-ttu-id="db9dd-181">单元格包含字符串转换为宽字符**BSTR**变量。</span><span class="sxs-lookup"><span data-stu-id="db9dd-181">Cells containing strings are converted to wide-character **BSTR** Variants.</span></span> <span data-ttu-id="db9dd-182">含有错误的单元格均转换为**VT_ERROR**类型的**变量**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-182">Cells containing errors are converted to **Variants** of type **VT_ERROR**.</span></span> <span data-ttu-id="db9dd-183">包含**布尔值** **True**或**False**的单元格均转换为**VT_BOOL**类型的**变量**。</span><span class="sxs-lookup"><span data-stu-id="db9dd-183">Cells containing **Boolean** **True** or **False** are converted to **Variants** of type **VT_BOOL**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="db9dd-184">**Variant 类型的值**将存储**True**为-1 和**False**作为 0。</span><span class="sxs-lookup"><span data-stu-id="db9dd-184">The **Variant** stores **True** as -1 and **False** as 0.</span></span> <span data-ttu-id="db9dd-185">不是日期格式数字或货币金额会转换为的类型**VT_R8**变体。</span><span class="sxs-lookup"><span data-stu-id="db9dd-185">Numbers not formatted as dates or currency amounts are converted to Variants of type **VT_R8**.</span></span> 
  
### <a name="variant-and-string-arguments"></a><span data-ttu-id="db9dd-186">Variant 类型的值和字符串参数</span><span class="sxs-lookup"><span data-stu-id="db9dd-186">Variant and string arguments</span></span>

<span data-ttu-id="db9dd-187">Excel 适用于内部的宽字符 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="db9dd-187">Excel works internally with wide-character Unicode strings.</span></span> <span data-ttu-id="db9dd-188">当 VBA 用户定义函数声明为采用**字符串**参数时，Excel 提供将字符串转换为字节字符串的特定于区域设置的方式。</span><span class="sxs-lookup"><span data-stu-id="db9dd-188">When a VBA user-defined function is declared as taking a **String** argument, Excel converts the supplied string to a byte-string in a locale-specific way.</span></span> <span data-ttu-id="db9dd-189">如果您希望您传递一个 Unicode 字符串的函数，您 VBA 用户定义函数应接受**Variant**而不是**字符串**参数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-189">If you want your function to be passed a Unicode string, your VBA user-defined function should accept a **Variant** instead of a **String** argument.</span></span> <span data-ttu-id="db9dd-190">您的 DLL 函数然后可以接受从 VBA 的**Variant** BSTR 宽字符 string。</span><span class="sxs-lookup"><span data-stu-id="db9dd-190">Your DLL function can then accept that **Variant** BSTR wide-character string from VBA.</span></span> 
  
<span data-ttu-id="db9dd-191">若要从 DLL VBA 返回 Unicode 字符串，您应修改就地**Variant**字符串参数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-191">To return Unicode strings to VBA from a DLL, you should modify a **Variant** string argument in place.</span></span> <span data-ttu-id="db9dd-192">为此，您必须声明为**Variant**和在 C/c + + 代码中，采用指针的 DLL 函数和声明为 VBA 代码中的参数`ByRef varg As Variant`。</span><span class="sxs-lookup"><span data-stu-id="db9dd-192">For this to work, you must declare the DLL function as taking a pointer to the **Variant** and in your C/C++ code, and declare the argument in the VBA code as  `ByRef varg As Variant`.</span></span> <span data-ttu-id="db9dd-193">应释放的旧的字符串内存，并使用仅在 DLL 中的 OLE Bstr 字符串函数创建新的字符串值。</span><span class="sxs-lookup"><span data-stu-id="db9dd-193">The old string memory should be released, and the new string value created by using the OLE Bstr string functions only in the DLL.</span></span>
  
<span data-ttu-id="db9dd-194">若要从 DLL VBA 返回一个字节的字符串，您应修改就地字节字符串 BSTR 参数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-194">To return a byte string to VBA from a DLL, you should modify a byte-string BSTR argument in place.</span></span> <span data-ttu-id="db9dd-195">为此，您必须声明为指针指向 BSTR 和 C/c + + 代码，采用指针的 DLL 函数并声明中作为**ByRef varg As String**VBA 代码的参数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-195">For this to work, you must declare the DLL function as taking a pointer to a pointer to the BSTR and in your C/C++ code, and declare the argument in the VBA code as ' **ByRef varg As String**'.</span></span>
  
<span data-ttu-id="db9dd-196">仅应处理传递 VBA 中的以下方式使用 OLE BSTR 字符串函数以避免出现内存相关问题的字符串。</span><span class="sxs-lookup"><span data-stu-id="db9dd-196">You should only handle strings that are passed in these ways from VBA using the OLE BSTR string functions to avoid memory-related problems.</span></span> <span data-ttu-id="db9dd-197">例如，您必须调用**SysFreeString**之前覆盖中传递的字符串，并**SysAllocStringByteLen**或**只能**为一个新字符串分配空间释放内存。</span><span class="sxs-lookup"><span data-stu-id="db9dd-197">For example, you must call **SysFreeString** to free the memory before overwriting the passed in string, and **SysAllocStringByteLen** or **SysAllocStringLen** to allocate space for a new string.</span></span> 
  
<span data-ttu-id="db9dd-198">您可以通过**CVerr**函数使用下表中所示的参数为**变量**在 VBA 中创建 Excel 工作表错误。</span><span class="sxs-lookup"><span data-stu-id="db9dd-198">You can create Excel worksheet errors as **Variants** in VBA by using the **CVerr** function with arguments as shown in the following table.</span></span> <span data-ttu-id="db9dd-199">工作表错误还可返回到 VBA 从 DLL 的**ulVal**字段中使用**变体**类型**VT_ERROR**，并具有以下值。</span><span class="sxs-lookup"><span data-stu-id="db9dd-199">Worksheet errors can also be returned to VBA from a DLL using **Variants** of type **VT_ERROR**, and with the following values in the **ulVal** field.</span></span> 
  
|<span data-ttu-id="db9dd-200">**Error**</span><span class="sxs-lookup"><span data-stu-id="db9dd-200">**Error**</span></span>|<span data-ttu-id="db9dd-201">**Variant ulVal 值**</span><span class="sxs-lookup"><span data-stu-id="db9dd-201">**Variant ulVal value**</span></span>|<span data-ttu-id="db9dd-202">**CVerr 参数**</span><span class="sxs-lookup"><span data-stu-id="db9dd-202">**CVerr argument**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="db9dd-203">#NULL!</span><span class="sxs-lookup"><span data-stu-id="db9dd-203">#NULL!</span></span>  <br/> |<span data-ttu-id="db9dd-204">2148141008</span><span class="sxs-lookup"><span data-stu-id="db9dd-204">2148141008</span></span>  <br/> |<span data-ttu-id="db9dd-205">2000</span><span class="sxs-lookup"><span data-stu-id="db9dd-205">2000</span></span>  <br/> |
|<span data-ttu-id="db9dd-206">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="db9dd-206">#DIV/0!</span></span>  <br/> |<span data-ttu-id="db9dd-207">2148141015</span><span class="sxs-lookup"><span data-stu-id="db9dd-207">2148141015</span></span>  <br/> |<span data-ttu-id="db9dd-208">2007</span><span class="sxs-lookup"><span data-stu-id="db9dd-208">2007</span></span>  <br/> |
|<span data-ttu-id="db9dd-209">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="db9dd-209">#VALUE!</span></span>  <br/> |<span data-ttu-id="db9dd-210">2148141023</span><span class="sxs-lookup"><span data-stu-id="db9dd-210">2148141023</span></span>  <br/> |<span data-ttu-id="db9dd-211">2015</span><span class="sxs-lookup"><span data-stu-id="db9dd-211">2015</span></span>  <br/> |
|<span data-ttu-id="db9dd-212">#REF!</span><span class="sxs-lookup"><span data-stu-id="db9dd-212">#REF!</span></span>  <br/> |<span data-ttu-id="db9dd-213">2148141031</span><span class="sxs-lookup"><span data-stu-id="db9dd-213">2148141031</span></span>  <br/> |<span data-ttu-id="db9dd-214">2023</span><span class="sxs-lookup"><span data-stu-id="db9dd-214">2023</span></span>  <br/> |
|<span data-ttu-id="db9dd-215">#NAME?</span><span class="sxs-lookup"><span data-stu-id="db9dd-215">#NAME?</span></span>  <br/> |<span data-ttu-id="db9dd-216">2148141037</span><span class="sxs-lookup"><span data-stu-id="db9dd-216">2148141037</span></span>  <br/> |<span data-ttu-id="db9dd-217">2029</span><span class="sxs-lookup"><span data-stu-id="db9dd-217">2029</span></span>  <br/> |
|<span data-ttu-id="db9dd-218">#NUM!</span><span class="sxs-lookup"><span data-stu-id="db9dd-218">#NUM!</span></span>  <br/> |<span data-ttu-id="db9dd-219">2148141044</span><span class="sxs-lookup"><span data-stu-id="db9dd-219">2148141044</span></span>  <br/> |<span data-ttu-id="db9dd-220">2036</span><span class="sxs-lookup"><span data-stu-id="db9dd-220">2036</span></span>  <br/> |
|<span data-ttu-id="db9dd-221">#N/A</span><span class="sxs-lookup"><span data-stu-id="db9dd-221">#N/A</span></span>  <br/> |<span data-ttu-id="db9dd-222">2148141050</span><span class="sxs-lookup"><span data-stu-id="db9dd-222">2148141050</span></span>  <br/> |<span data-ttu-id="db9dd-223">2042</span><span class="sxs-lookup"><span data-stu-id="db9dd-223">2042</span></span>  <br/> |
   
<span data-ttu-id="db9dd-224">请注意，给定的 Variant **ulVal**值等于**CVerr**参数值以及 x800A0000 十六进制。</span><span class="sxs-lookup"><span data-stu-id="db9dd-224">Note that the Variant **ulVal** value given is equivalent to the **CVerr** argument value plus x800A0000 hexadecimal.</span></span> 
  
## <a name="calling-dll-functions-directly-from-the-worksheet"></a><span data-ttu-id="db9dd-225">直接从工作表中调用 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="db9dd-225">Calling DLL functions directly from the worksheet</span></span>

<span data-ttu-id="db9dd-226">您无法访问 Win32 DLL 函数从工作表中没有，例如，使用 VBA 或 XLM 接口，或又不允许 Excel 事先知道函数，它的参数以及它的返回类型。</span><span class="sxs-lookup"><span data-stu-id="db9dd-226">You cannot access Win32 DLL functions from the worksheet without, for example, using VBA or XLM as interfaces, or without letting Excel know about the function, its arguments, and its return type in advance.</span></span> <span data-ttu-id="db9dd-227">此操作的过程称为注册。</span><span class="sxs-lookup"><span data-stu-id="db9dd-227">The process of doing this is called registration.</span></span>
  
<span data-ttu-id="db9dd-228">Dll 函数可以访问工作表中的方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="db9dd-228">The ways in which the functions of a DLL can be accessed in the worksheet are as follows:</span></span>
  
- <span data-ttu-id="db9dd-229">声明在 VBA 中的函数，如前面所述并访问通过 VBA 用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-229">Declare the function in VBA as described previously and access it via a VBA user-defined function.</span></span>
    
- <span data-ttu-id="db9dd-230">调用 XLM 宏表，使用呼叫的 DLL 函数和访问通过 XLM 用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-230">Call the DLL function using CALL on an XLM macro sheet, and access it via an XLM user-defined function.</span></span>
    
- <span data-ttu-id="db9dd-231">使用 XLM 或 VBA 命令调用 XLM**注册**的函数，它提供了 Excel 工作表单元格中输入时识别函数所需的信息。</span><span class="sxs-lookup"><span data-stu-id="db9dd-231">Use an XLM or VBA command to call the XLM **REGISTER** function, which provides the information that Excel needs to recognize the function when it is entered into a worksheet cell.</span></span> 
    
- <span data-ttu-id="db9dd-232">将变成 XLL DLL 并注册 XLL 被激活时使用 C API **xlfRegister**函数的函数。</span><span class="sxs-lookup"><span data-stu-id="db9dd-232">Turn the DLL into an XLL and register the function using the C API **xlfRegister** function when the XLL is activated.</span></span> 
    
<span data-ttu-id="db9dd-233">是独立的第四个方法： 注册函数的代码和函数代码都包含在相同的代码项目中。</span><span class="sxs-lookup"><span data-stu-id="db9dd-233">The fourth approach is self-contained: the code that registers the functions and the function code are both contained in the same code project.</span></span> <span data-ttu-id="db9dd-234">对加载项进行的更改不涉及到 XLM 工作表或 VBA 代码模块进行更改。</span><span class="sxs-lookup"><span data-stu-id="db9dd-234">Making changes to the add-in does not involve making changes to an XLM sheet or to a VBA code module.</span></span> <span data-ttu-id="db9dd-235">若要同时仍保持中的 C api 的功能完善管理方式执行此操作，必须将变成 XLL DLL 并加载生成加载项使用加载项管理器。</span><span class="sxs-lookup"><span data-stu-id="db9dd-235">To do this in a well-managed way while still staying within the capabilities of the C API, you must turn your DLL into an XLL and load the resulting add-in by using the Add-in Manager.</span></span> <span data-ttu-id="db9dd-236">这使 Excel 调用的函数，您的 DLL 公开外接程序加载或时激活，从其可以注册的所有包含您 XLL 的功能和任何其他 DLL 初始化执行。</span><span class="sxs-lookup"><span data-stu-id="db9dd-236">This enables Excel to call a function that your DLL exposes when the add-in is loaded or activated, from which you can register all of the functions your XLL contains, and carry out any other DLL initialization.</span></span>
  
## <a name="calling-dll-commands-directly-from-excel"></a><span data-ttu-id="db9dd-237">直接从 Excel 调用 DLL 命令</span><span class="sxs-lookup"><span data-stu-id="db9dd-237">Calling DLL commands directly from Excel</span></span>

<span data-ttu-id="db9dd-238">Win32 DLL 命令将无法访问直接从 Excel 对话框和菜单不存在一个接口，如 VBA，或不提前注册的命令。</span><span class="sxs-lookup"><span data-stu-id="db9dd-238">Win32 DLL commands are not accessible directly from Excel dialog boxes and menus without there being an interface, such as VBA, or without the commands being registered in advance.</span></span>
  
<span data-ttu-id="db9dd-239">您可以在其中访问 DLL 的命令的方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="db9dd-239">The ways in which you can access the commands of a DLL are as follows:</span></span>
  
- <span data-ttu-id="db9dd-240">声明 VBA 中的命令，如前面所述并访问通过 VBA 宏。</span><span class="sxs-lookup"><span data-stu-id="db9dd-240">Declare the command in VBA as described previously and access it via a VBA macro.</span></span>
    
- <span data-ttu-id="db9dd-241">调用 XLM 宏表，使用**调用**DLL 命令并访问通过 XLM 宏。</span><span class="sxs-lookup"><span data-stu-id="db9dd-241">Call the DLL command using **CALL** on an XLM macro sheet, and access it via an XLM macro.</span></span> 
    
- <span data-ttu-id="db9dd-242">使用 XLM 或 VBA 命令调用 XLM**注册**的函数，它提供的信息 Excel 需要识别该命令时输入到一个对话框，需要宏命令的名称。</span><span class="sxs-lookup"><span data-stu-id="db9dd-242">Use an XLM or VBA command to call the XLM **REGISTER** function, which provides the information Excel needs to recognize the command when it is entered into a dialog box that expects the name of a macro command.</span></span> 
    
- <span data-ttu-id="db9dd-243">将变成 XLL DLL 并注册使用 C API **xlfRegister**函数的命令。</span><span class="sxs-lookup"><span data-stu-id="db9dd-243">Turn the DLL into an XLL and register the command using the C API **xlfRegister** function.</span></span> 
    
<span data-ttu-id="db9dd-244">如前面的 DLL 函数上下文中所述，第四个方法是最独立，保持最新的命令代码附近的注册代码。</span><span class="sxs-lookup"><span data-stu-id="db9dd-244">As discussed earlier in the context of DLL functions, the fourth approach is the most self-contained, keeping the registration code close to the command code.</span></span> <span data-ttu-id="db9dd-245">若要执行此操作，必须将变成 XLL DLL 并加载生成加载项使用的加载项管理器。</span><span class="sxs-lookup"><span data-stu-id="db9dd-245">To do this, you must turn your DLL into an XLL and load the resulting add-in using the Add-in Manager.</span></span> <span data-ttu-id="db9dd-246">在这种方式中注册命令还可以将命令附加到的用户界面，例如自定义菜单，元素或设置事件陷阱调用该命令的给定的键击或其他事件。</span><span class="sxs-lookup"><span data-stu-id="db9dd-246">Registering commands in this way also lets you attach the command to an element of the user interface, such as a custom menu, or to set up an event trap that calls the command on a given keystroke or other event.</span></span>
  
<span data-ttu-id="db9dd-247">使用 Excel 中注册的所有 XLL 命令都假定 Excel 的以下形式。</span><span class="sxs-lookup"><span data-stu-id="db9dd-247">All XLL commands that are registered with Excel are assumed by Excel to be of the following form.</span></span>
  
```cpp
int WINAPI my_xll_cmd(void)
{
// Function code...
    return 1;
}
```

> [!NOTE]
> <span data-ttu-id="db9dd-248">除非调用从 XLM 宏工作表，在其中案例的返回值转换为**TRUE**或**FALSE**，则 Excel 会忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="db9dd-248">Excel ignores the return value unless it is called from an XLM macro sheet, in which case the return value is converted to **TRUE** or **FALSE**.</span></span> <span data-ttu-id="db9dd-249">如果它失败或已被用户取消，因此应返回 1 如果您的命令执行成功和 0。</span><span class="sxs-lookup"><span data-stu-id="db9dd-249">You should therefore return 1 if your command executed successfully, and 0 if it failed or was canceled by the user.</span></span> 
  
## <a name="dll-memory-and-multiple-dll-instances"></a><span data-ttu-id="db9dd-250">DLL 内存和多个 DLL 实例</span><span class="sxs-lookup"><span data-stu-id="db9dd-250">DLL memory and multiple DLL instances</span></span>

<span data-ttu-id="db9dd-251">当应用程序加载 DLL 时，该 DLL 可执行代码加载到全局堆，以便它可以运行，并在其数据结构全局堆分配的空间。</span><span class="sxs-lookup"><span data-stu-id="db9dd-251">When an application loads a DLL, the DLL's executable code is loaded into the global heap so that it can be run, and space is allocated on the global heap for its data structures.</span></span> <span data-ttu-id="db9dd-252">Windows 使用内存映射以使显示如同它们位于应用程序的过程中，以便应用程序可以访问这些这些领域的内存。</span><span class="sxs-lookup"><span data-stu-id="db9dd-252">Windows uses memory mapping to make these areas of memory appear as if they are in the application's process so that the application can access them.</span></span>
  
<span data-ttu-id="db9dd-253">如果第二个应用程序然后加载 DLL，Windows 不会创建 DLL 的可执行代码，另一个副本，如内存是只读的。</span><span class="sxs-lookup"><span data-stu-id="db9dd-253">If a second application then loads the DLL, Windows does not make another copy of the DLL executable code, as that memory is read-only.</span></span> <span data-ttu-id="db9dd-254">Windows 将 DLL 可执行代码内存映射到两个应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="db9dd-254">Windows maps the DLL executable code memory to the processes of both applications.</span></span> <span data-ttu-id="db9dd-255">但是，它执行分配第二个空格的 DLL 的数据结构的私有副本并将此副本映射到第二个进程。</span><span class="sxs-lookup"><span data-stu-id="db9dd-255">It does, however, allocate a second space for a private copy of the DLL's data structures and maps this copy to the second process only.</span></span> <span data-ttu-id="db9dd-256">这样可确保不应用程序可能会干扰 DLL 的其他数据。</span><span class="sxs-lookup"><span data-stu-id="db9dd-256">This ensures that neither application can interfere with the DLL data of the other.</span></span>
  
<span data-ttu-id="db9dd-257">这意味着 DLL 开发人员不必担心静态和全局变量和多个应用程序或多个实例的同一应用程序正在访问的数据结构。</span><span class="sxs-lookup"><span data-stu-id="db9dd-257">This means that DLL developers do not have to be concerned about static and global variables and data structures being accessed by more than one application, or more than one instance of the same application.</span></span> <span data-ttu-id="db9dd-258">每个应用程序的每个实例获取其自己的 DLL 数据副本。</span><span class="sxs-lookup"><span data-stu-id="db9dd-258">Every instance of every application gets its own copy of the DLL's data.</span></span>
  
<span data-ttu-id="db9dd-259">DLL 开发人员需要为长短相同的应用程序从不同的线程，调用其 DLL 多次实例，因为这可能会导致争夺该实例的数据。</span><span class="sxs-lookup"><span data-stu-id="db9dd-259">DLL developers do need to be concerned about the same instance of an application calling their DLL many times from different threads, because this can result in contention for that instance's data.</span></span> <span data-ttu-id="db9dd-260">有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="db9dd-260">For more information, see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db9dd-261">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db9dd-261">See also</span></span>

- [<span data-ttu-id="db9dd-262">开发 DLL</span><span class="sxs-lookup"><span data-stu-id="db9dd-262">Developing DLLs</span></span>](developing-dlls.md) 
- [<span data-ttu-id="db9dd-263">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="db9dd-263">Calling into Excel from the DLL or XLL</span></span>](calling-into-excel-from-the-dll-or-xll.md)

