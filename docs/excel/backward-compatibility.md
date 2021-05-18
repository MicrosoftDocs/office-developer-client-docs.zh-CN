---
title: 向后兼容性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- version compatibility [excel 2007]，XLL compatibility [Excel 2007]，backward compatibility [Excel 2007]
localization_priority: Normal
ms.assetid: ac200824-0620-4f03-8bd2-59226c1e79d7
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3e1368ef55b96be947527456e0f01918afec6663
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301678"
---
# <a name="backward-compatibility"></a><span data-ttu-id="2c676-104">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="2c676-104">Backward compatibility</span></span>

<span data-ttu-id="2c676-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2c676-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2c676-106">本主题解决不同版本的 Microsoft Excel 中的 XLL 兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="2c676-106">This topic addresses issues of XLL compatibility in different versions of Microsoft Excel.</span></span>
  
## <a name="useful-constant-definitions"></a><span data-ttu-id="2c676-107">有用的常量定义</span><span class="sxs-lookup"><span data-stu-id="2c676-107">Useful constant definitions</span></span>

<span data-ttu-id="2c676-108">请考虑在 XLL 项目代码中包含与这些类似的定义，并替换此上下文中使用文字编号的所有实例。</span><span class="sxs-lookup"><span data-stu-id="2c676-108">Consider including definitions similar to these in your XLL project code and replacing all instances of literal numbers used in this context.</span></span> <span data-ttu-id="2c676-109">这将阐明特定于版本的代码，并减少与版本相关的错误的可能性，形式为不一样的数字。</span><span class="sxs-lookup"><span data-stu-id="2c676-109">This will clarify code that is version specific, and reduce the likelihood of version-related bugs in the form of innocuous-looking numbers.</span></span>
  
```cpp
#define MAX_XL11_ROWS            65536
#define MAX_XL11_COLS              256
#define MAX_XL12_ROWS          1048576
#define MAX_XL12_COLS            16384
#define MAX_XL11_UDF_ARGS           30
#define MAX_XL12_UDF_ARGS          255
#define MAX_XL4_STR_LEN           255u
#define MAX_XL12_STR_LEN        32767u
```

## <a name="getting-the-running-version"></a><span data-ttu-id="2c676-110">获取正在运行的版本</span><span class="sxs-lookup"><span data-stu-id="2c676-110">Getting the running version</span></span>

<span data-ttu-id="2c676-111">应检测使用 运行的版本，其中 是设置为 2 的数字  `Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`  `arg` **XLOPER，version** 是字符串 **XLOPER，** 然后可以强制转换为整数。</span><span class="sxs-lookup"><span data-stu-id="2c676-111">You should detect which version is running using  `Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`, where  `arg` is a numeric **XLOPER** set to 2 and version is a string **XLOPER** which can then be coerced to an integer.</span></span> <span data-ttu-id="2c676-112">对于 Microsoft Excel 2013，这是 15.0。</span><span class="sxs-lookup"><span data-stu-id="2c676-112">For Microsoft Excel 2013, this is 15.0.</span></span> <span data-ttu-id="2c676-113">应在 xlAutoOpen 函数中或从 [xlAutoOpen 函数中执行](xlautoopen.md) 此操作。</span><span class="sxs-lookup"><span data-stu-id="2c676-113">You should do this in, or from, the [xlAutoOpen](xlautoopen.md) function.</span></span> <span data-ttu-id="2c676-114">然后，您可以设置一个全局变量，该变量通知项目中的所有模块正在运行哪个版本的 Excel。</span><span class="sxs-lookup"><span data-stu-id="2c676-114">You can then set a global variable that informs all of the modules in your project which version of Excel is running.</span></span> <span data-ttu-id="2c676-115">然后，代码可以决定是使用 **Excel12** 和 **XLOPER12** 调用 C API，还是使用 **XLOPER** s 使用 **Excel4。**</span><span class="sxs-lookup"><span data-stu-id="2c676-115">Your code can then decide whether to call the C API using **Excel12** and **XLOPER12** s, or using **Excel4** using **XLOPER** s.</span></span>
  
<span data-ttu-id="2c676-116">您可以调用 **XLCallVer** 来发现 C API 版本，但这并不意味着您运行的是 Excel 2007 之前的版本。</span><span class="sxs-lookup"><span data-stu-id="2c676-116">You can call **XLCallVer** to discover the C API version, but this does not indicate which of the pre-Excel 2007 versions you are running.</span></span> 
  
## <a name="creating-add-ins-that-export-dual-interfaces"></a><span data-ttu-id="2c676-117">创建导出双接口的外接程序</span><span class="sxs-lookup"><span data-stu-id="2c676-117">Creating add-ins that export dual interfaces</span></span>

<span data-ttu-id="2c676-118">请考虑一个 XLL 函数，该函数接受一个字符串并返回一个可以是任何工作表数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c676-118">Consider an XLL function that takes a string and returns a value that can be any of the worksheet data types.</span></span> <span data-ttu-id="2c676-119">您可以导出注册为类型"PD"的函数，并按如下方式建立原型，其中字符串作为长度计数字节字符串传递。</span><span class="sxs-lookup"><span data-stu-id="2c676-119">You could export a function registered as type "PD" and prototyped as follows where the string is passed as a length-counted byte string.</span></span>
  
`LPXLOPER WINAPI my_xll_fn(unsigned char *arg);`
  
<span data-ttu-id="2c676-120">尽管这运行良好，但有几个原因导致这不是从 Excel 2007 开始的代码的理想接口：</span><span class="sxs-lookup"><span data-stu-id="2c676-120">Although this works perfectly well, there are several reasons why this is not the ideal interface to your code starting in Excel 2007:</span></span>
  
- <span data-ttu-id="2c676-121">它受 C API 字节字符串的限制，无法访问自 Excel 2007 起支持的长 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="2c676-121">It is subject to the limitations of C API byte strings and cannot access the long Unicode strings supported starting in Excel 2007.</span></span>
    
- <span data-ttu-id="2c676-122">尽管从 Excel 2007 开始，Excel 可以传递和接受 **XLOPER，** 但它在内部会将其转换为 **XLOPER12，** 因此从 Excel 2007 开始存在隐式转换开销，当代码在早期版本的 Excel 中运行时，不存在此开销。</span><span class="sxs-lookup"><span data-stu-id="2c676-122">Although, starting in Excel 2007, Excel can pass and accept **XLOPER** s, internally it converts them to **XLOPER12** s, so there is an implicit conversion overhead starting in Excel 2007 that is not there when the code runs in earlier versions of Excel.</span></span>
    
- <span data-ttu-id="2c676-123">此函数可能是使线程安全函数，但如果类型字符串更改为 ，在  `PD$` Excel 2007 之前注册将失败。</span><span class="sxs-lookup"><span data-stu-id="2c676-123">It may be that this function can be made thread safe, but if the type string is changed to  `PD$`, registration fails in starting before Excel 2007.</span></span>
    
<span data-ttu-id="2c676-124">出于这些原因，理想情况下，从 Excel 2007 开始，您应该为注册为 的用户导出函数，假定您的代码是线程安全的，并按如下所示  `QD%$` 进行原型制作。</span><span class="sxs-lookup"><span data-stu-id="2c676-124">For these reasons, ideally, starting in Excel 2007 you should export a function for your users that was registered as  `QD%$`, assuming your code is thread safe and prototyped as follows.</span></span>
  
`LPXLOPER12 WINAPI my_xll_fn_v12(wchar_t *arg);`
  
<span data-ttu-id="2c676-125">您可能想要从 Excel 2007 开始注册其他函数的另一个原因是，它允许 XLL 函数最多使用 255 个参数，而不是早期版本的 30 个限制。</span><span class="sxs-lookup"><span data-stu-id="2c676-125">Another reason why you might want to register a different function starting in Excel 2007 is that it permits XLL functions to take up to 255 arguments, instead of the 30 limit of earlier versions.</span></span>
  
<span data-ttu-id="2c676-126">幸运的是，通过从项目中导出这两个版本，您可以同时获得这两个优势。</span><span class="sxs-lookup"><span data-stu-id="2c676-126">Fortunately, you can have the benefits of both by exporting both versions from your project.</span></span> <span data-ttu-id="2c676-127">然后，您可以检测正在运行的 Excel 版本，并按条件注册最合适的函数。</span><span class="sxs-lookup"><span data-stu-id="2c676-127">You can then detect the running Excel version and conditionally register the most appropriate function.</span></span> <span data-ttu-id="2c676-128">有关详细信息和示例实现，请参阅 Developing [Add-ins (XLL) in Excel 2007。](https://msdn.microsoft.com/library/aa730920.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c676-128">For more information and an example implementation, see [Developing Add-ins (XLLs) in Excel 2007](https://msdn.microsoft.com/library/aa730920.aspx).</span></span>
  
<span data-ttu-id="2c676-129">此方法导致在 Excel 2003 中运行的工作表显示的结果可能不同于从 Excel 2007 开始运行的同一工作表的结果。</span><span class="sxs-lookup"><span data-stu-id="2c676-129">This approach leads to the possibility that a worksheet running in Excel 2003 could display different results than the same sheet running starting in Excel 2007.</span></span> <span data-ttu-id="2c676-130">例如，Excel 2003 将 Excel 2003 工作表单元格中的 Unicode 字符串映射到 ASCII 字节字符串，并在将字符串传递给 XLL 函数之前截断该字符串。</span><span class="sxs-lookup"><span data-stu-id="2c676-130">For example, Excel 2003 would map a Unicode string in an Excel 2003 worksheet cell to an ASCII byte-string and truncate it before passing it to an XLL function.</span></span> <span data-ttu-id="2c676-131">从 Excel 2007 开始，Excel 将反向 Unicode 字符串传递给以正确方式注册的 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="2c676-131">Starting in Excel 2007, Excel will pass an unconverted Unicode string to an XLL function registered in the right way.</span></span> <span data-ttu-id="2c676-132">这可能会导致不同的结果。</span><span class="sxs-lookup"><span data-stu-id="2c676-132">This could lead to a different result.</span></span> <span data-ttu-id="2c676-133">您应该了解此可能性以及给用户的后果，而不只是在升级过程中。</span><span class="sxs-lookup"><span data-stu-id="2c676-133">You should be aware of this possibility and the consequences to your users, not just in the upgrade.</span></span> <span data-ttu-id="2c676-134">例如，在 Excel 2000 和 Excel 2003 之间改进了一些内置数值函数。</span><span class="sxs-lookup"><span data-stu-id="2c676-134">For example, some built-in numeric functions were improved between Excel 2000 and Excel 2003.</span></span>
  
## <a name="new-worksheet-functions-and-analysis-toolpak-functions"></a><span data-ttu-id="2c676-135">新的工作表函数和分析工具库函数</span><span class="sxs-lookup"><span data-stu-id="2c676-135">New Worksheet functions and Analysis Toolpak functions</span></span>

<span data-ttu-id="2c676-136">分析工具库 (ATP) 函数是自 Excel 2007 起 Excel 的一部分。</span><span class="sxs-lookup"><span data-stu-id="2c676-136">Analysis Toolpak (ATP) functions are part of Excel starting in Excel 2007.</span></span> <span data-ttu-id="2c676-137">以前，XLL 只能使用 [xlUDF](xludf.md)调用 ATP 函数。</span><span class="sxs-lookup"><span data-stu-id="2c676-137">Previously, an XLL could only call an ATP function by using [xlUDF](xludf.md).</span></span> <span data-ttu-id="2c676-138">从 Excel 2007 开始，应该使用 xlcall.h 中定义的函数枚举来调用 ATP 函数。</span><span class="sxs-lookup"><span data-stu-id="2c676-138">Starting in Excel 2007, the ATP functions should be called using the function enumerations defined in xlcall.h.</span></span> <span data-ttu-id="2c676-139">从 DLL 调用用户定义函数中的示例演示了两种不同的方法。</span><span class="sxs-lookup"><span data-stu-id="2c676-139">The example in Calling User-defined Functions from DLLs demonstrates the two different methods.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c676-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c676-140">See also</span></span>

- [<span data-ttu-id="2c676-141">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="2c676-141">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md) 
- [<span data-ttu-id="2c676-142">在 Excel 中使用 C API 进行编程</span><span class="sxs-lookup"><span data-stu-id="2c676-142">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
- [<span data-ttu-id="2c676-143">适用于 Excel 的 C API 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="2c676-143">What's New in the C API for Excel</span></span>](what-s-new-in-the-c-api-for-excel.md)

