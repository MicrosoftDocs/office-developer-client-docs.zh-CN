---
title: Excel 使用的数据类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
keywords:
- 注册数据类型 [excel 2007],Excel 数据类型,字符串 [Excel 2007],数字 [Excel 2007],数据结构 [Excel 2007],数据类型 [Excel 2007]
ms.assetid: 8740a8fb-ad67-4232-a49b-d78967a786c2
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: c546fc80b212301689744d3279a59733d9cc5524
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310904"
---
# <a name="data-types-used-by-excel"></a><span data-ttu-id="a5b16-104">Excel 使用的数据类型</span><span class="sxs-lookup"><span data-stu-id="a5b16-104">Data types used by Excel</span></span>

<span data-ttu-id="a5b16-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a5b16-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a5b16-106">Microsoft Excel 会交换多种 ANSI C/c ++ 类型，以及一些特定于 Excel 的数据结构。</span><span class="sxs-lookup"><span data-stu-id="a5b16-106">Microsoft Excel exchanges several ANSI C/C++ types and also some Excel-specific data structures.</span></span> <span data-ttu-id="a5b16-107">本文介绍了这些内容，为其他部分提供上下文。有关详细信息，请参阅 [xlfRegister（窗体 1）](xlfregister-form-1.md)主题。</span><span class="sxs-lookup"><span data-stu-id="a5b16-107">These are mentioned here to provide a context for other sections, and they are discussed in detail in the [xlfRegister (Form 1)](xlfregister-form-1.md) topic.</span></span> 
  
## <a name="ansi-cc-types"></a><span data-ttu-id="a5b16-108">ANSI C/C++ 类型</span><span class="sxs-lookup"><span data-stu-id="a5b16-108">ANSI C/C++ types</span></span>

### <a name="numbers"></a><span data-ttu-id="a5b16-109">数字</span><span class="sxs-lookup"><span data-stu-id="a5b16-109">Numbers</span></span>

<span data-ttu-id="a5b16-110">Excel 的所有版本：</span><span class="sxs-lookup"><span data-stu-id="a5b16-110">All versions of Excel:</span></span>
  
- <span data-ttu-id="a5b16-111">8 字节双精度</span><span class="sxs-lookup"><span data-stu-id="a5b16-111">8-byte double</span></span>
    
- <span data-ttu-id="a5b16-112">[signed] short [int] &ndash; 用于**布尔**值及整数</span><span class="sxs-lookup"><span data-stu-id="a5b16-112">[signed] short [int] &ndash; used for **Boolean** values and also integers</span></span> 
    
- <span data-ttu-id="a5b16-113">unsigned short [int]</span><span class="sxs-lookup"><span data-stu-id="a5b16-113">unsigned short [int]</span></span>
    
- <span data-ttu-id="a5b16-114">[signed long] int</span><span class="sxs-lookup"><span data-stu-id="a5b16-114">[signed long] int</span></span>
    
### <a name="strings"></a><span data-ttu-id="a5b16-115">字符串</span><span class="sxs-lookup"><span data-stu-id="a5b16-115">Strings</span></span>

<span data-ttu-id="a5b16-116">Excel 的所有版本：</span><span class="sxs-lookup"><span data-stu-id="a5b16-116">All versions of Excel:</span></span>
  
- <span data-ttu-id="a5b16-117">[signed] char \* &ndash; 最多包含 255 个字符的以 null 结尾的字节字符串</span><span class="sxs-lookup"><span data-stu-id="a5b16-117">[signed] char \* &ndash; null-terminated byte strings of up to 255 characters</span></span>
    
- <span data-ttu-id="a5b16-118">unsigned char \* &ndash; 最多包含 255 个字符的长度计数型字节字符串</span><span class="sxs-lookup"><span data-stu-id="a5b16-118">unsigned char \* &ndash; length-counted byte strings of up to 255 characters</span></span>
    
<span data-ttu-id="a5b16-119">自 Excel 2007 起：</span><span class="sxs-lookup"><span data-stu-id="a5b16-119">Starting in Excel 2007:</span></span>
  
- <span data-ttu-id="a5b16-120">unsigned short \* &ndash; 最多包含 32,767 个字符的 Unicode 字符串，可以是以 null 结尾的或长度计数型字符串</span><span class="sxs-lookup"><span data-stu-id="a5b16-120">unsigned short \* &ndash; Unicode strings of up to 32,767 characters, which can be null-terminated or length-counted</span></span>
    
<span data-ttu-id="a5b16-121">Excel 中的所有工作表数字均存储为双精度值，以便在与 Excel 交换整数类型时无需声明加载项函数（实际上这样产生了少量的转换开销）。</span><span class="sxs-lookup"><span data-stu-id="a5b16-121">All worksheet numbers in Excel are stored as doubles so that it is not necessary (and in fact introduces a small conversion overhead) to declare add-in functions as exchanging integer types with Excel.</span></span>
  
<span data-ttu-id="a5b16-122">使用整数类型时，Excel 会验证输入是否在该类型的限制范围内，如果超出限制，则会失败并显示 **#NUM!**</span><span class="sxs-lookup"><span data-stu-id="a5b16-122">Where you are using integer types, Excel verifies that the inputs are within the limits of the type, and they fail with **#NUM!**</span></span> <span data-ttu-id="a5b16-123">。</span><span class="sxs-lookup"><span data-stu-id="a5b16-123">if outside these.</span></span> <span data-ttu-id="a5b16-124">注册采用使用 short int 实现的 **Boolean** 参数的函数时例外。在这种情况下，任何非零输入均转换为 1，并会直接传入零。</span><span class="sxs-lookup"><span data-stu-id="a5b16-124">The exception is when you are registering a function to take a **Boolean** argument, implemented using short int. In this case, any non-zero input is converted to 1, and zero is passed straight through.</span></span> 
  
## <a name="excel-specific-data-structures"></a><span data-ttu-id="a5b16-125">特定于 Excel 的数据结构</span><span class="sxs-lookup"><span data-stu-id="a5b16-125">Excel-specific data structures</span></span>

<span data-ttu-id="a5b16-126">Excel 的所有版本：</span><span class="sxs-lookup"><span data-stu-id="a5b16-126">All versions of Excel:</span></span>
  
- <span data-ttu-id="a5b16-127">**FP** &ndash; 二维浮点数组结构，通过给定 Excel 版本支持的最大数字列数最多可支持 65,356 行。</span><span class="sxs-lookup"><span data-stu-id="a5b16-127">**FP** &ndash; a two-dimensional floating-point array structure supporting up to 65,356 rows by the maximum number columns supported in the given version of Excel.</span></span> 
    
- <span data-ttu-id="a5b16-128">**XLOPER** &ndash; 可表示所有工作表数据类型（包括错误）、整数、范围引用、XLM 宏工作表流控制类型和内部二进制存储数据类型的多类型数据结构。</span><span class="sxs-lookup"><span data-stu-id="a5b16-128">**XLOPER** &ndash; a multi-type data structure that can represent all the worksheet data types (including errors), integers, range references, XLM macro sheet flow control types, and an internal binary storage data type.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="a5b16-129">字符串表示为最多包含 255 个字符的长度计数型字节字符串。</span><span class="sxs-lookup"><span data-stu-id="a5b16-129">Strings are represented as length-counted byte strings of up to 255 characters length.</span></span> 
  
<span data-ttu-id="a5b16-130">自 Excel 2007 起：</span><span class="sxs-lookup"><span data-stu-id="a5b16-130">Starting in Excel 2007:</span></span>
  
- <span data-ttu-id="a5b16-131">**FP12** &ndash; 自 Excel 2007 起支持所有行和列的二维浮点数组结构。</span><span class="sxs-lookup"><span data-stu-id="a5b16-131">**FP12** &ndash; a two-dimensional floating-point array structure supporting all the rows and columns starting in Excel 2007.</span></span> 
    
- <span data-ttu-id="a5b16-132">**XLOPER12** &ndash; 可表示所有工作表数据类型（包括错误）、整数、范围引用、XLM 宏工作表流控制类型和内部二进制存储数据类型的多类型数据结构。</span><span class="sxs-lookup"><span data-stu-id="a5b16-132">**XLOPER12** &ndash; a multi-type data structure that can represent all the worksheet data types (including errors), integers, range references, XLM macro sheet flow control types, and an internal binary storage data type.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="a5b16-133">字符串表示为最多包含 32,767 个字符的长度计数型 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="a5b16-133">Strings are represented as length-counted Unicode strings of up to 32,767 characters long.</span></span> 
  
## <a name="registration-data-type-codes"></a><span data-ttu-id="a5b16-134">注册数据类型代码</span><span class="sxs-lookup"><span data-stu-id="a5b16-134">Registration data type codes</span></span>

<span data-ttu-id="a5b16-135">XLL 函数使用 C API 函数 **xlfRegister** 注册，该函数会将为返回类型和参数类型编码的字母字符串用作其第三个参数。</span><span class="sxs-lookup"><span data-stu-id="a5b16-135">XLL functions are registered using the C API function **xlfRegister**, which takes as its third argument a string of letters that encode the return and argument types.</span></span> <span data-ttu-id="a5b16-136">此字符串还包含用于告知 Excel 此函数是否具有以下特征的信息：可变、线程安全（自 Excel 2007 起）、等效于宏工作表、是否通过就地修改参数返回结果。</span><span class="sxs-lookup"><span data-stu-id="a5b16-136">This string also contains the information that tells Excel whether the function is volatile, is thread-safe (starting in Excel 2007), is macro sheet equivalent, and whether it returns its result by modifying an argument in place.</span></span>
  
<span data-ttu-id="a5b16-137">[xlfRegister（窗体 1）](xlfregister-form-1.md)主题复制了下表，并进行了详细介绍。</span><span class="sxs-lookup"><span data-stu-id="a5b16-137">The following table is reproduced and discussed in more detail in the [xlfRegister (Form 1)](xlfregister-form-1.md) topic.</span></span> <span data-ttu-id="a5b16-138">此处复制该表的目的在于为其他部分提供上下文。</span><span class="sxs-lookup"><span data-stu-id="a5b16-138">It is reproduced here in order to provide a context for the rest of this section.</span></span> <span data-ttu-id="a5b16-139">例如，可以将采用长度计数型 Unicode 字符串（自 Excel 2007 起）的函数描述为采用 C% 类型的参数。</span><span class="sxs-lookup"><span data-stu-id="a5b16-139">For example, a function that takes a length-counted Unicode string (starting in Excel 2007) could be described as taking a type C% argument.</span></span> 
  
|<span data-ttu-id="a5b16-140">数据类型</span><span class="sxs-lookup"><span data-stu-id="a5b16-140">Data type</span></span>|<span data-ttu-id="a5b16-141">按值传递</span><span class="sxs-lookup"><span data-stu-id="a5b16-141">Pass by value</span></span>|<span data-ttu-id="a5b16-142">按引用传递（指针）</span><span class="sxs-lookup"><span data-stu-id="a5b16-142">Pass by ref (pointer)</span></span>|<span data-ttu-id="a5b16-143">注释</span><span class="sxs-lookup"><span data-stu-id="a5b16-143">Comments</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5b16-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="a5b16-144">Boolean</span></span>  <br/> |<span data-ttu-id="a5b16-145">A</span><span class="sxs-lookup"><span data-stu-id="a5b16-145">A</span></span>  <br/> |<span data-ttu-id="a5b16-146">L</span><span class="sxs-lookup"><span data-stu-id="a5b16-146">L</span></span>  <br/> |<span data-ttu-id="a5b16-147">short（0=false 或 1=true）</span><span class="sxs-lookup"><span data-stu-id="a5b16-147">short (0=false or 1=true)</span></span>  <br/> |
|<span data-ttu-id="a5b16-148">double</span><span class="sxs-lookup"><span data-stu-id="a5b16-148">double</span></span>  <br/> |<span data-ttu-id="a5b16-149">B</span><span class="sxs-lookup"><span data-stu-id="a5b16-149">B</span></span>  <br/> |<span data-ttu-id="a5b16-150">E</span><span class="sxs-lookup"><span data-stu-id="a5b16-150">E</span></span>  <br/> ||
|<span data-ttu-id="a5b16-151">char \*</span><span class="sxs-lookup"><span data-stu-id="a5b16-151">char \*</span></span>  <br/> ||<span data-ttu-id="a5b16-152">C、F</span><span class="sxs-lookup"><span data-stu-id="a5b16-152">C, F</span></span>  <br/> |<span data-ttu-id="a5b16-153">以 null 结尾的 ASCII 字节字符串</span><span class="sxs-lookup"><span data-stu-id="a5b16-153">Null-terminated ASCII byte string</span></span>  <br/> |
|<span data-ttu-id="a5b16-154">unsigned char \*</span><span class="sxs-lookup"><span data-stu-id="a5b16-154">unsigned char \*</span></span>  <br/> ||<span data-ttu-id="a5b16-155">D、G</span><span class="sxs-lookup"><span data-stu-id="a5b16-155">D, G</span></span>  <br/> |<span data-ttu-id="a5b16-156">长度计数型 ASCII 字节字符串</span><span class="sxs-lookup"><span data-stu-id="a5b16-156">Length -counted ASCII byte string</span></span>  <br/> |
|<span data-ttu-id="a5b16-157">unsigned short \*（自 Excel 2007 起）</span><span class="sxs-lookup"><span data-stu-id="a5b16-157">unsigned short \*  (starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="a5b16-158">C%、F%</span><span class="sxs-lookup"><span data-stu-id="a5b16-158">C%, F%</span></span>  <br/> |<span data-ttu-id="a5b16-159">以 null 结尾的 Unicode 宽字符字符串</span><span class="sxs-lookup"><span data-stu-id="a5b16-159">Null-terminated Unicode wide character string</span></span>  <br/> |
|<span data-ttu-id="a5b16-160">unsigned short \*（自 Excel 2007 起）</span><span class="sxs-lookup"><span data-stu-id="a5b16-160">unsigned short \*  (starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="a5b16-161">D%、G%</span><span class="sxs-lookup"><span data-stu-id="a5b16-161">D%, G%</span></span>  <br/> |<span data-ttu-id="a5b16-162">长度计数型 Unicode 宽字符字符串</span><span class="sxs-lookup"><span data-stu-id="a5b16-162">Length-counted Unicode wide character string</span></span>  <br/> |
|<span data-ttu-id="a5b16-163">unsigned short [int]</span><span class="sxs-lookup"><span data-stu-id="a5b16-163">unsigned short [int]</span></span>  <br/> |<span data-ttu-id="a5b16-164">H</span><span class="sxs-lookup"><span data-stu-id="a5b16-164">H</span></span>  <br/> ||<span data-ttu-id="a5b16-165">WORD</span><span class="sxs-lookup"><span data-stu-id="a5b16-165">WORD</span></span>  <br/> |
|<span data-ttu-id="a5b16-166">[signed] short [int]</span><span class="sxs-lookup"><span data-stu-id="a5b16-166">[signed] short [int]</span></span>  <br/> |<span data-ttu-id="a5b16-167">I</span><span class="sxs-lookup"><span data-stu-id="a5b16-167">I</span></span>  <br/> |<span data-ttu-id="a5b16-168">M</span><span class="sxs-lookup"><span data-stu-id="a5b16-168">M</span></span>  <br/> |<span data-ttu-id="a5b16-169">16 位</span><span class="sxs-lookup"><span data-stu-id="a5b16-169">16-bit</span></span>  <br/> |
|<span data-ttu-id="a5b16-170">[signed long] int</span><span class="sxs-lookup"><span data-stu-id="a5b16-170">[signed long] int</span></span>  <br/> |<span data-ttu-id="a5b16-171">J</span><span class="sxs-lookup"><span data-stu-id="a5b16-171">J</span></span>  <br/> |<span data-ttu-id="a5b16-172">N</span><span class="sxs-lookup"><span data-stu-id="a5b16-172">N</span></span>  <br/> |<span data-ttu-id="a5b16-173">32 位</span><span class="sxs-lookup"><span data-stu-id="a5b16-173">32-bit</span></span>  <br/> |
|<span data-ttu-id="a5b16-174">Array</span><span class="sxs-lookup"><span data-stu-id="a5b16-174">Array</span></span>  <br/> ||<span data-ttu-id="a5b16-175">O</span><span class="sxs-lookup"><span data-stu-id="a5b16-175">O</span></span>  <br/> | <span data-ttu-id="a5b16-176">按引用传递为三个参数：</span><span class="sxs-lookup"><span data-stu-id="a5b16-176">Passed as three arguments by reference:</span></span>  <br/><span data-ttu-id="a5b16-177">1. short int \*行</span><span class="sxs-lookup"><span data-stu-id="a5b16-177">1. short int \*rows</span></span>  <br/><span data-ttu-id="a5b16-178">2. short int \*列</span><span class="sxs-lookup"><span data-stu-id="a5b16-178">2. short int \*columns</span></span>  <br/><span data-ttu-id="a5b16-179">3. double \*数组</span><span class="sxs-lookup"><span data-stu-id="a5b16-179">3. double \*array</span></span>  <br/> |
|<span data-ttu-id="a5b16-180">Array</span><span class="sxs-lookup"><span data-stu-id="a5b16-180">Array</span></span>  <br/> <span data-ttu-id="a5b16-181">（自 Excel 2007 起）</span><span class="sxs-lookup"><span data-stu-id="a5b16-181">(starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="a5b16-182">O%</span><span class="sxs-lookup"><span data-stu-id="a5b16-182">O%</span></span>  <br/> | <span data-ttu-id="a5b16-183">按引用传递为三个参数：</span><span class="sxs-lookup"><span data-stu-id="a5b16-183">Passed as three arguments by reference:</span></span>  <br/><span data-ttu-id="a5b16-184">1. int \*行</span><span class="sxs-lookup"><span data-stu-id="a5b16-184">1. int \*rows</span></span>  <br/><span data-ttu-id="a5b16-185">2. int \*列</span><span class="sxs-lookup"><span data-stu-id="a5b16-185">2. int \*columns</span></span>  <br/><span data-ttu-id="a5b16-186">3. double \*数组</span><span class="sxs-lookup"><span data-stu-id="a5b16-186">3. double \*array</span></span>  <br/> |
|<span data-ttu-id="a5b16-187">FP</span><span class="sxs-lookup"><span data-stu-id="a5b16-187">FP</span></span>  <br/> ||<span data-ttu-id="a5b16-188">K</span><span class="sxs-lookup"><span data-stu-id="a5b16-188">K</span></span>  <br/> |<span data-ttu-id="a5b16-189">浮点数组结构</span><span class="sxs-lookup"><span data-stu-id="a5b16-189">Floating-point array structure</span></span>  <br/> |
|<span data-ttu-id="a5b16-190">FP12</span><span class="sxs-lookup"><span data-stu-id="a5b16-190">FP12</span></span>  <br/> <span data-ttu-id="a5b16-191">（自 Excel 2007 起）</span><span class="sxs-lookup"><span data-stu-id="a5b16-191">(starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="a5b16-192">K%</span><span class="sxs-lookup"><span data-stu-id="a5b16-192">K%</span></span>  <br/> |<span data-ttu-id="a5b16-193">大型网格浮点数组结构</span><span class="sxs-lookup"><span data-stu-id="a5b16-193">Large grid floating-point array structure</span></span>  <br/> |
|<span data-ttu-id="a5b16-194">XLOPER</span><span class="sxs-lookup"><span data-stu-id="a5b16-194">XLOPER</span></span>  <br/> ||<span data-ttu-id="a5b16-195">P</span><span class="sxs-lookup"><span data-stu-id="a5b16-195">P</span></span>  <br/> |<span data-ttu-id="a5b16-196">变量类型工作表值和数组</span><span class="sxs-lookup"><span data-stu-id="a5b16-196">Variable-type worksheet values and arrays</span></span>  <br/> |
|||<span data-ttu-id="a5b16-197">R</span><span class="sxs-lookup"><span data-stu-id="a5b16-197">R</span></span>  <br/> |<span data-ttu-id="a5b16-198">值、数组和范围引用</span><span class="sxs-lookup"><span data-stu-id="a5b16-198">Values, arrays, and range references</span></span>  <br/> |
|<span data-ttu-id="a5b16-199">XLOPER12</span><span class="sxs-lookup"><span data-stu-id="a5b16-199">XLOPER12</span></span>  <br/> <span data-ttu-id="a5b16-200">（自 Excel 2007 起）</span><span class="sxs-lookup"><span data-stu-id="a5b16-200">(starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="a5b16-201">Q</span><span class="sxs-lookup"><span data-stu-id="a5b16-201">Q</span></span>  <br/> |<span data-ttu-id="a5b16-202">变量类型工作表值和数组</span><span class="sxs-lookup"><span data-stu-id="a5b16-202">Variable-type worksheet values and arrays</span></span>  <br/> |
|||<span data-ttu-id="a5b16-203">U</span><span class="sxs-lookup"><span data-stu-id="a5b16-203">U</span></span>  <br/> |<span data-ttu-id="a5b16-204">值、数组和范围引用</span><span class="sxs-lookup"><span data-stu-id="a5b16-204">Values, arrays, and range references</span></span>  <br/> |
   
<span data-ttu-id="a5b16-205">下列类型均是 Microsoft Office Excel 2007 新增的类型，较旧版本中不支持这些类型：**C%**、**F%**、**D%**、**G%**、**K%**、**O%**、**Q** 和 **U**。</span><span class="sxs-lookup"><span data-stu-id="a5b16-205">The types **C%**, **F%**, **D%**, **G%**, **K%**, **O%**, **Q**, and **U** were all new in Microsoft Office Excel 2007 and are not supported in earlier versions.</span></span> <span data-ttu-id="a5b16-206">下列字符串类型用于就地修改的参数：**F**、**F%**、**G** 和 **G%**。</span><span class="sxs-lookup"><span data-stu-id="a5b16-206">The string types **F**, **F%**, **G**, and **G%** are used for arguments that are modified-in-place.</span></span> <span data-ttu-id="a5b16-207">如果 **XLOPER** 或 **XLOPER12** 参数分别注册为 **P** 或 **Q** 类型，当 Excel 准备这些类型时，会将单个单元格引用转换为简单值，并将多单元格引用转换为数组。</span><span class="sxs-lookup"><span data-stu-id="a5b16-207">When **XLOPER** or **XLOPER12** arguments are registered as types **P** or **Q** respectively, Excel converts single-cell references to simple values and multi-cell references to arrays when it prepares them.</span></span> 
  
<span data-ttu-id="a5b16-208">**P** 和 **Q** 类型始终作为下列类型之一引入函数：**xltypeNum**、**xltypeStr**、**xltypeBool**、**xltypeErr**、**xltypeMulti**、**xltypeMissing** 或 **xltypeNil**，但不会作为 **xltypeRef** 或 **xltypeSRef** 引入，因为始终会取消引用这些类型。</span><span class="sxs-lookup"><span data-stu-id="a5b16-208">**P** and **Q** types always arrive in your function as one of the following types: **xltypeNum**, **xltypeStr**, **xltypeBool**, **xltypeErr**, **xltypeMulti**, **xltypeMissing**, or **xltypeNil**, but not **xltypeRef** or **xltypeSRef** because these are always dereferenced.</span></span> 
  
<span data-ttu-id="a5b16-209">类型 **O** 实际上是堆栈上的三个参数，是为了与 Fortran DLL 兼容而引入的，其中参数通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="a5b16-209">Type **O**, which is really three arguments on the stack, was introduced for compatibility with Fortran DLLs where arguments are passed by reference.</span></span> <span data-ttu-id="a5b16-210">该类型不能用于返回值，除非将参数声明为就地修改返回值，并将结果置于引用值中。</span><span class="sxs-lookup"><span data-stu-id="a5b16-210">It cannot be used to return a value except by declaring the argument as a modify-in-place return value and placing the results in the referenced values.</span></span> <span data-ttu-id="a5b16-211">**O%** 类型在 Excel 2007 中扩展 **O** 类型，使它可以访问范围大于 Office Excel 2003 网格的数组。</span><span class="sxs-lookup"><span data-stu-id="a5b16-211">Type **O%** extends type **O** in Excel 2007 so that it can access arrays that cover areas larger than the Office Excel 2003 grid.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a5b16-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5b16-212">See also</span></span>

- [<span data-ttu-id="a5b16-213">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="a5b16-213">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="a5b16-214">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="a5b16-214">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
- [<span data-ttu-id="a5b16-215">Excel XLL SDK API 函数引用</span><span class="sxs-lookup"><span data-stu-id="a5b16-215">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)

