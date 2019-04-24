---
title: 在 Excel 中访问 DLL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- 访问 dll [excel 2007], DLL [Excel 2007], 在 Excel 中访问
ms.assetid: e2bfd6ea-efa3-45c1-a5b8-2ccb8650c6ab
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: fac4ad30048aa1bf3879009bc97ea46a112a9ce5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304009"
---
# <a name="access-dlls-in-excel"></a><span data-ttu-id="a5aa1-104">在 Excel 中访问 DLL</span><span class="sxs-lookup"><span data-stu-id="a5aa1-104">Access DLLs in Excel</span></span>

<span data-ttu-id="a5aa1-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a5aa1-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a5aa1-106">可以通过以下几种方式在 Microsoft Excel 中访问 DLL 函数：</span><span class="sxs-lookup"><span data-stu-id="a5aa1-106">You can access a DLL function or command in Microsoft Excel in several ways:</span></span>
  
- <span data-ttu-id="a5aa1-107">通过 Microsoft Visual Basic for Applications (VBA) 代码模块，其中可使用 **Declare** 语句使用函数或命令。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-107">Through a Microsoft Visual Basic for Applications (VBA) code module in which the function or command has been made available using a **Declare** statement.</span></span> 
    
- <span data-ttu-id="a5aa1-108">通过使用 **CALL** 或 **REGISTER** 函数的 XLM 宏工作表。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-108">Through an XLM macro sheet by using the **CALL** or **REGISTER** functions.</span></span> 
    
- <span data-ttu-id="a5aa1-109">直接通过工作表或者通过用户界面 (UI) 中的自定义项。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-109">Directly from the worksheet or from a customized item in the user interface (UI).</span></span>
    
<span data-ttu-id="a5aa1-110">本文档未介绍 XLM 函数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-110">This documentation does not cover XLM functions.</span></span> <span data-ttu-id="a5aa1-111">建议你使用其他两种方法之一。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-111">It is recommended that you use either of the other two approaches.</span></span>
  
<span data-ttu-id="a5aa1-112">若要直接通过工作表或者 UI 中的自定义项访问，必须在 Excel 中注册函数或命令。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-112">To be accessed directly from the worksheet or from a customized item in the UI, the function or command must first be registered with Excel.</span></span> <span data-ttu-id="a5aa1-113">有关注册命令和函数的信息，请参阅[在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-113">For information about registering commands and functions, see [Accessing XLL Code in Excel](accessing-xll-code-in-excel.md).</span></span>
  
## <a name="calling-dll-functions-and-commands-from-vba"></a><span data-ttu-id="a5aa1-114">通过 VBA 调用 DLL 函数和命令</span><span class="sxs-lookup"><span data-stu-id="a5aa1-114">Calling DLL functions and commands from VBA</span></span>

<span data-ttu-id="a5aa1-115">可以使用 **Declare** 语句访问 VBA 中的 DLL 函数和命令。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-115">You can access DLL functions and commands in VBA by using the **Declare** statement.</span></span> <span data-ttu-id="a5aa1-116">该语句中包含一个命令语法和一个函数语法。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-116">This statement has one syntax for commands and one for functions.</span></span> 
  
- <span data-ttu-id="a5aa1-117">**语法 1 - 命令**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-117">**Syntax 1 - commands**</span></span>
    
  ```vb
  [Public | Private] Declare Sub name Lib "libname" [Alias "aliasname"] [([arglist])]
  ```

- <span data-ttu-id="a5aa1-118">**语法 2 - 函数**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-118">**Syntax 2 - functions**</span></span>
    
  ```vb
  [Public | Private] Declare Function name Lib "libname" [Alias "aliasname"] [([arglist])] [As type]
  ```

<span data-ttu-id="a5aa1-119">可选**公用**和**专用**关键字用于指定所导入函数的范围：整个 Visual Basic 项目还是仅 Visual Basic 模块。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-119">The optional **Public** and **Private** keywords specify the scope of the imported function: the entire Visual Basic project or just the Visual Basic module, respectively.</span></span> <span data-ttu-id="a5aa1-120">此名称为想要在 VBA 代码中使用的名称。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-120">The name is the name that you want to use in the VBA code.</span></span> <span data-ttu-id="a5aa1-121">如果它与 DL 中的名称不同，则必须使用别名“aliasname”说明符，并且应赋予函数 DLL 所导出的名称。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-121">If this differs from the name in the DLL, you must use the Alias "aliasname" specifier, and you should give the name of the function as exported by the DLL.</span></span> <span data-ttu-id="a5aa1-122">如果想要通过引用 DLL 序号访问 DLL 函数，则必须提供别名（以 **#** 为前缀的序数）。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-122">If you want to access a DLL function by reference to a DLL ordinal number, you must provide an alias name, which is the ordinal prefixed by **#**.</span></span>
  
<span data-ttu-id="a5aa1-123">命令应返回 **void**。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-123">Commands should return **void**.</span></span> <span data-ttu-id="a5aa1-124">函数应返回 VBA 可识别 **ByVal** 的类型。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-124">Functions should return types that VBA can recognize **ByVal**.</span></span> <span data-ttu-id="a5aa1-125">这意味着，某些类型可以通过修改相应的参数更轻松地返回：字符串、数组、用户定义的类型和对象。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-125">This means that some types are more easily returned by modifying arguments in place: strings, arrays, user-defined types, and objects.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5aa1-126">VBA 无法检查 Visual Basic 模块中的参数列表和返回内容是否与 DLL 中的代码相同。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-126">VBA cannot check that the argument list and return stated in the Visual Basic module are the same as coded in the DLL.</span></span> <span data-ttu-id="a5aa1-127">需要你自己亲自仔细检查，因为如果出错，则会导致 Excel 崩溃。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-127">You should check this yourself very carefully, because a mistake could cause Excel to crash.</span></span> 
  
<span data-ttu-id="a5aa1-128">如果函数或命令的参数不是通过引用或指针传递，则它们必须以 **arglist** 声明中的 **ByVal** 关键字开头。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-128">When the function or command's arguments are not passed by reference or pointer, they must be preceded by the **ByVal** keyword in the **arglist** declaration.</span></span> <span data-ttu-id="a5aa1-129">当 C/C++ 函数采用指针参数时，或者 C++ 函数采用引用参数时，它们应以 **ByRef** 传递。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-129">When a C/C++ function takes pointer arguments, or a C++ function takes reference arguments, they should be passed **ByRef**.</span></span> <span data-ttu-id="a5aa1-130">参数列表中的关键字 **ByRef** 可以省略，因为它在 VBA 中为默认值。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-130">The keyword **ByRef** can be omitted from argument lists because it is the default in VBA.</span></span> 
  
### <a name="argument-types-in-cc-and-vba"></a><span data-ttu-id="a5aa1-131">C/C++ 和 VBA 中的参数类型</span><span class="sxs-lookup"><span data-stu-id="a5aa1-131">Argument types in C/C++ and VBA</span></span>

<span data-ttu-id="a5aa1-132">比较 C/C++ 和 VBA 中的参数类型声明时，应注意以下事项。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-132">You should note the following when you compare the declarations of argument types in C/C++ and VBA.</span></span>
  
- <span data-ttu-id="a5aa1-133">VBA **String** 在传递 ByVal 时作为指针传递至字节字符串 BSTR 结构，而在传递 **ByRef** 时作为指针传递至指针。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-133">A VBA **String** is passed as a pointer to a byte-string BSTR structure when passed ByVal, and as a pointer to a pointer when passed **ByRef**.</span></span>
    
- <span data-ttu-id="a5aa1-134">VBA **变体**包含一个字符串，该字符串在传递 **ByVal** 时作为指针传递至 Unicode 宽字符字符串 BSTR 结构，并在传递 **ByRef** 时作为指针传递至指针。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-134">A VBA **Variant** that contains a string is passed as a pointer to a Unicode wide-character string BSTR structure when passed **ByVal**, and as a pointer to a pointer when passed **ByRef**.</span></span>
    
- <span data-ttu-id="a5aa1-135">VBA **Integer** 是一个 16 位类型的值，等同于 C/C++ 中的有符号短整。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-135">The VBA **Integer** is a 16-bit type equivalent to a signed short in C/C++.</span></span> 
    
- <span data-ttu-id="a5aa1-136">VBA **Long** 是一个 32 位类型的值，等同于 C/C++ 中的有符号整数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-136">The VBA **Long** is a 32-bit type equivalent to a signed int in C/C++.</span></span> 
    
- <span data-ttu-id="a5aa1-137">VBA 和 C/C++ 分别使用 **Type** 和 **struct** 语句支持用户定义的数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-137">Both VBA and C/C++ allow the definition of user-defined data types, using the **Type** and **struct** statements respectively.</span></span> 
    
- <span data-ttu-id="a5aa1-138">VBA 和 C/C++ 支持**变体**数据类型，它在 Windows OLE/COM 头文件的 C/C 中被定义为 VARIANT。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-138">Both VBA and C/C++ support the **Variant** data type, defined for C/C++ in the Windows OLE/COM header files as VARIANT.</span></span> 
    
- <span data-ttu-id="a5aa1-139">VBA 数组为 OLE **SafeArrays**，它在 Windows OLE/COM 头文件的 C/C 中被定义为 **SAFEARRAY**。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-139">VBA arrays are OLE **SafeArrays**, defined for C/C++ in the Windows OLE/COM header files as **SAFEARRAY**.</span></span>
    
- <span data-ttu-id="a5aa1-140">VBA **Currency** 数据类型作为 **CY** 类型结构传递且在 Windows 头文件 wtypes.h 中定义（传递 **ByVal** 时），并作为指针传递至指针（传递 **ByRef** 时）。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-140">The VBA **Currency** data type is passed as a structure of type **CY**, defined in the Windows header file wtypes.h, when passed **ByVal**, and as a pointer to this when passed **ByRef**.</span></span>
    
<span data-ttu-id="a5aa1-141">在 VBA 中，用户定义的数据类型中的数据元素将打包为 4 字节边界，而在 Visual Studio 中，它们默认打包为 8 字节边界。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-141">In VBA, data elements in user-defined data types are packed to 4-byte boundaries, whereas in Visual Studio, by default, they are packed to 8-byte boundaries.</span></span> <span data-ttu-id="a5aa1-142">因此，必须将 `#pragma pack(4) … #pragma pack()` 块中的 C/C++ 结构定义括起来，以免元素未对齐。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-142">Therefore you must enclose the C/C++ structure definition in a `#pragma pack(4) … #pragma pack()` block to avoid elements being misaligned.</span></span> 
  
<span data-ttu-id="a5aa1-143">以下示例所示为等效用户类型定义。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-143">The following is an example of equivalent user type definitions.</span></span>
  
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

<span data-ttu-id="a5aa1-144">在某些情况下，VBA 比 Excel 支持的值范围更大。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-144">VBA supports a greater range of values in some cases than Excel supports.</span></span> <span data-ttu-id="a5aa1-145">VBA 双精度符合 IEEE 标准，支持工作表中当前已四舍五入为零的次正规数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-145">The VBA double is IEEE compliant, supporting subnormal numbers that are currently rounded down to zero on the worksheet.</span></span> <span data-ttu-id="a5aa1-146">VBA **Date** 类型可使用负序列化日期表示早至 0100 年 1 月 1 日的日期。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-146">The VBA **Date** type can represent dates as early as 1-Jan-0100 using negative serialized dates.</span></span> <span data-ttu-id="a5aa1-147">Excel 仅支持大于或等于零的序列化日期。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-147">Excel only allows serialized dates greater than or equal to zero.</span></span> <span data-ttu-id="a5aa1-148">VBA **Currency** 类型（成比例的 64 位整数）可以实现 8 字节双精度上不支持的精度，这也与工作表不匹配。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-148">The VBA **Currency** type—a scaled 64-bit integer—can achieve accuracy not supported in 8-byte doubles, and so is not matched in the worksheet.</span></span> 
  
<span data-ttu-id="a5aa1-149">Excel 仅可将以下类型的变体传递至 VBA 用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-149">Excel only passes Variants of the following types to a VBA user-defined function.</span></span>
  
|<span data-ttu-id="a5aa1-150">**VBA 数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-150">**VBA data type**</span></span>|<span data-ttu-id="a5aa1-151">**C/C++ 变体类型位标志**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-151">**C/C++ Variant type bit flags**</span></span>|<span data-ttu-id="a5aa1-152">**说明**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-152">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a5aa1-153">双精度</span><span class="sxs-lookup"><span data-stu-id="a5aa1-153">Double</span></span>  <br/> |<span data-ttu-id="a5aa1-154">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-154">**VT_R8**</span></span> <br/> ||
|<span data-ttu-id="a5aa1-155">布尔值</span><span class="sxs-lookup"><span data-stu-id="a5aa1-155">Boolean</span></span>  <br/> |<span data-ttu-id="a5aa1-156">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-156">**VT_BOOL**</span></span> <br/> ||
|<span data-ttu-id="a5aa1-157">日期</span><span class="sxs-lookup"><span data-stu-id="a5aa1-157">Date</span></span>  <br/> |<span data-ttu-id="a5aa1-158">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-158">**VT_DATE**</span></span> <br/> ||
|<span data-ttu-id="a5aa1-159">字符串</span><span class="sxs-lookup"><span data-stu-id="a5aa1-159">String</span></span>  <br/> |<span data-ttu-id="a5aa1-160">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-160">**VT_BSTR**</span></span> <br/> |<span data-ttu-id="a5aa1-161">OLE Bstr 字节字符串</span><span class="sxs-lookup"><span data-stu-id="a5aa1-161">OLE Bstr byte string</span></span>  <br/> |
|<span data-ttu-id="a5aa1-162">区域</span><span class="sxs-lookup"><span data-stu-id="a5aa1-162">Range</span></span>  <br/> |<span data-ttu-id="a5aa1-163">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-163">**VT_DISPATCH**</span></span> <br/> |<span data-ttu-id="a5aa1-164">区域和单元格引用</span><span class="sxs-lookup"><span data-stu-id="a5aa1-164">Range and cell references</span></span>  <br/> |
|<span data-ttu-id="a5aa1-165">包含数组的变体</span><span class="sxs-lookup"><span data-stu-id="a5aa1-165">Variant containing an array</span></span>  <br/> |<span data-ttu-id="a5aa1-166">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-166">**VT_ARRAY**</span></span> | <span data-ttu-id="a5aa1-167">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-167">**VT_VARIANT**</span></span> <br/> |<span data-ttu-id="a5aa1-168">文本数组</span><span class="sxs-lookup"><span data-stu-id="a5aa1-168">Literal arrays</span></span>  <br/> |
|<span data-ttu-id="a5aa1-169">Ccy</span><span class="sxs-lookup"><span data-stu-id="a5aa1-169">Ccy</span></span>  <br/> |<span data-ttu-id="a5aa1-170">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-170">**VT_CY**</span></span> <br/> |<span data-ttu-id="a5aa1-171">64 位成比例整数，支持 4 位小数位数的精度。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-171">64-bit integer scaled to permit 4 decimal places of accuracy.</span></span>  <br/> |
|<span data-ttu-id="a5aa1-172">包含错误的变体</span><span class="sxs-lookup"><span data-stu-id="a5aa1-172">Variant containing an error</span></span>  <br/> |<span data-ttu-id="a5aa1-173">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-173">**VT_ERROR**</span></span> <br/> ||
||<span data-ttu-id="a5aa1-174">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-174">**VT_EMPTY**</span></span> <br/> |<span data-ttu-id="a5aa1-175">空单元格或已省略的参数</span><span class="sxs-lookup"><span data-stu-id="a5aa1-175">Empty cells or omitted arguments</span></span>  <br/> |
   
<span data-ttu-id="a5aa1-176">可以使用 **VarType** 检查 VBA 中的传入变体类型，通过引用调用时返回区域值类型的函数除外。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-176">You can check the type of a passed-in Variant in VBA using the **VarType**, except that the function returns the type of the range's values when called with references.</span></span> <span data-ttu-id="a5aa1-177">若要确定**变体\*\*\*\*区域**引用对象，可以使用 **IsObject** 函数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-177">To determine if a **Variant** is a **Range** reference object, you can use the **IsObject** function.</span></span> 
  
<span data-ttu-id="a5aa1-178">可以从**区域**创建 VBA 中包含变体数组的**变体**，方法是将其**值**属性指定为**变量**。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-178">You can create **Variants** that contain arrays of variants in VBA from a **Range** by assigning its **Value** property to a **Variant**.</span></span> <span data-ttu-id="a5aa1-179">源区域中使用当时的区域设置中的标准货币格式的所有单元格均将转换为**货币**类型的数组元素。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-179">Any cells in the source range that are formatted using the standard currency format for the regional settings in force at the time are converted to array elements of type **Currency**.</span></span> <span data-ttu-id="a5aa1-180">采用日期格式的所有单元格均将转换为**日期**类型的数组元素。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-180">Any cells formatted as dates are converted to array elements of type **Date**.</span></span> <span data-ttu-id="a5aa1-181">包含字符串的单元格将转换为宽字符 **BSTR** 变体。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-181">Cells containing strings are converted to wide-character **BSTR** Variants.</span></span> <span data-ttu-id="a5aa1-182">包含错误的单元格将转换为 **VT_ERROR** 类型的**变体**。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-182">Cells containing errors are converted to **Variants** of type **VT_ERROR**.</span></span> <span data-ttu-id="a5aa1-183">包含**布尔表达式** **True** 或 **False** 的单元格将转换为 **VT_BOOL** 类型的**变体**。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-183">Cells containing **Boolean** **True** or **False** are converted to **Variants** of type **VT_BOOL**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a5aa1-184">**变体**将 **True** 存储为 -1，将 **False** 存储为 0。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-184">The **Variant** stores **True** as -1 and **False** as 0.</span></span> <span data-ttu-id="a5aa1-185">未采用日期或货币金额格式的数字将转化为 **VT_R8** 类型的变体。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-185">Numbers not formatted as dates or currency amounts are converted to Variants of type **VT_R8**.</span></span> 
  
### <a name="variant-and-string-arguments"></a><span data-ttu-id="a5aa1-186">变体和字符串参数</span><span class="sxs-lookup"><span data-stu-id="a5aa1-186">Variant and string arguments</span></span>

<span data-ttu-id="a5aa1-187">Excel 从内部使用宽字符 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-187">Excel works internally with wide-character Unicode strings.</span></span> <span data-ttu-id="a5aa1-188">如果 VBA 用户定义的函数被声明为采用**字符串**参数，则 Excel 将以特定于区域设置的方式将提供的字符串转换为字节字符串。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-188">When a VBA user-defined function is declared as taking a **String** argument, Excel converts the supplied string to a byte-string in a locale-specific way.</span></span> <span data-ttu-id="a5aa1-189">如果想要函数传递为 Unicode 字符串，则 VBA 用户定义的函数应接受**变体**而不是**字符串**参数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-189">If you want your function to be passed a Unicode string, your VBA user-defined function should accept a **Variant** instead of a **String** argument.</span></span> <span data-ttu-id="a5aa1-190">DLL 函数随后可接受 VBA 中的**变体** BSTR 宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-190">Your DLL function can then accept that **Variant** BSTR wide-character string from VBA.</span></span> 
  
<span data-ttu-id="a5aa1-191">若要将 Unicode 字符串从 DLL 返回至 VBA，应相应地修改**变体**字符串参数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-191">To return Unicode strings to VBA from a DLL, you should modify a **Variant** string argument in place.</span></span> <span data-ttu-id="a5aa1-192">为此，必须将 DLL 函数声明为将指针指向**变体**和 C/C++ 代码，并将 VBA 代码中的参数声明为 `ByRef varg As Variant`。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-192">For this to work, you must declare the DLL function as taking a pointer to the **Variant** and in your C/C++ code, and declare the argument in the VBA code as  `ByRef varg As Variant`.</span></span> <span data-ttu-id="a5aa1-193">应擦除原先的字符串内存，并且使用 OLE Bstr 字符串函数创建的新字符串只能在 DLL 中运行。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-193">The old string memory should be released, and the new string value created by using the OLE Bstr string functions only in the DLL.</span></span>
  
<span data-ttu-id="a5aa1-194">若要将字节字符串从 DLL 返回至 VBA，应相应地修改字节字符串 BSTR 参数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-194">To return a byte string to VBA from a DLL, you should modify a byte-string BSTR argument in place.</span></span> <span data-ttu-id="a5aa1-195">为此，必须将 DLL 函数声明为将指针指向 BSTR 指针和 C/C++ 代码，并将 VBA 代码中的参数声明为“**ByRef varg As String**”。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-195">For this to work, you must declare the DLL function as taking a pointer to a pointer to the BSTR and in your C/C++ code, and declare the argument in the VBA code as ' **ByRef varg As String**'.</span></span>
  
<span data-ttu-id="a5aa1-196">应仅使用 OLE BSTR 字符串函数处理以这些方式从 VBA 传递的字符串，以免出现与内存相关的问题。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-196">You should only handle strings that are passed in these ways from VBA using the OLE BSTR string functions to avoid memory-related problems.</span></span> <span data-ttu-id="a5aa1-197">例如，必须先调用 **SysFreeString** 以释放内存，然后再覆盖传入的字符串，并调用 **SysAllocStringByteLen** 或 **SysAllocStringLen** 为新字符串分配空间。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-197">For example, you must call **SysFreeString** to free the memory before overwriting the passed in string, and **SysAllocStringByteLen** or **SysAllocStringLen** to allocate space for a new string.</span></span> 
  
<span data-ttu-id="a5aa1-198">可以结合使用 **CVerr** 函数和下表中所示的参数，以在 VBA 中创建如**变体**一样的 Excel 工作表错误。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-198">You can create Excel worksheet errors as **Variants** in VBA by using the **CVerr** function with arguments as shown in the following table.</span></span> <span data-ttu-id="a5aa1-199">此外，还可以使用 **VT_ERROR** 类型的**变体**以及以下**ulVal**字段值，将工作表错误返回至 VBA。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-199">Worksheet errors can also be returned to VBA from a DLL using **Variants** of type **VT_ERROR**, and with the following values in the **ulVal** field.</span></span> 
  
|<span data-ttu-id="a5aa1-200">**错误**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-200">**Error**</span></span>|<span data-ttu-id="a5aa1-201">**变体 ulVal 值**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-201">**Variant ulVal value**</span></span>|<span data-ttu-id="a5aa1-202">**CVerr参数**</span><span class="sxs-lookup"><span data-stu-id="a5aa1-202">**CVerr argument**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a5aa1-203">#NULL!</span><span class="sxs-lookup"><span data-stu-id="a5aa1-203">#NULL!</span></span>  <br/> |<span data-ttu-id="a5aa1-204">2148141008</span><span class="sxs-lookup"><span data-stu-id="a5aa1-204">2148141008</span></span>  <br/> |<span data-ttu-id="a5aa1-205">2000</span><span class="sxs-lookup"><span data-stu-id="a5aa1-205">2,000</span></span>  <br/> |
|<span data-ttu-id="a5aa1-206">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="a5aa1-206">#DIV/0!</span></span>  <br/> |<span data-ttu-id="a5aa1-207">2148141015</span><span class="sxs-lookup"><span data-stu-id="a5aa1-207">2148141015</span></span>  <br/> |<span data-ttu-id="a5aa1-208">2007</span><span class="sxs-lookup"><span data-stu-id="a5aa1-208">Word 2007</span></span>  <br/> |
|<span data-ttu-id="a5aa1-209">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="a5aa1-209">#VALUE!</span></span>  <br/> |<span data-ttu-id="a5aa1-210">2148141023</span><span class="sxs-lookup"><span data-stu-id="a5aa1-210">2148141023</span></span>  <br/> |<span data-ttu-id="a5aa1-211">2015</span><span class="sxs-lookup"><span data-stu-id="a5aa1-211">December 2015</span></span>  <br/> |
|<span data-ttu-id="a5aa1-212">#REF!</span><span class="sxs-lookup"><span data-stu-id="a5aa1-212">#REF!</span></span>  <br/> |<span data-ttu-id="a5aa1-213">2148141031</span><span class="sxs-lookup"><span data-stu-id="a5aa1-213">2148141031</span></span>  <br/> |<span data-ttu-id="a5aa1-214">2023</span><span class="sxs-lookup"><span data-stu-id="a5aa1-214">2023</span></span>  <br/> |
|<span data-ttu-id="a5aa1-215">#NAME?</span><span class="sxs-lookup"><span data-stu-id="a5aa1-215">#NAME?</span></span>  <br/> |<span data-ttu-id="a5aa1-216">2148141037</span><span class="sxs-lookup"><span data-stu-id="a5aa1-216">2148141037</span></span>  <br/> |<span data-ttu-id="a5aa1-217">2029</span><span class="sxs-lookup"><span data-stu-id="a5aa1-217">2029</span></span>  <br/> |
|<span data-ttu-id="a5aa1-218">#NUM!</span><span class="sxs-lookup"><span data-stu-id="a5aa1-218">#NUM!</span></span>  <br/> |<span data-ttu-id="a5aa1-219">2148141044</span><span class="sxs-lookup"><span data-stu-id="a5aa1-219">2148141044</span></span>  <br/> |<span data-ttu-id="a5aa1-220">2036</span><span class="sxs-lookup"><span data-stu-id="a5aa1-220">2036</span></span>  <br/> |
|<span data-ttu-id="a5aa1-221">#N/A</span><span class="sxs-lookup"><span data-stu-id="a5aa1-221">#N/A</span></span>  <br/> |<span data-ttu-id="a5aa1-222">2148141050</span><span class="sxs-lookup"><span data-stu-id="a5aa1-222">2148141050</span></span>  <br/> |<span data-ttu-id="a5aa1-223">2042</span><span class="sxs-lookup"><span data-stu-id="a5aa1-223">2042</span></span>  <br/> |
   
<span data-ttu-id="a5aa1-224">请注意，提供的变体 **ulVal** 值等于 **CVerr** 参数值加上 x800A0000 十六进制值。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-224">Note that the Variant **ulVal** value given is equivalent to the **CVerr** argument value plus x800A0000 hexadecimal.</span></span> 
  
## <a name="calling-dll-functions-directly-from-the-worksheet"></a><span data-ttu-id="a5aa1-225">直接从工作表调用 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="a5aa1-225">Calling DLL functions directly from the worksheet</span></span>

<span data-ttu-id="a5aa1-226">例如，如果没有将 VBA 或 XLM 用作接口，或者没有让 Excel 提前知道气焊、其参数及其返回类型，则无法从工作表返回 Win32 DLL 函数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-226">You cannot access Win32 DLL functions from the worksheet without, for example, using VBA or XLM as interfaces, or without letting Excel know about the function, its arguments, and its return type in advance.</span></span> <span data-ttu-id="a5aa1-227">此操作过程称为注册。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-227">The process of doing this is called registration.</span></span>
  
<span data-ttu-id="a5aa1-228">可在工作表中访问 DLL 函数的方式如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5aa1-228">The ways in which the functions of a DLL can be accessed in the worksheet are as follows:</span></span>
  
- <span data-ttu-id="a5aa1-229">按上面所述在 VBA 中声明函数，然后通过 VBA 用户定义的函数访问它。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-229">Declare the function in VBA as described previously and access it via a VBA user-defined function.</span></span>
    
- <span data-ttu-id="a5aa1-230">使用 XLM 宏工作表上的 CALL 调用 DLL 函数，然后通过 XLM 用户定义的函数访问它。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-230">Call the DLL function using CALL on an XLM macro sheet, and access it via an XLM user-defined function.</span></span>
    
- <span data-ttu-id="a5aa1-231">使用 XLM 或 VBA 命令调用 XLM **REGISTER** 函数，这将会提供 Excel 识别函数（在函数被输入到工作表单元格时）所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-231">Use an XLM or VBA command to call the XLM **REGISTER** function, which provides the information that Excel needs to recognize the function when it is entered into a worksheet cell.</span></span> 
    
- <span data-ttu-id="a5aa1-232">将 DLL 变为 XLL 并在 XLL 激活时使用 C API **xlfRegister** 函数注册函数。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-232">Turn the DLL into an XLL and register the function using the C API **xlfRegister** function when the XLL is activated.</span></span> 
    
<span data-ttu-id="a5aa1-233">第四种方法为独立方法：用于注册函数和函数代码的代码包含于同一代码项目中。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-233">The fourth approach is self-contained: the code that registers the functions and the function code are both contained in the same code project.</span></span> <span data-ttu-id="a5aa1-234">更改加载项并不涉及更改 XLM 工作表或 VBA 代码模块。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-234">Making changes to the add-in does not involve making changes to an XLM sheet or to a VBA code module.</span></span> <span data-ttu-id="a5aa1-235">若要以管理良好的方式完成此操作，同时保持 C API 的功能，则必须使用加载项管理器将 DLL 变为 XLL 并加载生成的加载项。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-235">To do this in a well-managed way while still staying within the capabilities of the C API, you must turn your DLL into an XLL and load the resulting add-in by using the Add-in Manager.</span></span> <span data-ttu-id="a5aa1-236">这使 Excel 能够在加载或激活加载项时调用 DLL 公开的函数，这样你就可以注册 XLL 包含的所有函数，并执行任何其他 DLL 初始化。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-236">This enables Excel to call a function that your DLL exposes when the add-in is loaded or activated, from which you can register all of the functions your XLL contains, and carry out any other DLL initialization.</span></span>
  
## <a name="calling-dll-commands-directly-from-excel"></a><span data-ttu-id="a5aa1-237">直接通过 Excel 调用 DLL</span><span class="sxs-lookup"><span data-stu-id="a5aa1-237">Calling DLL commands directly from Excel</span></span>

<span data-ttu-id="a5aa1-238">在没有接口（如 VBA）或没有提前注册命令的情况下，无法直接通过 Excel 对话框和菜单访问 Win32 DLL 命令。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-238">Win32 DLL commands are not accessible directly from Excel dialog boxes and menus without there being an interface, such as VBA, or without the commands being registered in advance.</span></span>
  
<span data-ttu-id="a5aa1-239">可用于访问 DLL 命令的方式如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5aa1-239">The ways in which you can access the commands of a DLL are as follows:</span></span>
  
- <span data-ttu-id="a5aa1-240">按上面所述在 VBA 中声明函数，然后通过 VBA 宏访问它。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-240">Declare the command in VBA as described previously and access it via a VBA macro.</span></span>
    
- <span data-ttu-id="a5aa1-241">使用 XLM 宏工作表上的 **CALL** 调用 DLL，然后通过 XLM 宏访问它。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-241">Call the DLL command using **CALL** on an XLM macro sheet, and access it via an XLM macro.</span></span> 
    
- <span data-ttu-id="a5aa1-242">使用 XLM 或 VBA 命令调用 XLM **REGISTER** 函数，这将会提供 Excel 识别命令（在命令被输入到期望获得宏命令名称的对话框时）所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-242">Use an XLM or VBA command to call the XLM **REGISTER** function, which provides the information Excel needs to recognize the command when it is entered into a dialog box that expects the name of a macro command.</span></span> 
    
- <span data-ttu-id="a5aa1-243">将 DLL 变为 XLL 并使用 C API **xlfRegister** 函数注册命令。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-243">Turn the DLL into an XLL and register the command using the C API **xlfRegister** function.</span></span> 
    
<span data-ttu-id="a5aa1-244">如前面的 DLL 函数上下文所述，第四种方法最独立，使注册代码与命令代码接近。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-244">As discussed earlier in the context of DLL functions, the fourth approach is the most self-contained, keeping the registration code close to the command code.</span></span> <span data-ttu-id="a5aa1-245">若要执行此操作，必须使用加载项管理器将 DLL 变为 XLL 并加载生成的加载项。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-245">To do this, you must turn your DLL into an XLL and load the resulting add-in using the Add-in Manager.</span></span> <span data-ttu-id="a5aa1-246">如果使用此方式注册命令，则还可以将命令附加到某个用户界面元素，如自定义菜单，或者设置事件陷进，以在指定击键或其他事件时调用此命令。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-246">Registering commands in this way also lets you attach the command to an element of the user interface, such as a custom menu, or to set up an event trap that calls the command on a given keystroke or other event.</span></span>
  
<span data-ttu-id="a5aa1-247">Excel 假定使用 Excel 注册的所有 XLL 命令采用以下形式。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-247">All XLL commands that are registered with Excel are assumed by Excel to be of the following form.</span></span>
  
```cpp
int WINAPI my_xll_cmd(void)
{
// Function code...
    return 1;
}
```

> [!NOTE]
> <span data-ttu-id="a5aa1-248">Excel 将忽略返回值，除非是通过 XLM 宏工作表调用该值，在此情况下，返回值将转换为 **TRUE** 或 **FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-248">Excel ignores the return value unless it is called from an XLM macro sheet, in which case the return value is converted to **TRUE** or **FALSE**.</span></span> <span data-ttu-id="a5aa1-249">因此，如果命令执行成功，则应返回 1，如果失败或者被用户取消，则返回 0。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-249">You should therefore return 1 if your command executed successfully, and 0 if it failed or was canceled by the user.</span></span> 
  
## <a name="dll-memory-and-multiple-dll-instances"></a><span data-ttu-id="a5aa1-250">DLL 内存和多个 DLL 实例</span><span class="sxs-lookup"><span data-stu-id="a5aa1-250">DLL memory and multiple DLL instances</span></span>

<span data-ttu-id="a5aa1-251">应用程序加载 DLL 时，此 DLL 的可执行代码将加载到全局堆中，以便运行该代码，并且将会在全局堆中为其数据结构分配空间。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-251">When an application loads a DLL, the DLL's executable code is loaded into the global heap so that it can be run, and space is allocated on the global heap for its data structures.</span></span> <span data-ttu-id="a5aa1-252">Windows 使用内存映射使这些内存区域看上去像位于应用程序进程中一样，这样一来应用程序就可访问它们。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-252">Windows uses memory mapping to make these areas of memory appear as if they are in the application's process so that the application can access them.</span></span>
  
<span data-ttu-id="a5aa1-253">如果另一个应用程序随后加载 DLL，则 Windows 不会生成另一个 DLL 可执行代码副本，因为该内存为只读。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-253">If a second application then loads the DLL, Windows does not make another copy of the DLL executable code, as that memory is read-only.</span></span> <span data-ttu-id="a5aa1-254">Windows 会将此 DLL 可执行代码内存映射至两个应用程序的进程。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-254">Windows maps the DLL executable code memory to the processes of both applications.</span></span> <span data-ttu-id="a5aa1-255">但是，它会为 DLL 数据结构专用副本分配另一个空间，并且只会将此副本映射至第二个进程。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-255">It does, however, allocate a second space for a private copy of the DLL's data structures and maps this copy to the second process only.</span></span> <span data-ttu-id="a5aa1-256">这可确保两个应用程序的 DLL 数据不会相互干扰。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-256">This ensures that neither application can interfere with the DLL data of the other.</span></span>
  
<span data-ttu-id="a5aa1-257">这意味着，DLL 开发人员无需在意静态和全局变量及数据结构被多个应用程序或相同应用程序的多个实例访问。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-257">This means that DLL developers do not have to be concerned about static and global variables and data structures being accessed by more than one application, or more than one instance of the same application.</span></span> <span data-ttu-id="a5aa1-258">每个应用程序的每个实例均有自己的 DLL 数据副本。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-258">Every instance of every application gets its own copy of the DLL's data.</span></span>
  
<span data-ttu-id="a5aa1-259">DLL 开发人员必须考虑应用程序的相同实例从不同线程多次调用 DLL，因为这会导致该实例的数据被争用。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-259">DLL developers do need to be concerned about the same instance of an application calling their DLL many times from different threads, because this can result in contention for that instance's data.</span></span> <span data-ttu-id="a5aa1-260">有关更多信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="a5aa1-260">For more information, see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5aa1-261">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5aa1-261">See also</span></span>

- [<span data-ttu-id="a5aa1-262">开发 DLL</span><span class="sxs-lookup"><span data-stu-id="a5aa1-262">Developing DLLs</span></span>](developing-dlls.md) 
- [<span data-ttu-id="a5aa1-263">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="a5aa1-263">Calling into Excel from the DLL or XLL</span></span>](calling-into-excel-from-the-dll-or-xll.md)

