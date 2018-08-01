---
title: 使用 Excel 数据类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
keywords:
- 注册数据类型 [excel 2007]，Excel 数据类型、 [Excel 2007] 的字符串、 数字 [Excel 2007]、 数据结构 [Excel 2007]，数据类型 [Excel 2007]
localization_priority: Normal
ms.assetid: 8740a8fb-ad67-4232-a49b-d78967a786c2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: b32a9beb2f77c12e6b6f2c445672c717a2546386
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773648"
---
# <a name="data-types-used-by-excel"></a><span data-ttu-id="22a39-104">使用 Excel 数据类型</span><span class="sxs-lookup"><span data-stu-id="22a39-104">Data types used by Excel</span></span>

<span data-ttu-id="22a39-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="22a39-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="22a39-106">Microsoft Excel 交换几种 ANSI C/c + + 类型和还某些特定于 Excel 的数据结构。</span><span class="sxs-lookup"><span data-stu-id="22a39-106">Microsoft Excel exchanges several ANSI C/C++ types and also some Excel-specific data structures.</span></span> <span data-ttu-id="22a39-107">这些此处提及的其他部分中，提供上下文和[xlfRegister (窗体 1)](xlfregister-form-1.md)主题中详细讨论了它们。</span><span class="sxs-lookup"><span data-stu-id="22a39-107">These are mentioned here to provide a context for other sections, and they are discussed in detail in the [xlfRegister (Form 1)](xlfregister-form-1.md) topic.</span></span> 
  
## <a name="ansi-cc-types"></a><span data-ttu-id="22a39-108">ANSI C/c + + 类型</span><span class="sxs-lookup"><span data-stu-id="22a39-108">ANSI C/C++ types</span></span>

### <a name="numbers"></a><span data-ttu-id="22a39-109">����</span><span class="sxs-lookup"><span data-stu-id="22a39-109">Numbers</span></span>

<span data-ttu-id="22a39-110">所有版本的 Excel 中：</span><span class="sxs-lookup"><span data-stu-id="22a39-110">All versions of Excel:</span></span>
  
- <span data-ttu-id="22a39-111">8 字节双精度值</span><span class="sxs-lookup"><span data-stu-id="22a39-111">8-byte double</span></span>
    
- <span data-ttu-id="22a39-112">[签名] short [int]&ndash;用于**布尔**值和还整数</span><span class="sxs-lookup"><span data-stu-id="22a39-112">[signed] short [int] &ndash; used for **Boolean** values and also integers</span></span> 
    
- <span data-ttu-id="22a39-113">无符号的 short [int]</span><span class="sxs-lookup"><span data-stu-id="22a39-113">unsigned short [int]</span></span>
    
- <span data-ttu-id="22a39-114">[签名长] int</span><span class="sxs-lookup"><span data-stu-id="22a39-114">[signed long] int</span></span>
    
### <a name="strings"></a><span data-ttu-id="22a39-115">字符串</span><span class="sxs-lookup"><span data-stu-id="22a39-115">Strings</span></span>

<span data-ttu-id="22a39-116">所有版本的 Excel 中：</span><span class="sxs-lookup"><span data-stu-id="22a39-116">All versions of Excel:</span></span>
  
- <span data-ttu-id="22a39-117">[签名] char \* &ndash; null 结尾的字节的最多 255 个字符的字符串</span><span class="sxs-lookup"><span data-stu-id="22a39-117">[signed] char \* &ndash; null-terminated byte strings of up to 255 characters</span></span>
    
- <span data-ttu-id="22a39-118">未签署的 char \* &ndash;最多 255 个字符的长度计数字节字符串</span><span class="sxs-lookup"><span data-stu-id="22a39-118">unsigned char \* &ndash; length-counted byte strings of up to 255 characters</span></span>
    
<span data-ttu-id="22a39-119">启动 Excel 2007 中：</span><span class="sxs-lookup"><span data-stu-id="22a39-119">Starting in Excel 2007:</span></span>
  
- <span data-ttu-id="22a39-120">未签署的短\*&ndash;达 32,767 个字符，可以是 null 结尾或长度计数的 Unicode 字符串</span><span class="sxs-lookup"><span data-stu-id="22a39-120">unsigned short \* &ndash; Unicode strings of up to 32,767 characters, which can be null-terminated or length-counted</span></span>
    
<span data-ttu-id="22a39-121">在 Excel 中的所有工作表号码存储为双精度型值，以使它不需要 （和实际上引入了小型转换开销） 声明作为交换整数类型，通过 Excel 外接程序函数。</span><span class="sxs-lookup"><span data-stu-id="22a39-121">All worksheet numbers in Excel are stored as doubles so that it is not necessary (and in fact introduces a small conversion overhead) to declare add-in functions as exchanging integer types with Excel.</span></span>
  
<span data-ttu-id="22a39-122">如果您使用的整数类型，Excel 验证的输入中的类型，限制是，且它们失败并出现 **#NUM ！**</span><span class="sxs-lookup"><span data-stu-id="22a39-122">Where you are using integer types, Excel verifies that the inputs are within the limits of the type, and they fail with **#NUM!**</span></span> <span data-ttu-id="22a39-123">如果这些外部。</span><span class="sxs-lookup"><span data-stu-id="22a39-123">if outside these.</span></span> <span data-ttu-id="22a39-124">您要注册才能使用短 int。 实现一个**布尔**参数的函数时除外在这种情况下，任何非零输入将转换为 1，并直接通过传递零。</span><span class="sxs-lookup"><span data-stu-id="22a39-124">The exception is when you are registering a function to take a **Boolean** argument, implemented using short int. In this case, any non-zero input is converted to 1, and zero is passed straight through.</span></span> 
  
## <a name="excel-specific-data-structures"></a><span data-ttu-id="22a39-125">特定于 Excel 的数据结构</span><span class="sxs-lookup"><span data-stu-id="22a39-125">Excel-specific data structures</span></span>

<span data-ttu-id="22a39-126">所有版本的 Excel 中：</span><span class="sxs-lookup"><span data-stu-id="22a39-126">All versions of Excel:</span></span>
  
- <span data-ttu-id="22a39-127">**FP**&ndash;由在给定的 Excel 版本中受支持的最大数字列支持多达包含 65356 行的二维浮点数组结构。</span><span class="sxs-lookup"><span data-stu-id="22a39-127">**FP** &ndash; a two-dimensional floating-point array structure supporting up to 65,356 rows by the maximum number columns supported in the given version of Excel.</span></span> 
    
- <span data-ttu-id="22a39-128">**XLOPER**&ndash; （包括错误） 的所有工作表数据类型、 整数、 区域引用、 XLM 宏工作表流控件类型和内部二进制存储数据类型可以表示多类型数据结构。</span><span class="sxs-lookup"><span data-stu-id="22a39-128">**XLOPER** &ndash; a multi-type data structure that can represent all the worksheet data types (including errors), integers, range references, XLM macro sheet flow control types, and an internal binary storage data type.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="22a39-129">字符串长度计数字节的最多 255 个字符长度的字符串表示。</span><span class="sxs-lookup"><span data-stu-id="22a39-129">Strings are represented as length-counted byte strings of up to 255 characters length.</span></span> 
  
<span data-ttu-id="22a39-130">启动 Excel 2007 中：</span><span class="sxs-lookup"><span data-stu-id="22a39-130">Starting in Excel 2007:</span></span>
  
- <span data-ttu-id="22a39-131">**FP12**&ndash;支持所有的行和列开始在 Excel 2007 中的二维浮点数组结构。</span><span class="sxs-lookup"><span data-stu-id="22a39-131">**FP12** &ndash; a two-dimensional floating-point array structure supporting all the rows and columns starting in Excel 2007.</span></span> 
    
- <span data-ttu-id="22a39-132">**XLOPER12**&ndash; （包括错误） 的所有工作表数据类型、 整数、 区域引用、 XLM 宏工作表流控件类型和内部二进制存储数据类型可以表示多类型数据结构。</span><span class="sxs-lookup"><span data-stu-id="22a39-132">**XLOPER12** &ndash; a multi-type data structure that can represent all the worksheet data types (including errors), integers, range references, XLM macro sheet flow control types, and an internal binary storage data type.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="22a39-133">字符串表示作为计算长度在内的长达 32,767 个字符的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="22a39-133">Strings are represented as length-counted Unicode strings of up to 32,767 characters long.</span></span> 
  
## <a name="registration-data-type-codes"></a><span data-ttu-id="22a39-134">注册数据类型代码</span><span class="sxs-lookup"><span data-stu-id="22a39-134">Registration data type codes</span></span>

<span data-ttu-id="22a39-135">使用 C API 函数**xlfRegister**，它采用作为其第三个参数返回和参数的类型编码的字母字符串注册 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="22a39-135">XLL functions are registered using the C API function **xlfRegister**, which takes as its third argument a string of letters that encode the return and argument types.</span></span> <span data-ttu-id="22a39-136">此字符串还包含告诉 Excel 可变函数是否是线程安全 （在 Excel 2007 中从开始）、 是等效的宏工作表的信息并是否返回其结果通过修改就地参数。</span><span class="sxs-lookup"><span data-stu-id="22a39-136">This string also contains the information that tells Excel whether the function is volatile, is thread-safe (starting in Excel 2007), is macro sheet equivalent, and whether it returns its result by modifying an argument in place.</span></span>
  
<span data-ttu-id="22a39-137">下表是复制并[xlfRegister (窗体 1)](xlfregister-form-1.md)主题中的更详细地讨论。</span><span class="sxs-lookup"><span data-stu-id="22a39-137">The following table is reproduced and discussed in more detail in the [xlfRegister (Form 1)](xlfregister-form-1.md) topic.</span></span> <span data-ttu-id="22a39-138">被复制此处以便为本节的其余部分提供上下文。</span><span class="sxs-lookup"><span data-stu-id="22a39-138">It is reproduced here in order to provide a context for the rest of this section.</span></span> <span data-ttu-id="22a39-139">例如，采用的长度计数的 Unicode 字符串 （在 Excel 2007 中从开始） 函数无法描述为采用 C %参数的类型。</span><span class="sxs-lookup"><span data-stu-id="22a39-139">For example, a function that takes a length-counted Unicode string (starting in Excel 2007) could be described as taking a type C% argument.</span></span> 
  
|<span data-ttu-id="22a39-140">数据类型</span><span class="sxs-lookup"><span data-stu-id="22a39-140">Data type</span></span>|<span data-ttu-id="22a39-141">按值传递</span><span class="sxs-lookup"><span data-stu-id="22a39-141">Pass by value</span></span>|<span data-ttu-id="22a39-142">Ref （指针） 通过传递</span><span class="sxs-lookup"><span data-stu-id="22a39-142">Pass by ref (pointer)</span></span>|<span data-ttu-id="22a39-143">注释</span><span class="sxs-lookup"><span data-stu-id="22a39-143">Comments</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22a39-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="22a39-144">Boolean</span></span>  <br/> |<span data-ttu-id="22a39-145">A</span><span class="sxs-lookup"><span data-stu-id="22a39-145">A</span></span>  <br/> |<span data-ttu-id="22a39-146">L</span><span class="sxs-lookup"><span data-stu-id="22a39-146">L</span></span>  <br/> |<span data-ttu-id="22a39-147">短 (0 = false 或 1 = true)</span><span class="sxs-lookup"><span data-stu-id="22a39-147">short (0=false or 1=true)</span></span>  <br/> |
|<span data-ttu-id="22a39-148">double</span><span class="sxs-lookup"><span data-stu-id="22a39-148">double</span></span>  <br/> |<span data-ttu-id="22a39-149">B</span><span class="sxs-lookup"><span data-stu-id="22a39-149">B</span></span>  <br/> |<span data-ttu-id="22a39-150">E</span><span class="sxs-lookup"><span data-stu-id="22a39-150">E</span></span>  <br/> ||
|<span data-ttu-id="22a39-151">char\*</span><span class="sxs-lookup"><span data-stu-id="22a39-151">char \*</span></span>  <br/> ||<span data-ttu-id="22a39-152">C F</span><span class="sxs-lookup"><span data-stu-id="22a39-152">C, F</span></span>  <br/> |<span data-ttu-id="22a39-153">Null 结尾的 ASCII 字节字符串</span><span class="sxs-lookup"><span data-stu-id="22a39-153">Null-terminated ASCII byte string</span></span>  <br/> |
|<span data-ttu-id="22a39-154">无符号的字符\*</span><span class="sxs-lookup"><span data-stu-id="22a39-154">unsigned char \*</span></span>  <br/> ||<span data-ttu-id="22a39-155">D、 G</span><span class="sxs-lookup"><span data-stu-id="22a39-155">D, G</span></span>  <br/> |<span data-ttu-id="22a39-156">长度-计数 ASCII 字节字符串</span><span class="sxs-lookup"><span data-stu-id="22a39-156">Length -counted ASCII byte string</span></span>  <br/> |
|<span data-ttu-id="22a39-157">未签署的短\*（在 Excel 2007 中从开始）</span><span class="sxs-lookup"><span data-stu-id="22a39-157">unsigned short \*  (starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="22a39-158">C %，F %</span><span class="sxs-lookup"><span data-stu-id="22a39-158">C%, F%</span></span>  <br/> |<span data-ttu-id="22a39-159">Null 结尾的 Unicode 宽字符字符串</span><span class="sxs-lookup"><span data-stu-id="22a39-159">Null-terminated Unicode wide character string</span></span>  <br/> |
|<span data-ttu-id="22a39-160">未签署的短\*（在 Excel 2007 中从开始）</span><span class="sxs-lookup"><span data-stu-id="22a39-160">unsigned short \*  (starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="22a39-161">D %，G %</span><span class="sxs-lookup"><span data-stu-id="22a39-161">D%, G%</span></span>  <br/> |<span data-ttu-id="22a39-162">长度计数 Unicode 宽字符字符串</span><span class="sxs-lookup"><span data-stu-id="22a39-162">Length-counted Unicode wide character string</span></span>  <br/> |
|<span data-ttu-id="22a39-163">无符号的 short [int]</span><span class="sxs-lookup"><span data-stu-id="22a39-163">unsigned short [int]</span></span>  <br/> |<span data-ttu-id="22a39-164">H</span><span class="sxs-lookup"><span data-stu-id="22a39-164">H</span></span>  <br/> ||<span data-ttu-id="22a39-165">WORD</span><span class="sxs-lookup"><span data-stu-id="22a39-165">WORD</span></span>  <br/> |
|<span data-ttu-id="22a39-166">[签名] short [int]</span><span class="sxs-lookup"><span data-stu-id="22a39-166">[signed] short [int]</span></span>  <br/> |<span data-ttu-id="22a39-167">I</span><span class="sxs-lookup"><span data-stu-id="22a39-167">I</span></span>  <br/> |<span data-ttu-id="22a39-168">M</span><span class="sxs-lookup"><span data-stu-id="22a39-168">M</span></span>  <br/> |<span data-ttu-id="22a39-169">16 位</span><span class="sxs-lookup"><span data-stu-id="22a39-169">16-bit</span></span>  <br/> |
|<span data-ttu-id="22a39-170">[签名长] int</span><span class="sxs-lookup"><span data-stu-id="22a39-170">[signed long] int</span></span>  <br/> |<span data-ttu-id="22a39-171">J</span><span class="sxs-lookup"><span data-stu-id="22a39-171">J</span></span>  <br/> |<span data-ttu-id="22a39-172">N</span><span class="sxs-lookup"><span data-stu-id="22a39-172">N</span></span>  <br/> |<span data-ttu-id="22a39-173">32 位</span><span class="sxs-lookup"><span data-stu-id="22a39-173">32-bit</span></span>  <br/> |
|<span data-ttu-id="22a39-174">数组</span><span class="sxs-lookup"><span data-stu-id="22a39-174">Array</span></span>  <br/> ||<span data-ttu-id="22a39-175">O</span><span class="sxs-lookup"><span data-stu-id="22a39-175">O</span></span>  <br/> | <span data-ttu-id="22a39-176">通过引用作为三个参数传递：</span><span class="sxs-lookup"><span data-stu-id="22a39-176">Passed as three arguments by reference:</span></span>  <br/><span data-ttu-id="22a39-177">1.短 int\*行</span><span class="sxs-lookup"><span data-stu-id="22a39-177">1. short int \*rows</span></span>  <br/><span data-ttu-id="22a39-178">2.短 int\*列</span><span class="sxs-lookup"><span data-stu-id="22a39-178">2. short int \*columns</span></span>  <br/><span data-ttu-id="22a39-179">3.double\*数组</span><span class="sxs-lookup"><span data-stu-id="22a39-179">3. double \*array</span></span>  <br/> |
|<span data-ttu-id="22a39-180">数组</span><span class="sxs-lookup"><span data-stu-id="22a39-180">Array</span></span>  <br/> <span data-ttu-id="22a39-181">（在 Excel 2007 中从开始）</span><span class="sxs-lookup"><span data-stu-id="22a39-181">(starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="22a39-182">O %</span><span class="sxs-lookup"><span data-stu-id="22a39-182">O%</span></span>  <br/> | <span data-ttu-id="22a39-183">通过引用作为三个参数传递：</span><span class="sxs-lookup"><span data-stu-id="22a39-183">Passed as three arguments by reference:</span></span>  <br/><span data-ttu-id="22a39-184">1.int\*行</span><span class="sxs-lookup"><span data-stu-id="22a39-184">1. int \*rows</span></span>  <br/><span data-ttu-id="22a39-185">2.int\*列</span><span class="sxs-lookup"><span data-stu-id="22a39-185">2. int \*columns</span></span>  <br/><span data-ttu-id="22a39-186">3.double\*数组</span><span class="sxs-lookup"><span data-stu-id="22a39-186">3. double \*array</span></span>  <br/> |
|<span data-ttu-id="22a39-187">FP</span><span class="sxs-lookup"><span data-stu-id="22a39-187">FP</span></span>  <br/> ||<span data-ttu-id="22a39-188">K</span><span class="sxs-lookup"><span data-stu-id="22a39-188">K</span></span>  <br/> |<span data-ttu-id="22a39-189">浮点数组结构</span><span class="sxs-lookup"><span data-stu-id="22a39-189">Floating-point array structure</span></span>  <br/> |
|<span data-ttu-id="22a39-190">FP12</span><span class="sxs-lookup"><span data-stu-id="22a39-190">FP12</span></span>  <br/> <span data-ttu-id="22a39-191">（在 Excel 2007 中从开始）</span><span class="sxs-lookup"><span data-stu-id="22a39-191">(starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="22a39-192">K %</span><span class="sxs-lookup"><span data-stu-id="22a39-192">K%</span></span>  <br/> |<span data-ttu-id="22a39-193">大网格浮点数组结构</span><span class="sxs-lookup"><span data-stu-id="22a39-193">Large grid floating-point array structure</span></span>  <br/> |
|<span data-ttu-id="22a39-194">XLOPER</span><span class="sxs-lookup"><span data-stu-id="22a39-194">XLOPER</span></span>  <br/> ||<span data-ttu-id="22a39-195">P</span><span class="sxs-lookup"><span data-stu-id="22a39-195">P</span></span>  <br/> |<span data-ttu-id="22a39-196">变量类型工作表值和阵列</span><span class="sxs-lookup"><span data-stu-id="22a39-196">Variable-type worksheet values and arrays</span></span>  <br/> |
|||<span data-ttu-id="22a39-197">R</span><span class="sxs-lookup"><span data-stu-id="22a39-197">R</span></span>  <br/> |<span data-ttu-id="22a39-198">值、 数组和区域引用</span><span class="sxs-lookup"><span data-stu-id="22a39-198">Values, arrays, and range references</span></span>  <br/> |
|<span data-ttu-id="22a39-199">XLOPER12</span><span class="sxs-lookup"><span data-stu-id="22a39-199">XLOPER12</span></span>  <br/> <span data-ttu-id="22a39-200">（在 Excel 2007 中从开始）</span><span class="sxs-lookup"><span data-stu-id="22a39-200">(starting in Excel 2007)</span></span>  <br/> ||<span data-ttu-id="22a39-201">Q</span><span class="sxs-lookup"><span data-stu-id="22a39-201">Q</span></span>  <br/> |<span data-ttu-id="22a39-202">变量类型工作表值和阵列</span><span class="sxs-lookup"><span data-stu-id="22a39-202">Variable-type worksheet values and arrays</span></span>  <br/> |
|||<span data-ttu-id="22a39-203">U</span><span class="sxs-lookup"><span data-stu-id="22a39-203">U</span></span>  <br/> |<span data-ttu-id="22a39-204">值、 数组和区域引用</span><span class="sxs-lookup"><span data-stu-id="22a39-204">Values, arrays, and range references</span></span>  <br/> |
   
<span data-ttu-id="22a39-205">类型**C %**、 **F %**、 **D %**、 **G %**、 **K %**、 **O %**、 **Q**、 和**U**了 Microsoft Office Excel 2007 中的所有新和不支持早期版本中。</span><span class="sxs-lookup"><span data-stu-id="22a39-205">The types **C%**, **F%**, **D%**, **G%**, **K%**, **O%**, **Q**, and **U** were all new in Microsoft Office Excel 2007 and are not supported in earlier versions.</span></span> <span data-ttu-id="22a39-206">**F**、 **F %**、 **G**、 和**G %** 的字符串类型用于修改就地的参数。</span><span class="sxs-lookup"><span data-stu-id="22a39-206">The string types **F**, **F%**, **G**, and **G%** are used for arguments that are modified-in-place.</span></span> <span data-ttu-id="22a39-207">时**XLOPER**或**XLOPER12**参数分别注册为**P**或**Q**的类型，Excel 就会转换简单值的单个单元格引用和数组的多单元格引用时它准备它们。</span><span class="sxs-lookup"><span data-stu-id="22a39-207">When **XLOPER** or **XLOPER12** arguments are registered as types **P** or **Q** respectively, Excel converts single-cell references to simple values and multi-cell references to arrays when it prepares them.</span></span> 
  
<span data-ttu-id="22a39-208">**P**和**Q**类型始终进入您函数为以下类型之一： **xltypeNum**、 **xltypeStr**、 **xltypeBool**、 **xltypeErr**、 **xltypeMulti**、 **xltypeMissing**或**xltypeNil**，但不**xltypeRef**或**xltypeSRef**因为这些始终取消引用。</span><span class="sxs-lookup"><span data-stu-id="22a39-208">**P** and **Q** types always arrive in your function as one of the following types: **xltypeNum**, **xltypeStr**, **xltypeBool**, **xltypeErr**, **xltypeMulti**, **xltypeMissing**, or **xltypeNil**, but not **xltypeRef** or **xltypeSRef** because these are always dereferenced.</span></span> 
  
<span data-ttu-id="22a39-209">类型**O**，实际上是在堆栈上的三个参数，引入了与 Fortran Dll 的引用传递的参数的兼容性。</span><span class="sxs-lookup"><span data-stu-id="22a39-209">Type **O**, which is really three arguments on the stack, was introduced for compatibility with Fortran DLLs where arguments are passed by reference.</span></span> <span data-ttu-id="22a39-210">它不能用于通过声明作为修改就地返回值参数并将结果放中引用的值返回除值。</span><span class="sxs-lookup"><span data-stu-id="22a39-210">It cannot be used to return a value except by declaring the argument as a modify-in-place return value and placing the results in the referenced values.</span></span> <span data-ttu-id="22a39-211">键入 **%o%** 扩展 Excel 2007 中的**O**类型，以便它可以访问覆盖区域大于 Office Excel 2003 网格的数组。</span><span class="sxs-lookup"><span data-stu-id="22a39-211">Type **O%** extends type **O** in Excel 2007 so that it can access arrays that cover areas larger than the Office Excel 2003 grid.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="22a39-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22a39-212">See also</span></span>

- [<span data-ttu-id="22a39-213">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="22a39-213">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="22a39-214">Excel Programming Concepts</span><span class="sxs-lookup"><span data-stu-id="22a39-214">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
- [<span data-ttu-id="22a39-215">Excel XLL SDK API Function Reference</span><span class="sxs-lookup"><span data-stu-id="22a39-215">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)

