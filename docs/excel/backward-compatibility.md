---
title: 向后兼容性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 版本兼容性 [excel 2007], XLL 兼容性 [excel 2007], 向后兼容性 [excel 2007]
localization_priority: Normal
ms.assetid: ac200824-0620-4f03-8bd2-59226c1e79d7
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3e1368ef55b96be947527456e0f01918afec6663
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301678"
---
# <a name="backward-compatibility"></a><span data-ttu-id="52272-104">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="52272-104">Backward compatibility</span></span>

<span data-ttu-id="52272-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52272-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="52272-106">本主题解决不同版本的 Microsoft Excel 中的 XLL 兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="52272-106">This topic addresses issues of XLL compatibility in different versions of Microsoft Excel.</span></span>
  
## <a name="useful-constant-definitions"></a><span data-ttu-id="52272-107">有用的常量定义</span><span class="sxs-lookup"><span data-stu-id="52272-107">Useful constant definitions</span></span>

<span data-ttu-id="52272-108">请考虑在 XLL 项目代码中包括与以下内容类似的定义, 并替换此上下文中使用的文本编号的所有实例。</span><span class="sxs-lookup"><span data-stu-id="52272-108">Consider including definitions similar to these in your XLL project code and replacing all instances of literal numbers used in this context.</span></span> <span data-ttu-id="52272-109">这将阐明特定于版本的代码, 并以看似无害的数字的形式降低与版本相关的 bug 的可能性。</span><span class="sxs-lookup"><span data-stu-id="52272-109">This will clarify code that is version specific, and reduce the likelihood of version-related bugs in the form of innocuous-looking numbers.</span></span>
  
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

## <a name="getting-the-running-version"></a><span data-ttu-id="52272-110">获取正在运行的版本</span><span class="sxs-lookup"><span data-stu-id="52272-110">Getting the running version</span></span>

<span data-ttu-id="52272-111">应`Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`检测使用哪个版本正在运行, `arg`其中是将数值**XLOPER**设置为 2, 版本是字符串**XLOPER** , 然后可以将该字符串强制转换为整数。</span><span class="sxs-lookup"><span data-stu-id="52272-111">You should detect which version is running using  `Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`, where  `arg` is a numeric **XLOPER** set to 2 and version is a string **XLOPER** which can then be coerced to an integer.</span></span> <span data-ttu-id="52272-112">对于 Microsoft Excel 2013, 此为15.0。</span><span class="sxs-lookup"><span data-stu-id="52272-112">For Microsoft Excel 2013, this is 15.0.</span></span> <span data-ttu-id="52272-113">应在[xlAutoOpen](xlautoopen.md)函数中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="52272-113">You should do this in, or from, the [xlAutoOpen](xlautoopen.md) function.</span></span> <span data-ttu-id="52272-114">然后, 您可以设置一个全局变量, 用于通知项目中的所有模块运行的是哪个版本的 Excel。</span><span class="sxs-lookup"><span data-stu-id="52272-114">You can then set a global variable that informs all of the modules in your project which version of Excel is running.</span></span> <span data-ttu-id="52272-115">然后, 您的代码可以决定是使用**Excel12**和**XLOPER12**s 调用 C API, 还是使用**XLOPER**s 调用**Excel4** 。</span><span class="sxs-lookup"><span data-stu-id="52272-115">Your code can then decide whether to call the C API using **Excel12** and **XLOPER12**s, or using **Excel4** using **XLOPER**s.</span></span>
  
<span data-ttu-id="52272-116">您可以调用**XLCallVer**来发现 C API 版本, 但这并不表示运行的是 Excel 的前2007版本中的哪一个。</span><span class="sxs-lookup"><span data-stu-id="52272-116">You can call **XLCallVer** to discover the C API version, but this does not indicate which of the pre-Excel 2007 versions you are running.</span></span> 
  
## <a name="creating-add-ins-that-export-dual-interfaces"></a><span data-ttu-id="52272-117">创建导出双重接口的外接程序</span><span class="sxs-lookup"><span data-stu-id="52272-117">Creating add-ins that export dual interfaces</span></span>

<span data-ttu-id="52272-118">考虑使用一个字符串的 XLL 函数, 并返回一个可以是任何工作表数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="52272-118">Consider an XLL function that takes a string and returns a value that can be any of the worksheet data types.</span></span> <span data-ttu-id="52272-119">您可以导出注册为类型 "PD" 和 "原型" 的函数, 如下所示, 在将字符串作为长度计数的字节字符串传递。</span><span class="sxs-lookup"><span data-stu-id="52272-119">You could export a function registered as type "PD" and prototyped as follows where the string is passed as a length-counted byte string.</span></span>
  
`LPXLOPER WINAPI my_xll_fn(unsigned char *arg);`
  
<span data-ttu-id="52272-120">虽然这非常有效, 但在 Excel 2007 中, 这并不是您的代码的理想界面的原因有以下几个:</span><span class="sxs-lookup"><span data-stu-id="52272-120">Although this works perfectly well, there are several reasons why this is not the ideal interface to your code starting in Excel 2007:</span></span>
  
- <span data-ttu-id="52272-121">它受 C API 字节字符串限制的限制, 无法访问在 Excel 2007 中开始支持的长 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="52272-121">It is subject to the limitations of C API byte strings and cannot access the long Unicode strings supported starting in Excel 2007.</span></span>
    
- <span data-ttu-id="52272-122">[! 注意] 在 excel 2007 中, excel 可以传递和接受**XLOPER**s, 在内部它会将它们转换为**XLOPER12**s, 因此在 excel 2007 中, 在 excel 的早期版本中运行时, 不会出现从 excel 中开始的隐式转换开销。</span><span class="sxs-lookup"><span data-stu-id="52272-122">Although, starting in Excel 2007, Excel can pass and accept **XLOPER**s, internally it converts them to **XLOPER12**s, so there is an implicit conversion overhead starting in Excel 2007 that is not there when the code runs in earlier versions of Excel.</span></span>
    
- <span data-ttu-id="52272-123">可以使此函数成为线程安全的, 但如果类型字符串已更改为`PD$`, 则注册将在 Excel 2007 之前的启动过程中失败。</span><span class="sxs-lookup"><span data-stu-id="52272-123">It may be that this function can be made thread safe, but if the type string is changed to  `PD$`, registration fails in starting before Excel 2007.</span></span>
    
<span data-ttu-id="52272-124">出于这些原因, 理想情况下, 从 Excel 2007 开始, 应导出注册为`QD%$`的用户的函数, 假定您的代码是线程安全和原型, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="52272-124">For these reasons, ideally, starting in Excel 2007 you should export a function for your users that was registered as  `QD%$`, assuming your code is thread safe and prototyped as follows.</span></span>
  
`LPXLOPER12 WINAPI my_xll_fn_v12(wchar_t *arg);`
  
<span data-ttu-id="52272-125">您可能想要在 Excel 2007 中开始注册不同函数的另一个原因是, 它允许 XLL 函数最长为255个参数, 而不是较早版本的30个限制。</span><span class="sxs-lookup"><span data-stu-id="52272-125">Another reason why you might want to register a different function starting in Excel 2007 is that it permits XLL functions to take up to 255 arguments, instead of the 30 limit of earlier versions.</span></span>
  
<span data-ttu-id="52272-126">幸运的是, 可以通过从项目中导出这两个版本来获得这两个版本的好处。</span><span class="sxs-lookup"><span data-stu-id="52272-126">Fortunately, you can have the benefits of both by exporting both versions from your project.</span></span> <span data-ttu-id="52272-127">然后, 您可以检测正在运行的 Excel 版本, 并有条件地注册最合适的函数。</span><span class="sxs-lookup"><span data-stu-id="52272-127">You can then detect the running Excel version and conditionally register the most appropriate function.</span></span> <span data-ttu-id="52272-128">有关详细信息和示例实现, 请参阅[在 Excel 2007 中开发外接程序 (xll)](https://msdn.microsoft.com/library/aa730920.aspx)。</span><span class="sxs-lookup"><span data-stu-id="52272-128">For more information and an example implementation, see [Developing Add-ins (XLLs) in Excel 2007](https://msdn.microsoft.com/library/aa730920.aspx).</span></span>
  
<span data-ttu-id="52272-129">此方法使运行在 excel 2003 中的工作表显示的结果可能与运行在 excel 2007 中的同一工作表显示不同的结果。</span><span class="sxs-lookup"><span data-stu-id="52272-129">This approach leads to the possibility that a worksheet running in Excel 2003 could display different results than the same sheet running starting in Excel 2007.</span></span> <span data-ttu-id="52272-130">例如, excel 2003 会将 excel 2003 工作表单元格中的 Unicode 字符串映射为 ASCII 字节字符串, 并在将其传递给 XLL 函数之前将其截断。</span><span class="sxs-lookup"><span data-stu-id="52272-130">For example, Excel 2003 would map a Unicode string in an Excel 2003 worksheet cell to an ASCII byte-string and truncate it before passing it to an XLL function.</span></span> <span data-ttu-id="52272-131">从 excel 2007 开始, excel 会将未转换的 Unicode 字符串传递给以正确方式注册的 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="52272-131">Starting in Excel 2007, Excel will pass an unconverted Unicode string to an XLL function registered in the right way.</span></span> <span data-ttu-id="52272-132">这可能会导致不同的结果。</span><span class="sxs-lookup"><span data-stu-id="52272-132">This could lead to a different result.</span></span> <span data-ttu-id="52272-133">您应了解这种可能性以及对用户产生的后果, 而不只是在升级中。</span><span class="sxs-lookup"><span data-stu-id="52272-133">You should be aware of this possibility and the consequences to your users, not just in the upgrade.</span></span> <span data-ttu-id="52272-134">例如, 在 excel 2000 和 excel 2003 之间改进了一些内置数值函数。</span><span class="sxs-lookup"><span data-stu-id="52272-134">For example, some built-in numeric functions were improved between Excel 2000 and Excel 2003.</span></span>
  
## <a name="new-worksheet-functions-and-analysis-toolpak-functions"></a><span data-ttu-id="52272-135">新的工作表函数和分析工具库函数</span><span class="sxs-lookup"><span data-stu-id="52272-135">New Worksheet functions and Analysis Toolpak functions</span></span>

<span data-ttu-id="52272-136">分析工具库 (ATP) 函数是 excel 2007 中启动的 excel 的一部分。</span><span class="sxs-lookup"><span data-stu-id="52272-136">Analysis Toolpak (ATP) functions are part of Excel starting in Excel 2007.</span></span> <span data-ttu-id="52272-137">以前, XLL 只能通过使用[xlUDF](xludf.md)调用 ATP 函数。</span><span class="sxs-lookup"><span data-stu-id="52272-137">Previously, an XLL could only call an ATP function by using [xlUDF](xludf.md).</span></span> <span data-ttu-id="52272-138">从 Excel 2007 开始, 应使用 xlcall.h 中定义的函数枚举调用 ATP 函数。</span><span class="sxs-lookup"><span data-stu-id="52272-138">Starting in Excel 2007, the ATP functions should be called using the function enumerations defined in xlcall.h.</span></span> <span data-ttu-id="52272-139">从 dll 调用用户定义的函数的示例演示了两种不同的方法。</span><span class="sxs-lookup"><span data-stu-id="52272-139">The example in Calling User-defined Functions from DLLs demonstrates the two different methods.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52272-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52272-140">See also</span></span>

- [<span data-ttu-id="52272-141">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="52272-141">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md) 
- [<span data-ttu-id="52272-142">在 Excel 中使用 C API 进行编程</span><span class="sxs-lookup"><span data-stu-id="52272-142">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
- [<span data-ttu-id="52272-143">适用于 Excel 的 C API 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="52272-143">What's New in the C API for Excel</span></span>](what-s-new-in-the-c-api-for-excel.md)

