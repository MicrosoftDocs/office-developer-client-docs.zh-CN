---
title: XLL Excel中的已知问题
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 已知问题 [excel 2007]
localization_priority: Normal
ms.assetid: 3dfecc0b-a91c-448e-8721-5d3486b625fa
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 34784f6895386efe7e6c3ca7ec213c7d71931058
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304002"
---
# <a name="known-issues-in-excel-xll-development"></a><span data-ttu-id="bdf62-104">XLL Excel中的已知问题</span><span class="sxs-lookup"><span data-stu-id="bdf62-104">Known Issues in Excel XLL Development</span></span>

 <span data-ttu-id="bdf62-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bdf62-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="bdf62-106">本主题介绍 XLL Microsoft Excel可能会遇到的已知问题。</span><span class="sxs-lookup"><span data-stu-id="bdf62-106">This topic describes known issues in Microsoft Excel that you might encounter in XLL development.</span></span>
  
## <a name="unregistering-xll-commands-and-functions"></a><span data-ttu-id="bdf62-107">注销 XLL 命令和函数</span><span class="sxs-lookup"><span data-stu-id="bdf62-107">Unregistering XLL Commands and Functions</span></span>

<span data-ttu-id="bdf62-108">当 XLL 注册函数或命令时，Excel为资源创建一个新名称，并关联对 DLL 函数的引用和该名称。</span><span class="sxs-lookup"><span data-stu-id="bdf62-108">When an XLL registers a function or command, Excel creates a new name for the resource and associates a reference to the DLL function with that name.</span></span> <span data-ttu-id="bdf62-109">该名称取自 [xlfRegister](xlfregister-form-1.md)函数的第四个参数 *pxFunctionText。*</span><span class="sxs-lookup"><span data-stu-id="bdf62-109">The name is taken from the fourth argument,  *pxFunctionText*  , of the [xlfRegister](xlfregister-form-1.md) function.</span></span> <span data-ttu-id="bdf62-110">此名称在用于管理工作表名称的正常对话框中隐藏。</span><span class="sxs-lookup"><span data-stu-id="bdf62-110">This name is hidden from the normal dialog boxes for managing worksheet names.</span></span> <span data-ttu-id="bdf62-111">若要取消注册函数或命令，必须使用 [xlfSetName](xlfsetname.md) 函数删除名称，传递名称但不传递定义。</span><span class="sxs-lookup"><span data-stu-id="bdf62-111">To unregister a function or command, you must delete the name by using the [xlfSetName](xlfsetname.md) function, passing the name but not passing a definition.</span></span> <span data-ttu-id="bdf62-112">但是，Bug 会阻止此操作从"函数向导"列表中删除名称。</span><span class="sxs-lookup"><span data-stu-id="bdf62-112">However, a bug prevents this from removing the name from the Function Wizard lists.</span></span> 
  
## <a name="argument-description-string-truncation-in-the-function-wizard"></a><span data-ttu-id="bdf62-113">参数说明 函数向导中的字符串截断</span><span class="sxs-lookup"><span data-stu-id="bdf62-113">Argument Description String Truncation in the Function Wizard</span></span>

<span data-ttu-id="bdf62-114">*pxArgumentHelp1* 参数和 **xlfRegister** 函数的所有后续参数是对应于 XLL 函数参数的可选字符串。</span><span class="sxs-lookup"><span data-stu-id="bdf62-114">The  *pxArgumentHelp1*  parameter and all subsequent parameters of the **xlfRegister** function are optional strings that correspond to the arguments of the XLL function.</span></span> <span data-ttu-id="bdf62-115">"函数向导"会显示这些参数，以在参数构造对话框中提供帮助。</span><span class="sxs-lookup"><span data-stu-id="bdf62-115">The Function Wizard displays these to provide help in the argument construction dialog box.</span></span> <span data-ttu-id="bdf62-116">有时Excel对话框显示最后一个参数时，该字符串会截断一个或两个字符。</span><span class="sxs-lookup"><span data-stu-id="bdf62-116">Sometimes Excel truncates the string that corresponds to the final argument by one or two characters when displaying it in the dialog box.</span></span> <span data-ttu-id="bdf62-117">通过将其他"空字符串"添加为函数注册的最后一个"参数帮助"参数，可以避免这一点。</span><span class="sxs-lookup"><span data-stu-id="bdf62-117">You can avoid this by adding an additional "empty string" as the last "argument help" parameter of your function registration.</span></span>
  
## <a name="binary-name-scope-limitation"></a><span data-ttu-id="bdf62-118">二进制名称范围限制</span><span class="sxs-lookup"><span data-stu-id="bdf62-118">Binary Name Scope Limitation</span></span>

<span data-ttu-id="bdf62-119">只有当创建时处于活动状态的工作表再次处于活动状态时，才能检索二进制名称及其数据。</span><span class="sxs-lookup"><span data-stu-id="bdf62-119">Binary names and their data can be retrieved only when the worksheet that was active at the time they were created is again active.</span></span> <span data-ttu-id="bdf62-120">由于工作表函数无法激活工作簿中的工作表 (只有命令才能) ，因此二进制名称的应用程序非常有限。</span><span class="sxs-lookup"><span data-stu-id="bdf62-120">Because worksheet functions cannot activate worksheets within a workbook (only commands can do this), applications of binary names are very limited.</span></span> <span data-ttu-id="bdf62-121">例如，如果你有一个仅从特定工作表调用的命令，可以使用二进制名称来存储与命令相关的数据。</span><span class="sxs-lookup"><span data-stu-id="bdf62-121">If you have a command that is only invoked from a particular worksheet, for example, you could use a binary name to store command-related data.</span></span>
  
## <a name="xlset-and-workbooks-with-array-formulas"></a><span data-ttu-id="bdf62-122">xlSet 和包含数组公式的工作簿</span><span class="sxs-lookup"><span data-stu-id="bdf62-122">xlSet and Workbooks with Array Formulas</span></span>

<span data-ttu-id="bdf62-123">在 Excel 2003 及更早版本中，如果尝试将值分配给非活动工作表（活动工作表上的等效区域包含数组公式）上的区域，[则 xlSet](xlset.md)函数将失败。</span><span class="sxs-lookup"><span data-stu-id="bdf62-123">In Excel 2003 and earlier versions, the [xlSet function](xlset.md) fails if you try to assign values to a range on a worksheet that is not the active worksheet, where the equivalent range on the active sheet contains an array formula.</span></span> <span data-ttu-id="bdf62-124">在这种情况下，Excel消息"您不能更改数组的一部分"。</span><span class="sxs-lookup"><span data-stu-id="bdf62-124">In this case, Excel displays the message "You cannot change part of an array."</span></span> <span data-ttu-id="bdf62-125">2007 年 10 Excel修复了这种情况。</span><span class="sxs-lookup"><span data-stu-id="bdf62-125">This was fixed in Excel 2007.</span></span> 
  
## <a name="circular-references-are-tolerated-in-data-tables"></a><span data-ttu-id="bdf62-126">数据表中允许循环引用</span><span class="sxs-lookup"><span data-stu-id="bdf62-126">Circular References are Tolerated in Data Tables</span></span>

<span data-ttu-id="bdf62-127">Excel数据表所基于的计算引用表本身中的某些内容，则当前不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="bdf62-127">Excel currently does not raise an error if the calculation that a data table is based on refers to something in the table itself.</span></span> <span data-ttu-id="bdf62-128">此方案不太可能出现，但创建或修改用于计算数据表值的公式时应谨慎。</span><span class="sxs-lookup"><span data-stu-id="bdf62-128">As unlikely as this scenario might be, you should be careful when you are creating or modifying formulas that are used to calculate data table values.</span></span>
  
## <a name="converting-an-integer-xloper12-to-an-xloper"></a><span data-ttu-id="bdf62-129">将整数 XLOPER12 转换为 XLOPER</span><span class="sxs-lookup"><span data-stu-id="bdf62-129">Converting an Integer XLOPER12 to an XLOPER</span></span>

<span data-ttu-id="bdf62-130">由于整数类型 **xltypeInt** 是 **XLOPER12** 数据类型 中的 32 位有符号整数，但它在 **XLOPER** 数据类型 中只是一个 16 位有符号整数，因此某些整数 **XLOPER12** 值不能包含在整数 **XLOPER** 中。</span><span class="sxs-lookup"><span data-stu-id="bdf62-130">Because the integer type **xltypeInt** is a 32-bit signed integer in the **XLOPER12** data type, but it is only a 16-bit signed integer in the **XLOPER** data type, it is possible that some integer **XLOPER12** values cannot be contained in an integer **XLOPER**.</span></span> <span data-ttu-id="bdf62-131">在Excel转换此类型时，它会通过将此类型转换为浮点 **xltypeNum** **XLOPER** 来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="bdf62-131">Where Excel converts this type internally, it gets around this problem by converting the type to a floating-point **xltypeNum** **XLOPER**.</span></span>
  
<span data-ttu-id="bdf62-132">Framework [XLOper12ToXLOper](xloper12toxloper.md)函数反映此行为，以与内部Excel一。</span><span class="sxs-lookup"><span data-stu-id="bdf62-132">The Framework [XLOper12ToXLOper](xloper12toxloper.md) function mirrors this behavior to be consistent with Excel internally.</span></span> <span data-ttu-id="bdf62-133">调用此函数时，不应假定返回的 **XLOPER** 始终为 **xltypeInt**;如果 **my_xloper.val.w** 的类型为 **xltypeNum，** 则读取 **my_xloper** 会提供 false 值。</span><span class="sxs-lookup"><span data-stu-id="bdf62-133">When you call this function, you should not assume that the returned **XLOPER** will always be **xltypeInt**; reading **my_xloper.val.w** gives a false value if the **my_xloper** type is **xltypeNum**.</span></span>
  
## <a name="returning-xloper-or-xloper12-by-modifying-arguments-in-place"></a><span data-ttu-id="bdf62-134">通过就地修改参数返回 XLOPER 或 XLOPER12</span><span class="sxs-lookup"><span data-stu-id="bdf62-134">Returning XLOPER or XLOPER12 by Modifying Arguments in Place</span></span>

<span data-ttu-id="bdf62-135">Excel通过就地修改参数来注册返回 **XLOPER** 或 **XLOPER12** 的函数。</span><span class="sxs-lookup"><span data-stu-id="bdf62-135">Excel permits the registration of functions that return an **XLOPER** or **XLOPER12** by modifying an argument in place.</span></span> <span data-ttu-id="bdf62-136">但是，如果 **XLOPER** /  **XLOPER12** 参数指向内存，并且指针随后被 DLL 函数的返回值覆盖，Excel内存。</span><span class="sxs-lookup"><span data-stu-id="bdf62-136">However, if an **XLOPER**/ **XLOPER12** argument points to memory, and the pointer is then overwritten by the return value of the DLL function, Excel can leak memory.</span></span> <span data-ttu-id="bdf62-137">Excel不显示错误，但最终可能会崩溃。</span><span class="sxs-lookup"><span data-stu-id="bdf62-137">Excel does not display an error, but it might eventually crash.</span></span> <span data-ttu-id="bdf62-138">此外，如果 DLL 为返回值分配了内存，Excel可能会尝试释放该内存，这可能会导致应用程序立即崩溃。</span><span class="sxs-lookup"><span data-stu-id="bdf62-138">Also, if the DLL allocated memory for the return value, Excel might try to free that memory, which could cause an immediate application crash.</span></span> <span data-ttu-id="bdf62-139">因此，不应就地 **修改** /  **XLOPER XLOPER12** 参数。</span><span class="sxs-lookup"><span data-stu-id="bdf62-139">Therefore, you should not modify **XLOPER**/ **XLOPER12** arguments in place.</span></span> <span data-ttu-id="bdf62-140">所有 **XLOPER** 或 **XLOPER12** 参数应严格视为只读。</span><span class="sxs-lookup"><span data-stu-id="bdf62-140">All **XLOPER** or **XLOPER12** arguments should be treated as strictly read-only.</span></span> 
  
<span data-ttu-id="bdf62-141">有关更多信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf62-141">For more information, see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bdf62-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdf62-142">See also</span></span>



[<span data-ttu-id="bdf62-143">XLOper12ToXLOper</span><span class="sxs-lookup"><span data-stu-id="bdf62-143">XLOper12ToXLOper</span></span>](xloper12toxloper.md)


[<span data-ttu-id="bdf62-144">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="bdf62-144">Developing Excel XLLs</span></span>](developing-excel-xlls.md)
  
[<span data-ttu-id="bdf62-145">Excel XLL SDK API 函数引用</span><span class="sxs-lookup"><span data-stu-id="bdf62-145">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)
  
[<span data-ttu-id="bdf62-146">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="bdf62-146">Memory Management in Excel</span></span>](memory-management-in-excel.md)

