---
title: 向后兼容性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 版本兼容性 [excel 2007]，XLL 兼容性 [Excel 2007] 中，向后兼容性 [Excel 2007]
localization_priority: Normal
ms.assetid: ac200824-0620-4f03-8bd2-59226c1e79d7
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3e1368ef55b96be947527456e0f01918afec6663
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387970"
---
# <a name="backward-compatibility"></a><span data-ttu-id="e85d2-104">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="e85d2-104">Backward compatibility</span></span>

<span data-ttu-id="e85d2-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e85d2-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e85d2-106">本主题介绍 XLL 不同版本的 Microsoft Excel 中的兼容性的问题。</span><span class="sxs-lookup"><span data-stu-id="e85d2-106">This topic addresses issues of XLL compatibility in different versions of Microsoft Excel.</span></span>
  
## <a name="useful-constant-definitions"></a><span data-ttu-id="e85d2-107">有用的常量定义</span><span class="sxs-lookup"><span data-stu-id="e85d2-107">Useful constant definitions</span></span>

<span data-ttu-id="e85d2-108">考虑包括定义类似于以下 XLL 项目代码和替换文本的数字，在此上下文中使用的所有实例中。</span><span class="sxs-lookup"><span data-stu-id="e85d2-108">Consider including definitions similar to these in your XLL project code and replacing all instances of literal numbers used in this context.</span></span> <span data-ttu-id="e85d2-109">这将阐述特定于，版本的代码，并降低版本相关的外观无关紧要的数字形式的错误的可能性。</span><span class="sxs-lookup"><span data-stu-id="e85d2-109">This will clarify code that is version specific, and reduce the likelihood of version-related bugs in the form of innocuous-looking numbers.</span></span>
  
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

## <a name="getting-the-running-version"></a><span data-ttu-id="e85d2-110">获取运行的版本</span><span class="sxs-lookup"><span data-stu-id="e85d2-110">Getting the running version</span></span>

<span data-ttu-id="e85d2-111">您应该会检测到哪些版本是否正在运行使用`Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`，其中`arg`为数值型**XLOPER**设置为 2 和版本是一个字符串**XLOPER**然后可以强制为一个整数值。</span><span class="sxs-lookup"><span data-stu-id="e85d2-111">You should detect which version is running using  `Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`, where  `arg` is a numeric **XLOPER** set to 2 and version is a string **XLOPER** which can then be coerced to an integer.</span></span> <span data-ttu-id="e85d2-112">对于 Microsoft Excel 2013，这是 15.0。</span><span class="sxs-lookup"><span data-stu-id="e85d2-112">For Microsoft Excel 2013, this is 15.0.</span></span> <span data-ttu-id="e85d2-113">在中，或[xlAutoOpen](xlautoopen.md)函数中，您应这样做。</span><span class="sxs-lookup"><span data-stu-id="e85d2-113">You should do this in, or from, the [xlAutoOpen](xlautoopen.md) function.</span></span> <span data-ttu-id="e85d2-114">然后，您可以设置通知的所有模块正在运行哪个版本的 Excel 项目中的全局变量。</span><span class="sxs-lookup"><span data-stu-id="e85d2-114">You can then set a global variable that informs all of the modules in your project which version of Excel is running.</span></span> <span data-ttu-id="e85d2-115">代码然后可以决定是否要调用的 C API 使用**Excel12**和**XLOPER12**s，或使用**Excel4**使用**XLOPER**s。</span><span class="sxs-lookup"><span data-stu-id="e85d2-115">Your code can then decide whether to call the C API using **Excel12** and **XLOPER12**s, or using **Excel4** using **XLOPER**s.</span></span>
  
<span data-ttu-id="e85d2-116">您可以调用**XLCallVer**发现 C API 版本中，但这并不表示其正在运行的 Excel 2007 版本。</span><span class="sxs-lookup"><span data-stu-id="e85d2-116">You can call **XLCallVer** to discover the C API version, but this does not indicate which of the pre-Excel 2007 versions you are running.</span></span> 
  
## <a name="creating-add-ins-that-export-dual-interfaces"></a><span data-ttu-id="e85d2-117">创建外接程序导出双重接口</span><span class="sxs-lookup"><span data-stu-id="e85d2-117">Creating add-ins that export dual interfaces</span></span>

<span data-ttu-id="e85d2-118">请考虑采用的字符串，并返回一个值，它可以是任何工作表数据类型的 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="e85d2-118">Consider an XLL function that takes a string and returns a value that can be any of the worksheet data types.</span></span> <span data-ttu-id="e85d2-119">您无法导出键入"PD"注册和原型的函数，如下所示其中长度计数字节字符串形式传递的字符串。</span><span class="sxs-lookup"><span data-stu-id="e85d2-119">You could export a function registered as type "PD" and prototyped as follows where the string is passed as a length-counted byte string.</span></span>
  
`LPXLOPER WINAPI my_xll_fn(unsigned char *arg);`
  
<span data-ttu-id="e85d2-120">尽管这非常好工作，但有以下几种原因这不是启动 Excel 2007 中代码的理想接口：</span><span class="sxs-lookup"><span data-stu-id="e85d2-120">Although this works perfectly well, there are several reasons why this is not the ideal interface to your code starting in Excel 2007:</span></span>
  
- <span data-ttu-id="e85d2-121">它受限制的 C API 字节字符串，并且无法访问 Excel 2007 中启动长 Unicode 字符串支持。</span><span class="sxs-lookup"><span data-stu-id="e85d2-121">It is subject to the limitations of C API byte strings and cannot access the long Unicode strings supported starting in Excel 2007.</span></span>
    
- <span data-ttu-id="e85d2-122">尽管从 Excel 2007 开始，Excel 可以传递和接受**XLOPER**s、 内部它将其转换为**XLOPER12**s，因此不存在的 Excel 的早期版本中的代码运行时的 Excel 2007 中启动隐式转换开销。</span><span class="sxs-lookup"><span data-stu-id="e85d2-122">Although, starting in Excel 2007, Excel can pass and accept **XLOPER**s, internally it converts them to **XLOPER12**s, so there is an implicit conversion overhead starting in Excel 2007 that is not there when the code runs in earlier versions of Excel.</span></span>
    
- <span data-ttu-id="e85d2-123">可能的此函数可线程安全的但如果字符串类型更改为`PD$`，在 Excel 2007 之前开始注册失败。</span><span class="sxs-lookup"><span data-stu-id="e85d2-123">It may be that this function can be made thread safe, but if the type string is changed to  `PD$`, registration fails in starting before Excel 2007.</span></span>
    
<span data-ttu-id="e85d2-124">出于以上原因，理想情况下，在 Excel 2007 中启动应导出函数为用户的已注册为`QD%$`，假定您的代码线程安全和原型如下所示。</span><span class="sxs-lookup"><span data-stu-id="e85d2-124">For these reasons, ideally, starting in Excel 2007 you should export a function for your users that was registered as  `QD%$`, assuming your code is thread safe and prototyped as follows.</span></span>
  
`LPXLOPER12 WINAPI my_xll_fn_v12(wchar_t *arg);`
  
<span data-ttu-id="e85d2-125">为什么您可能要注册不同函数启动 Excel 2007 中的另一个原因是它还允许 XLL 函数带最多 255 个参数，而不是早期版本的 30 限制。</span><span class="sxs-lookup"><span data-stu-id="e85d2-125">Another reason why you might want to register a different function starting in Excel 2007 is that it permits XLL functions to take up to 255 arguments, instead of the 30 limit of earlier versions.</span></span>
  
<span data-ttu-id="e85d2-126">幸运的是，您可以同时按从您的项目导出两个版本的好处。</span><span class="sxs-lookup"><span data-stu-id="e85d2-126">Fortunately, you can have the benefits of both by exporting both versions from your project.</span></span> <span data-ttu-id="e85d2-127">您可以然后检测正在运行的 Excel 版本，并有条件地注册最适当的函数。</span><span class="sxs-lookup"><span data-stu-id="e85d2-127">You can then detect the running Excel version and conditionally register the most appropriate function.</span></span> <span data-ttu-id="e85d2-128">有关详细信息和实现示例，请参阅[Developing 加载项 （xll （英文）） 在 Excel 2007 中](https://msdn.microsoft.com/library/aa730920.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e85d2-128">For more information and an example implementation, see [Developing Add-ins (XLLs) in Excel 2007](https://msdn.microsoft.com/library/aa730920.aspx).</span></span>
  
<span data-ttu-id="e85d2-129">此方法会导致在 Excel 2003 中运行的工作表无法显示不同的结果运行启动 Excel 2007 中的同一工作表的可能性。</span><span class="sxs-lookup"><span data-stu-id="e85d2-129">This approach leads to the possibility that a worksheet running in Excel 2003 could display different results than the same sheet running starting in Excel 2007.</span></span> <span data-ttu-id="e85d2-130">例如，Excel 2003 会将 Excel 2003 工作表单元格的 Unicode 字符串映射到 ASCII 字节字符串，然后截断它传递到 XLL 函数之前。</span><span class="sxs-lookup"><span data-stu-id="e85d2-130">For example, Excel 2003 would map a Unicode string in an Excel 2003 worksheet cell to an ASCII byte-string and truncate it before passing it to an XLL function.</span></span> <span data-ttu-id="e85d2-131">从 Excel 2007 开始，Excel 会将未转换的 Unicode 字符串传递给以正确的方式中注册的 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="e85d2-131">Starting in Excel 2007, Excel will pass an unconverted Unicode string to an XLL function registered in the right way.</span></span> <span data-ttu-id="e85d2-132">这可能导致不同的结果。</span><span class="sxs-lookup"><span data-stu-id="e85d2-132">This could lead to a different result.</span></span> <span data-ttu-id="e85d2-133">您应注意这种可能性和后果给用户，而不仅仅是升级中。</span><span class="sxs-lookup"><span data-stu-id="e85d2-133">You should be aware of this possibility and the consequences to your users, not just in the upgrade.</span></span> <span data-ttu-id="e85d2-134">例如，一些内置的数值函数进行了改进 Excel 2000 和 Excel 2003 之间。</span><span class="sxs-lookup"><span data-stu-id="e85d2-134">For example, some built-in numeric functions were improved between Excel 2000 and Excel 2003.</span></span>
  
## <a name="new-worksheet-functions-and-analysis-toolpak-functions"></a><span data-ttu-id="e85d2-135">新工作表函数和分析工具库函数</span><span class="sxs-lookup"><span data-stu-id="e85d2-135">New Worksheet functions and Analysis Toolpak functions</span></span>

<span data-ttu-id="e85d2-136">分析工具库 (ATP) 函数是启动 Excel 2007 中的 Excel 的一部分。</span><span class="sxs-lookup"><span data-stu-id="e85d2-136">Analysis Toolpak (ATP) functions are part of Excel starting in Excel 2007.</span></span> <span data-ttu-id="e85d2-137">以前，XLL 仅可以使用[xlUDF](xludf.md)调用 ATP 函数。</span><span class="sxs-lookup"><span data-stu-id="e85d2-137">Previously, an XLL could only call an ATP function by using [xlUDF](xludf.md).</span></span> <span data-ttu-id="e85d2-138">从 Excel 2007 开始，ATP 函数应该调用使用 xlcall.h 中定义的函数枚举。</span><span class="sxs-lookup"><span data-stu-id="e85d2-138">Starting in Excel 2007, the ATP functions should be called using the function enumerations defined in xlcall.h.</span></span> <span data-ttu-id="e85d2-139">从 Dll 调用用户定义函数中的示例演示两个不同的方法。</span><span class="sxs-lookup"><span data-stu-id="e85d2-139">The example in Calling User-defined Functions from DLLs demonstrates the two different methods.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e85d2-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e85d2-140">See also</span></span>

- [<span data-ttu-id="e85d2-141">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="e85d2-141">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md) 
- [<span data-ttu-id="e85d2-142">在 Excel 中使用 C API 进行编程</span><span class="sxs-lookup"><span data-stu-id="e85d2-142">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
- [<span data-ttu-id="e85d2-143">适用于 Excel 的 C API 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="e85d2-143">What's New in the C API for Excel</span></span>](what-s-new-in-the-c-api-for-excel.md)

