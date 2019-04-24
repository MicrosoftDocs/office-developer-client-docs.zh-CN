---
title: 从 DLL 或 XLL 调用 Excel
manager: soliver
ms.date: 08/22/2018
ms.audience: Developer
ms.topic: overview
keywords:
- 对话框 [excel 2007], 调用 excel 命令,DLL [Excel 2007], 调用 Excel,将参数传递到 C API 函数 [Excel 2007],命令 [Excel 2007], 使用对话框进行调用,命令 [Excel 2007], 可通过 DLL/XLL 访问,Excel4 函数 [Excel 2007],Excel12 函数 [Excel 2007],XLCallVer 函数 [Excel 2007],operRes 参数 [Excel 2007],函数 [Excel 2007], 可通过 DLL/XLL 进行访问,Excel12v 函数 [Excel 2007],仅 DLL 函数 [Excel 2007],C API [Excel 2007], 传递参数,参数计数 [Excel 2007],命令 [Excel 2007], 调用国际版本,仅 DLL 命令 [Excel 2007],国际版本 [Excel 2007], 调用函数和命令,XLL [Excel 2007], 调用 Excel,Excel 4v 函数 [Excel 2007],xlfn 参数 [Excel 2007],函数 [Excel 2007], 调用国际版本
ms.assetid: 616e3def-e4ec-4f3c-bc65-3b92710da1e6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: 8f2b63ba84b0a78bbf317c284913a8ec0986436f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304156"
---
# <a name="calling-into-excel-from-the-dll-or-xll"></a><span data-ttu-id="d78a6-104">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="d78a6-104">Calling into Excel from the DLL or XLL</span></span>

<span data-ttu-id="d78a6-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d78a6-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d78a6-106">借助 Microsoft Excel，DLL 可访问内置的 Excel 命令、工作表函数和宏表函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-106">Microsoft Excel enables your DLL to access built-in Excel commands, worksheet functions, and macro sheet functions.</span></span> <span data-ttu-id="d78a6-107">可按两种方式使用它们：通过从 Visual Basic for Applications (VBA) 调用的 DLL 命令和函数，以及通过 Excel 直接调用的已注册的 XLL 命令和函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-107">These are available both from DLL commands and functions called from Visual Basic for Applications (VBA), and from registered XLL commands and functions called directly by Excel.</span></span>
  
## <a name="excel4-excel4v-excel12-and-excel12v-functions"></a><span data-ttu-id="d78a6-108">Excel4、Excel4v、Excel12 和 Excel12v 函数</span><span class="sxs-lookup"><span data-stu-id="d78a6-108">Excel4, Excel4v, Excel12, and Excel12v Functions</span></span>

<span data-ttu-id="d78a6-109">借助 Excel，DLL 可通过回调函数 [Excel4](excel4-excel12.md)、[Excel4v](excel4v-excel12v.md)、[Excel12](excel4-excel12.md) 和 [Excel12v](excel4v-excel12v.md) 访问命令和函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-109">Excel enables your DLL to access the commands and functions through the callback functions [Excel4](excel4-excel12.md), [Excel4v](excel4v-excel12v.md), [Excel12](excel4-excel12.md), and [Excel12v](excel4v-excel12v.md).</span></span>
  
<span data-ttu-id="d78a6-110">Excel 版本 4 中引入了 **Excel4** 和 **Excel4v** 函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-110">The **Excel4** and **Excel4v** functions were introduced in Excel version 4.</span></span> <span data-ttu-id="d78a6-111">它们适用于 **XLOPER** 数据结构。</span><span class="sxs-lookup"><span data-stu-id="d78a6-111">They work with the **XLOPER** data structure.</span></span> <span data-ttu-id="d78a6-112">Excel 2007 引入了两个新的回调函数 **Excel12** 和 **Excel12v**，它们适用于 **XLOPER12** 数据结构。</span><span class="sxs-lookup"><span data-stu-id="d78a6-112">Excel 2007 introduced two new callback functions, **Excel12** and **Excel12v**, which work with the **XLOPER12** data structure.</span></span> <span data-ttu-id="d78a6-113">**Excel4** 和 **Excel4v** 函数由 Xlcall32.lib 库导出，后者必须包含在 DLL 或 XLL 项目中。</span><span class="sxs-lookup"><span data-stu-id="d78a6-113">The **Excel4** and **Excel4v** functions are exported by the library Xlcall32.lib, which must be included in your DLL or XLL project.</span></span> <span data-ttu-id="d78a6-114">**Excel12** 和 **Excel12v** 包含在 SDK C++ 源文件 Xlcall.cpp 中；如果想要通过 **XLOPER12** 结构访问 Excel 功能，则必须在项目中包含此文件。</span><span class="sxs-lookup"><span data-stu-id="d78a6-114">**Excel12** and **Excel12v** are included in the SDK C++ source file Xlcall.cpp, which must be included in your project if you want to access Excel functionality by using **XLOPER12** structures.</span></span> 
  
<span data-ttu-id="d78a6-115">以下代码显示了上述 4 个函数的函数原型。</span><span class="sxs-lookup"><span data-stu-id="d78a6-115">The following code shows the function prototypes for these four functions.</span></span> <span data-ttu-id="d78a6-116">前三个参数相同，只是第二个参数是一个指针，它同时指向第一对中的 **XLOPER** 和第二对中的 **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="d78a6-116">The first three arguments are the same except that the second argument is a pointer to an **XLOPER** in the first pair and a pointer to an **XLOPER12** in the second pair.</span></span> <span data-ttu-id="d78a6-117">**Excel4** 和 **Excel12** 中的调用约定是 **_cdecl**，它允许变量参数列表。</span><span class="sxs-lookup"><span data-stu-id="d78a6-117">The calling convention is **_cdecl** in **Excel4** and **Excel12** to permit the variable argument lists.</span></span> <span data-ttu-id="d78a6-118">省略号表示指向 **Excel4** 的 **XLOPER** 值和 **Excel12** 的 **XLOPER12** 值的指针。</span><span class="sxs-lookup"><span data-stu-id="d78a6-118">The ellipsis represents pointers to **XLOPER** values for **Excel4** and **XLOPER12** values for **Excel12**.</span></span> <span data-ttu-id="d78a6-119">指针数量等于 _count_ 参数的值。</span><span class="sxs-lookup"><span data-stu-id="d78a6-119">The number of pointers equals the value of the  _count_ parameter.</span></span> 
  
<span data-ttu-id="d78a6-120">**Excel 的所有版本**</span><span class="sxs-lookup"><span data-stu-id="d78a6-120">**All versions of Excel**</span></span>
  
 `int _cdecl Excel4(int xlfn, LPXLOPER operRes, int count,... );`
  
 `int pascal Excel4v(int xlfn, LPXLOPER operRes, int count, LPXLOPER opers[]);`
  
<span data-ttu-id="d78a6-121">**自 Excel 2007 起**</span><span class="sxs-lookup"><span data-stu-id="d78a6-121">**Starting in Excel 2007**</span></span>
  
 `int _cdecl Excel12(int xlfn, LPXLOPER12 operRes, int count,... );`
  
 `int pascal Excel12v(int xlfn, LPXLOPER12 operRes, int count, LPXLOPER12 opers[]);`
  
<span data-ttu-id="d78a6-122">要让 DLL 能够调用 **Excel4**、**Excel4v**、**Excel12** 或 **Excel12v**，Excel 必须将控制权传递给 DLL。</span><span class="sxs-lookup"><span data-stu-id="d78a6-122">For the DLL to be able to call **Excel4**, **Excel4v**, **Excel12**, or **Excel12v**, Excel must pass control to the DLL.</span></span> <span data-ttu-id="d78a6-123">这意味着，仅可在以下情况下调用 C API 回调：</span><span class="sxs-lookup"><span data-stu-id="d78a6-123">This means that these C API callbacks can be called only in the following scenarios:</span></span>
  
- <span data-ttu-id="d78a6-124">从 Excel 直接调用或通过 VBA 调用的 XLL 命令内部。</span><span class="sxs-lookup"><span data-stu-id="d78a6-124">From within an XLL command that Excel has called directly or via VBA.</span></span>
    
- <span data-ttu-id="d78a6-125">从 Excel 直接调用或通过 VBA 调用的 XLL 工作表或宏表函数内部。</span><span class="sxs-lookup"><span data-stu-id="d78a6-125">From within an XLL worksheet or macro sheet function that Excel has called directly or via VBA.</span></span>
    
<span data-ttu-id="d78a6-126">不可在以下情况下调用 Excel C API：</span><span class="sxs-lookup"><span data-stu-id="d78a6-126">You cannot call the Excel C API in the following scenarios:</span></span>
  
- <span data-ttu-id="d78a6-127">通过操作系统事件（例如，通过 [DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain) 函数）。</span><span class="sxs-lookup"><span data-stu-id="d78a6-127">From an operating system event (for example, from the [DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain) function).</span></span> 
    
- <span data-ttu-id="d78a6-128">通过 DLL 创建的后台线程。</span><span class="sxs-lookup"><span data-stu-id="d78a6-128">From a background thread that your DLL created.</span></span>
    
### <a name="return-values"></a><span data-ttu-id="d78a6-129">返回值</span><span class="sxs-lookup"><span data-stu-id="d78a6-129">Return values</span></span>

<span data-ttu-id="d78a6-130">上述 4 个函数均返回一个整数值，它通知调用方是否成功调用函数或命令。</span><span class="sxs-lookup"><span data-stu-id="d78a6-130">All four of these functions return an integer value that informs the caller whether the function or command was called successfully.</span></span> <span data-ttu-id="d78a6-131">返回的值可为下述任一值：</span><span class="sxs-lookup"><span data-stu-id="d78a6-131">The values returned can be any of the following:</span></span>
  
|<span data-ttu-id="d78a6-132">**返回值**</span><span class="sxs-lookup"><span data-stu-id="d78a6-132">**Return value**</span></span>|<span data-ttu-id="d78a6-133">**在 Xlcall.h 中定义为**</span><span class="sxs-lookup"><span data-stu-id="d78a6-133">**Defined in Xlcall.h as**</span></span>|<span data-ttu-id="d78a6-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="d78a6-134">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d78a6-135">0</span><span class="sxs-lookup"><span data-stu-id="d78a6-135">0%</span></span>  <br/> |<span data-ttu-id="d78a6-136">**xlretSuccess**</span><span class="sxs-lookup"><span data-stu-id="d78a6-136">**xlretSuccess**</span></span> <br/> |<span data-ttu-id="d78a6-137">函数或命令已成功执行。</span><span class="sxs-lookup"><span data-stu-id="d78a6-137">The function or command executed successfully.</span></span> <span data-ttu-id="d78a6-138">这并非表示操作不出错。</span><span class="sxs-lookup"><span data-stu-id="d78a6-138">This does not mean that the execution was error free.</span></span> <span data-ttu-id="d78a6-139">例如，调用 **FIND** 函数时，即使求值得到 **#VALUE!**，**Excel4** 也可能返回 **xlretSuccess**，</span><span class="sxs-lookup"><span data-stu-id="d78a6-139">For example, **Excel4** could return **xlretSuccess** when calling the function **FIND**, even though it evaluated to **#VALUE!**</span></span> <span data-ttu-id="d78a6-140">原因是找不到搜索文本。</span><span class="sxs-lookup"><span data-stu-id="d78a6-140">because the search text could not be found.</span></span> <span data-ttu-id="d78a6-141">应检查所返回的 **XLOPER/XLOPER12** 的类型和值（若可能）。</span><span class="sxs-lookup"><span data-stu-id="d78a6-141">You should inspect the type and value of the returned **XLOPER/XLOPER12** where this is a possibility.</span></span>  <br/> |
|<span data-ttu-id="d78a6-142">1</span><span class="sxs-lookup"><span data-stu-id="d78a6-142">-1</span></span>  <br/> |<span data-ttu-id="d78a6-143">**xlretAbort**</span><span class="sxs-lookup"><span data-stu-id="d78a6-143">**xlretAbort**</span></span> <br/> |<span data-ttu-id="d78a6-144">用户已通过单击“**取消**”按钮或按 Esc 键停止命令宏。</span><span class="sxs-lookup"><span data-stu-id="d78a6-144">A command macro was stopped by the user clicking the **CANCEL** button or pressing the ESC key.</span></span>  <br/> |
|<span data-ttu-id="d78a6-145">2</span><span class="sxs-lookup"><span data-stu-id="d78a6-145">2.</span></span>  <br/> |<span data-ttu-id="d78a6-146">**xlretInvXlfn**</span><span class="sxs-lookup"><span data-stu-id="d78a6-146">**xlretInvXlfn**</span></span> <br/> |<span data-ttu-id="d78a6-147">所提供的函数或命令代码无效。</span><span class="sxs-lookup"><span data-stu-id="d78a6-147">The supplied function or command code is not valid.</span></span> <span data-ttu-id="d78a6-148">当调用函数无权调用函数或命令时，可能出现此错误。</span><span class="sxs-lookup"><span data-stu-id="d78a6-148">This error can occur when the calling function does not have permission to call the function or command.</span></span> <span data-ttu-id="d78a6-149">例如，工作表函数无法调用宏表信息函数或命令函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-149">For example, a worksheet function cannot call a macro sheet information function or a command function.</span></span>  <br/> |
|<span data-ttu-id="d78a6-150">4</span><span class="sxs-lookup"><span data-stu-id="d78a6-150">4.</span></span>  <br/> |<span data-ttu-id="d78a6-151">**xlretInvCount**</span><span class="sxs-lookup"><span data-stu-id="d78a6-151">**xlretInvCount**</span></span> <br/> |<span data-ttu-id="d78a6-152">调用中提供的参数数目不正确。</span><span class="sxs-lookup"><span data-stu-id="d78a6-152">The number of arguments supplied in the call is not correct.</span></span>  <br/> |
|<span data-ttu-id="d78a6-153">8</span><span class="sxs-lookup"><span data-stu-id="d78a6-153">8.</span></span>  <br/> |<span data-ttu-id="d78a6-154">**xlretInvXloper**</span><span class="sxs-lookup"><span data-stu-id="d78a6-154">**xlretInvXloper**</span></span> <br/> |<span data-ttu-id="d78a6-155">一个或多个参数 **XLOPER** 或 **XLOPER12** 值构建或填充错误。</span><span class="sxs-lookup"><span data-stu-id="d78a6-155">One or more of the argument **XLOPER** or **XLOPER12** values are not properly formed or populated.</span></span>  <br/> |
|<span data-ttu-id="d78a6-156">16</span><span class="sxs-lookup"><span data-stu-id="d78a6-156">1.6</span></span>  <br/> |<span data-ttu-id="d78a6-157">**xlretStackOvfl**</span><span class="sxs-lookup"><span data-stu-id="d78a6-157">**xlretStackOvfl**</span></span> <br/> |<span data-ttu-id="d78a6-158">Excel 检测到存在操作可能溢出其堆栈的风险，因此未调用函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-158">Excel detected a risk that the operation might overflow its stack and, therefore, did not call the function.</span></span>  <br/> |
|<span data-ttu-id="d78a6-159">32</span><span class="sxs-lookup"><span data-stu-id="d78a6-159">3.2</span></span>  <br/> |<span data-ttu-id="d78a6-160">**xlretFailed**</span><span class="sxs-lookup"><span data-stu-id="d78a6-160">**xlretFailed**</span></span> <br/> |<span data-ttu-id="d78a6-161">命令或函数因任一其他返回值未描述的原因而失败。</span><span class="sxs-lookup"><span data-stu-id="d78a6-161">The command or function failed for a reason not described by one of the other return values.</span></span> <span data-ttu-id="d78a6-162">例如，需要过多内存的操作会失败且出现此错误。</span><span class="sxs-lookup"><span data-stu-id="d78a6-162">An operation that would require too much memory, for example, would fail with this error.</span></span> <span data-ttu-id="d78a6-163">在尝试通过 [xlCoerce](xlcoerce.md) 函数将较大型引用转换为 **xltypeMulti** 数组时，可能发生此问题。</span><span class="sxs-lookup"><span data-stu-id="d78a6-163">This could happen during an attempt to convert a very large reference to an **xltypeMulti** array by using the [xlCoerce](xlcoerce.md) function.</span></span>  <br/> |
|<span data-ttu-id="d78a6-164">64</span><span class="sxs-lookup"><span data-stu-id="d78a6-164">6.4</span></span>  <br/> |<span data-ttu-id="d78a6-165">**xlretUncalced**</span><span class="sxs-lookup"><span data-stu-id="d78a6-165">**xlretUncalced**</span></span> <br/> |<span data-ttu-id="d78a6-166">操作尝试检索未计算的单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d78a6-166">The operation attempted to retrieve the value of an uncalculated cell.</span></span> <span data-ttu-id="d78a6-167">要在 Excel 中保留重算完整性，工作表函数不可执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d78a6-167">To preserve recalculation integrity in Excel, worksheet functions are not permitted to do this.</span></span> <span data-ttu-id="d78a6-168">但是，注册为宏表函数的 XLL 命令和函数可访问未计算的单元格值。</span><span class="sxs-lookup"><span data-stu-id="d78a6-168">However, XLL commands and functions registered as macro sheet functions are permitted to access uncalculated cell values.</span></span>  <br/> |
|<span data-ttu-id="d78a6-169">128</span><span class="sxs-lookup"><span data-stu-id="d78a6-169">Default: 128</span></span>  <br/> |<span data-ttu-id="d78a6-170">**xlretNotThreadSafe**</span><span class="sxs-lookup"><span data-stu-id="d78a6-170">**xlretNotThreadSafe**</span></span> <br/> |<span data-ttu-id="d78a6-171">（自 Excel 2007 起）注册为线程安全的 XLL 工作表函数尝试调用非线程安全的 C API 函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-171">(Starting in Excel 2007) An XLL worksheet function registered as thread safe attempted to call a C API function that is not thread safe.</span></span> <span data-ttu-id="d78a6-172">例如，线程安全函数无法调用 XLM 函数 **xlfGetCell**。</span><span class="sxs-lookup"><span data-stu-id="d78a6-172">For example, a thread-safe function cannot call the XLM function **xlfGetCell**.</span></span>  <br/> |
|<span data-ttu-id="d78a6-173">256</span><span class="sxs-lookup"><span data-stu-id="d78a6-173">validAccesses: 256</span></span>  <br/> |<span data-ttu-id="d78a6-174">**xlRetInvAsynchronousContext**</span><span class="sxs-lookup"><span data-stu-id="d78a6-174">**xlRetInvAsynchronousContext**</span></span> <br/> |<span data-ttu-id="d78a6-175">（自 Excel 2010 起）异步函数句柄无效。</span><span class="sxs-lookup"><span data-stu-id="d78a6-175">(Starting in Excel 2010) The asynchronous function handle is invalid.</span></span>  <br/> |
|<span data-ttu-id="d78a6-176">512</span><span class="sxs-lookup"><span data-stu-id="d78a6-176">5.12</span></span>  <br/> |<span data-ttu-id="d78a6-177">**xlretNotClusterSafe**</span><span class="sxs-lookup"><span data-stu-id="d78a6-177">**xlretNotClusterSafe**</span></span> <br/> |<span data-ttu-id="d78a6-178">（自 Excel 2010 起）群集上不支持此调用。</span><span class="sxs-lookup"><span data-stu-id="d78a6-178">(Starting in Excel 2010) The call is not supported on clusters.</span></span>  <br/> |
   
<span data-ttu-id="d78a6-179">如果函数返回表中的某一失败值（即，不返回 **xlretSuccess**），则 **XLOPER** 或 **XLOPER12** 返回值也将设置为 **#VALUE!**。</span><span class="sxs-lookup"><span data-stu-id="d78a6-179">If the function returns one of the failure values in the table (that is, it does not return **xlretSuccess**), the **XLOPER** or **XLOPER12** return value will also be set to **#VALUE!**.</span></span> <span data-ttu-id="d78a6-180">在某些情况下，检查此项可能足以测试是否成功，但应注意，调用可同时返回 **xlretSuccess** 和 **#VALUE!**。</span><span class="sxs-lookup"><span data-stu-id="d78a6-180">In certain circumstances, checking for this might be a sufficient test of success, but you should note that a call can return both **xlretSuccess** and **#VALUE!**.</span></span>
  
<span data-ttu-id="d78a6-181">如果对 C API 的调用导致 **xlretUncalced** 或 **xlretAbort**，则 DLL 或 XLL 代码应将控制权归还给 Excel，然后再进行任何其他 C API 调用（而不是调用 [xlfree](xlfree.md) 函数来释放 **XLOPER** 和 **XLOPER12** 值中由 Excel 分配的内存资源。</span><span class="sxs-lookup"><span data-stu-id="d78a6-181">If a call to the C API results in either **xlretUncalced** or **xlretAbort**, your DLL or XLL code should return control to Excel before making any other C API calls (other than calls to the [xlfree](xlfree.md) function to release Excel-allocated memory resources in **XLOPER** and **XLOPER12** values).</span></span> 
  
### <a name="command-or-function-enumeration-argument-xlfn"></a><span data-ttu-id="d78a6-182">命令或函数枚举参数：xlfn</span><span class="sxs-lookup"><span data-stu-id="d78a6-182">Command or Function Enumeration Argument: xlfn</span></span>

<span data-ttu-id="d78a6-183">_xlfn_ 参数是回调函数的第一个参数，它是一个 32 位带符号整数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-183">The  _xlfn_ argument is the first argument to the callback functions and is a 32-bit signed integer.</span></span> <span data-ttu-id="d78a6-184">其值应为 SDK 头文件 Xlcall.h 中定义的函数或命令枚举之一，如下例中所示。</span><span class="sxs-lookup"><span data-stu-id="d78a6-184">Its value should be one of the function or command enumerations defined in the SDK header file Xlcall.h, as shown in the following example.</span></span> 
  
```cs
// Excel function numbers. 
#define xlfCount 0
#define xlfIsna 2
#define xlfIserror 3
#define xlfSum 4
#define xlfAverage 5
#define xlfMin 6
#define xlfMax 7
#define xlfRow 8
#define xlfColumn 9
#define xlfNa 10
...
// Excel command numbers. 
#define xlcBeep (0 | xlCommand)
#define xlcOpen (1 | xlCommand)
#define xlcOpenLinks (2 | xlCommand)
#define xlcCloseAll (3 | xlCommand)
#define xlcSave (4 | xlCommand)
#define xlcSaveAs (5 | xlCommand)
#define xlcFileDelete (6 | xlCommand)
#define xlcPageSetup (7 | xlCommand)
#define xlcPrint (8 | xlCommand)
#define xlcPrinterSetup (9 | xlCommand)
...
```

<span data-ttu-id="d78a6-185">所有工作表和宏表函数均介于 0 (**xlfCount**) 至 0x0fff 十六进制数之间的范围，但 Excel 2013 中分配的最大数为 547 小数、0x0223 十六进制数 (**xlfFloor_precise**)。</span><span class="sxs-lookup"><span data-stu-id="d78a6-185">All worksheet and macro sheet functions are in the range from 0 (**xlfCount**) through 0x0fff hexadecimal, although the highest assigned number in Excel 2013 is 547 decimal, 0x0223 hexadecimal (**xlfFloor_precise**).</span></span>
  
<span data-ttu-id="d78a6-186">所有命令函数均介于 0x8000 十六进制数 (**xlcBeep**) 至 0x8fff 十六进制数，但 Excel 2013 中分配的最大数为 0x8328 十六进制数 (**xlcHideallInkannots**)。</span><span class="sxs-lookup"><span data-stu-id="d78a6-186">All command functions are in the range from 0x8000 hexadecimal (**xlcBeep**) through 0x8fff hexadecimal, although the highest assigned number in Excel 2013 is 0x8328 hexadecimal (**xlcHideallInkannots**).</span></span> <span data-ttu-id="d78a6-187">这些在头文件中定义为 `(n | xlCommand)`，其中 `n` 是大于等于 0 的小数，**xlCommand** 定义为 0x8000 十六进制数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-187">These are defined in the header file as  `(n | xlCommand)` where  `n` is a decimal number greater than or equal to 0 and **xlCommand** is defined as 0x8000 hexadecimal.</span></span> 
  
### <a name="invoking-excel-commands-that-use-dialog-boxes"></a><span data-ttu-id="d78a6-188">调用使用对话框的 Excel 命令</span><span class="sxs-lookup"><span data-stu-id="d78a6-188">Invoking Excel Commands that Use Dialog Boxes</span></span>

<span data-ttu-id="d78a6-189">一些命令代码与 Excel 中使用对话框的操作相对应。</span><span class="sxs-lookup"><span data-stu-id="d78a6-189">Some of the command codes correspond to actions in Excel that use dialog boxes.</span></span> <span data-ttu-id="d78a6-190">例如，**xlcFileDelete** 采用单一参数：文件名或掩码。</span><span class="sxs-lookup"><span data-stu-id="d78a6-190">For example, **xlcFileDelete** takes a single argument: a file name or mask.</span></span> <span data-ttu-id="d78a6-191">这可通过对话框进行调用，因此用户可取消或修改“删除”操作。</span><span class="sxs-lookup"><span data-stu-id="d78a6-191">This can be invoked with the dialog box so that the user has the opportunity to cancel or modify the delete operation.</span></span> <span data-ttu-id="d78a6-192">也可在不使用对话框的情况下调用它，此时删除一个或多个文件，但不进行任何后续交互，其中假定文件已存在且调用方具有相关权限。</span><span class="sxs-lookup"><span data-stu-id="d78a6-192">It can also be called without the dialog box, in which case the file or files are deleted without any further interaction, assuming they exist and the caller has permission.</span></span> <span data-ttu-id="d78a6-193">若要在其对话框形式中调用此类命令，则必须使用按位 OR 操作和 0x1000 (**xlPrompt**) 来组合命令枚举。</span><span class="sxs-lookup"><span data-stu-id="d78a6-193">To call such commands in their dialog box form, the command enumeration must be combined by using the bitwise OR operation with 0x1000 (**xlPrompt**).</span></span>
  
<span data-ttu-id="d78a6-194">以下代码示例删除了当前目录中与 mask my_data\*.bak 匹配的文件，仅在参数为 true 时显示对话框。</span><span class="sxs-lookup"><span data-stu-id="d78a6-194">The following code example deletes files in the current directory matching the mask my_data\*.bak, displaying a dialog box only if the argument is true.</span></span>
  
```cs
bool delete_my_backup_files(bool show_dialog)
{
    XLOPER12 xResult, xFilter;
    xFilter.xltype = xltypeStr;
    xFilter.val.str = L"\014my_data*.bak"; // String length: 14 octal
    int cmd;
    if(show_dialog)
        cmd = xlcFileDelete | xlPrompt;
    else
        cmd = xlcFileDelete;
// xResult should be Boolean TRUE if successful, in which
// case return true; otherwise, false.
    return (Excel12(cmd, &xResult, 1, &xFilter) == xlretSuccess
        && xResult.xltype == xltypeBool
        && xResult.val.xbool == 1);
}
```

### <a name="calling-functions-and-commands-in-international-versions"></a><span data-ttu-id="d78a6-195">在国际版本中调用函数和命令</span><span class="sxs-lookup"><span data-stu-id="d78a6-195">Calling Functions and Commands in International Versions</span></span>

<span data-ttu-id="d78a6-196">可配置 Excel，以按各种语言显示函数和 XLM 命令名称。</span><span class="sxs-lookup"><span data-stu-id="d78a6-196">You can configure Excel to display functions and XLM command names in a variety of languages.</span></span> <span data-ttu-id="d78a6-197">某些 C API 命令和函数对解释为函数或命令名称的字符串进行操作。</span><span class="sxs-lookup"><span data-stu-id="d78a6-197">Some C API commands and functions operate on strings that are interpreted as function or command names.</span></span> <span data-ttu-id="d78a6-198">例如，**xlcFormula** 采用要置于指定的单元格中的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-198">For example, **xlcFormula** takes a string argument that is intended to be placed in a specified cell.</span></span> <span data-ttu-id="d78a6-199">要使加载项适用于所有语言设置，可提供英语字符串名称并在函数或命令枚举中设置位数 0x2000 (**xlIntl**)。</span><span class="sxs-lookup"><span data-stu-id="d78a6-199">For your add-in to work with all language settings, you can supply the English string names and set the bit 0x2000 (**xlIntl**) in the function or command enumeration.</span></span>
  
<span data-ttu-id="d78a6-200">以下代码示例在活动工作表的单元格 A2 中放置 `=SUM(X1:X100)` 的等效项。</span><span class="sxs-lookup"><span data-stu-id="d78a6-200">The following code example places the equivalent of  `=SUM(X1:X100)` in cell A2 on the active sheet.</span></span> <span data-ttu-id="d78a6-201">请注意，它使用框架函数 **TempActiveRef** 来创建临时外部引用 **XLOPER**。</span><span class="sxs-lookup"><span data-stu-id="d78a6-201">Note that it uses the Framework function, **TempActiveRef**, to create a temporary external reference **XLOPER**.</span></span> <span data-ttu-id="d78a6-202">公式将按由区域设置确定的适当语言在 A2 中显示（如果语言为法语，则为 `=SOMME(X1:X100)`）。</span><span class="sxs-lookup"><span data-stu-id="d78a6-202">The formula will appear in A2 in the correct locale-determined language (for example,  `=SOMME(X1:X100)` if the language is French).</span></span> 
  
```cs
int WINAPI InternationlExample(void)
{
    XLOPER12 xSum, xResult;
    xSum.xltype = xltypeStr;
    xSum.val.str = L"\015=SUM(X1:X100)";
    Excel12(xlcFormula | xlIntl, &xResult, 2,
        &xSum, TempActiveRef(2,2,1,1));
    return 1;
}

```

> [!NOTE]
> <span data-ttu-id="d78a6-203">由于对 **Excel12** 的调用的结果不是必需的，则可传递 0 (NULL) 作为第二个参数，而不是传递 **xResult** 的地址。</span><span class="sxs-lookup"><span data-stu-id="d78a6-203">Because the result of the call to **Excel12** is not required, zero (NULL) could be passed as the second argument instead of the address of **xResult**.</span></span> <span data-ttu-id="d78a6-204">此内容将在下一部分中详细介绍。</span><span class="sxs-lookup"><span data-stu-id="d78a6-204">This is discussed more in the next section.</span></span> 
  
### <a name="dll-only-functions-and-commands"></a><span data-ttu-id="d78a6-205">仅 DLL 函数和命令</span><span class="sxs-lookup"><span data-stu-id="d78a6-205">DLL-Only Functions and Commands</span></span>

<span data-ttu-id="d78a6-206">Excel 支持少量仅可通过 DLL 或 XLL 访问的函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-206">Excel supports a small number of functions that are only accessible from a DLL or XLL.</span></span> <span data-ttu-id="d78a6-207">这些函数在头文件中定义为 `(n | xlSpecial)`，其中 `n` 是大于等于 0 的小数，`xlSpecial` 定义为 0x4000 十六进制数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-207">These are defined in the header file as  `(n | xlSpecial)` where  `n` is a decimal number greater than or equal to 0 and  `xlSpecial` is defined as 0x4000 hexadecimal.</span></span> <span data-ttu-id="d78a6-208">这些函数在下表中列出且记录在 [API 函数引用](excel-xll-sdk-api-function-reference.md)中。</span><span class="sxs-lookup"><span data-stu-id="d78a6-208">These functions are listed in the following table and documented in the [API Function Reference](excel-xll-sdk-api-function-reference.md).</span></span>
  
||||
|:-----|:-----|:-----|
|[<span data-ttu-id="d78a6-209">xlFree</span><span class="sxs-lookup"><span data-stu-id="d78a6-209">xlFree</span></span>](xlfree.md) <br/> |<span data-ttu-id="d78a6-210">0</span><span class="sxs-lookup"><span data-stu-id="d78a6-210">0%</span></span> | <span data-ttu-id="d78a6-211">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-211">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-212">释放由 Excel 分配的内存资源。</span><span class="sxs-lookup"><span data-stu-id="d78a6-212">Frees Excel-allocated memory resources.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-213">xlStack</span><span class="sxs-lookup"><span data-stu-id="d78a6-213">xlStack</span></span>](xlstack.md) <br/> |<span data-ttu-id="d78a6-214">1</span><span class="sxs-lookup"><span data-stu-id="d78a6-214">-1</span></span> | <span data-ttu-id="d78a6-215">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-215">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-216">返回 Excel 堆栈上的空闲空间。</span><span class="sxs-lookup"><span data-stu-id="d78a6-216">Returns the free space on the Excel stack.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-217">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="d78a6-217">xlCoerce</span></span>](xlcoerce.md) <br/> |<span data-ttu-id="d78a6-218">2</span><span class="sxs-lookup"><span data-stu-id="d78a6-218">2.</span></span> | <span data-ttu-id="d78a6-219">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-219">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-220">在 **XLOPER** 和 **XLOPER12** 类型之间转换</span><span class="sxs-lookup"><span data-stu-id="d78a6-220">Converts between **XLOPER** and **XLOPER12** types</span></span>  <br/> |
|[<span data-ttu-id="d78a6-221">xlSet</span><span class="sxs-lookup"><span data-stu-id="d78a6-221">xlSet</span></span>](xlset.md) <br/> |<span data-ttu-id="d78a6-222">3</span><span class="sxs-lookup"><span data-stu-id="d78a6-222">3.</span></span> | <span data-ttu-id="d78a6-223">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-223">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-224">提供用于设置单元格值的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="d78a6-224">Provides a fast method of setting cell values.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-225">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="d78a6-225">xlSheetId</span></span>](xlsheetid.md) <br/> |<span data-ttu-id="d78a6-226">4</span><span class="sxs-lookup"><span data-stu-id="d78a6-226">4.</span></span> | <span data-ttu-id="d78a6-227">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-227">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-228">从其内部 ID 获取工作表名称。</span><span class="sxs-lookup"><span data-stu-id="d78a6-228">Obtains a worksheet name from its internal ID.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-229">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="d78a6-229">xlSheetNm</span></span>](xlsheetnm.md) <br/> |<span data-ttu-id="d78a6-230">5</span><span class="sxs-lookup"><span data-stu-id="d78a6-230">5.</span></span> | <span data-ttu-id="d78a6-231">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-231">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-232">从其名称中获取工作表内部 ID。</span><span class="sxs-lookup"><span data-stu-id="d78a6-232">Obtains a worksheet internal ID from its name.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-233">xlAbort</span><span class="sxs-lookup"><span data-stu-id="d78a6-233">xlAbort</span></span>](xlabort.md) <br/> |<span data-ttu-id="d78a6-234">6</span><span class="sxs-lookup"><span data-stu-id="d78a6-234">6.</span></span> | <span data-ttu-id="d78a6-235">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-235">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-236">验证用户是否已单击“**取消**”按钮或按 Esc 键。</span><span class="sxs-lookup"><span data-stu-id="d78a6-236">Verifies whether the user clicked the **CANCEL** button or pressed the ESC key.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-237">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="d78a6-237">xlGetInst</span></span>](xlgetinst.md) <br/> |<span data-ttu-id="d78a6-238">7</span><span class="sxs-lookup"><span data-stu-id="d78a6-238">7.</span></span> | <span data-ttu-id="d78a6-239">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-239">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-240">获取 Excel 实例句柄。</span><span class="sxs-lookup"><span data-stu-id="d78a6-240">Gets the Excel instance handle.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-241">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="d78a6-241">xlGetHwnd</span></span>](xlgethwnd.md) <br/> |<span data-ttu-id="d78a6-242">8</span><span class="sxs-lookup"><span data-stu-id="d78a6-242">8.</span></span> | <span data-ttu-id="d78a6-243">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-243">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-244">获取 Excel 主窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="d78a6-244">Gets the Excel main window handle.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-245">xlGetName</span><span class="sxs-lookup"><span data-stu-id="d78a6-245">xlGetName</span></span>](xlgetname.md) <br/> |<span data-ttu-id="d78a6-246">9</span><span class="sxs-lookup"><span data-stu-id="d78a6-246">9.</span></span> | <span data-ttu-id="d78a6-247">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-247">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-248">获取 DLL 的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="d78a6-248">Gets the path and file name of the DLL.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-249">xlEnableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="d78a6-249">xlEnableXLMsgs</span></span>](xlenablexlmsgs.md) <br/> |<span data-ttu-id="d78a6-250">10</span><span class="sxs-lookup"><span data-stu-id="d78a6-250">1.0</span></span> | <span data-ttu-id="d78a6-251">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-251">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-252">此函数已弃用，因此无需再调用。</span><span class="sxs-lookup"><span data-stu-id="d78a6-252">This function is deprecated and no longer needs to be called.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-253">xlDisableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="d78a6-253">xlDisableXLMsgs</span></span>](xldisablexlmsgs.md) <br/> |<span data-ttu-id="d78a6-254">11</span><span class="sxs-lookup"><span data-stu-id="d78a6-254">1.1</span></span> | <span data-ttu-id="d78a6-255">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-255">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-256">此函数已弃用，因此无需再调用。</span><span class="sxs-lookup"><span data-stu-id="d78a6-256">This function is deprecated and no longer needs to be called.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-257">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="d78a6-257">xlDefineBinaryName</span></span>](xldefinebinaryname.md) <br/> |<span data-ttu-id="d78a6-258">12</span><span class="sxs-lookup"><span data-stu-id="d78a6-258">1.2</span></span> | <span data-ttu-id="d78a6-259">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-259">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-260">指定一个永久二进制存储名称。</span><span class="sxs-lookup"><span data-stu-id="d78a6-260">Defines a persistent binary storage name.</span></span>  <br/> |
|[<span data-ttu-id="d78a6-261">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="d78a6-261">xlGetBinaryName</span></span>](xlgetbinaryname.md) <br/> |<span data-ttu-id="d78a6-262">13</span><span class="sxs-lookup"><span data-stu-id="d78a6-262">1.3</span></span> | <span data-ttu-id="d78a6-263">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="d78a6-263">xlSpecial</span></span>  <br/> |<span data-ttu-id="d78a6-264">获取永久二进制存储名称的数据。</span><span class="sxs-lookup"><span data-stu-id="d78a6-264">Gets a persistent binary storage name's data.</span></span>  <br/> |
   
## <a name="return-value-xloperxloper12-operres"></a><span data-ttu-id="d78a6-265">返回值 XLOPER/XLOPER12：operRes</span><span class="sxs-lookup"><span data-stu-id="d78a6-265">Return value XLOPER/XLOPER12: operRes</span></span>

<span data-ttu-id="d78a6-266">_operRes_ 参数是回调的第二个参数，并且是一个指向 **XLOPER**（**Excel4** 和 **Excel4v**）或 **XLOPER12**（**Excel12** 和 **Excel12v**）的指针。</span><span class="sxs-lookup"><span data-stu-id="d78a6-266">The  _operRes_ argument is the second argument to the callbacks and is a pointer to an **XLOPER** (**Excel4** and **Excel4v**) or **XLOPER12** (**Excel12** and **Excel12v**).</span></span> <span data-ttu-id="d78a6-267">成功调用后，它包含函数或命令的返回值。</span><span class="sxs-lookup"><span data-stu-id="d78a6-267">After a successful call, it contains the return value of the function or command.</span></span> <span data-ttu-id="d78a6-268">如果无需返回值，则可将 **operRes** 设置为 0（NULL 指针）。</span><span class="sxs-lookup"><span data-stu-id="d78a6-268">**operRes** can be set to zero (NULL pointer) if no return value is required.</span></span> <span data-ttu-id="d78a6-269">已覆盖 **operRes** 的先前内容，因此在调用之前必须释放之前指向的所有内存，以避免内存泄露。</span><span class="sxs-lookup"><span data-stu-id="d78a6-269">The previous contents of **operRes** are overwritten so that any memory previously pointed to must be freed before to the call to avoid memory leaks.</span></span> 
  
<span data-ttu-id="d78a6-270">如果无法调用函数或命令（例如，在参数错误的情况下），**operRes** 设置为错误 **#VALUE!**。</span><span class="sxs-lookup"><span data-stu-id="d78a6-270">If the function or command cannot be called (for example, if the arguments are incorrect), **operRes** is set to the error **#VALUE!**.</span></span> <span data-ttu-id="d78a6-271">命令始终返回**布尔值**：如果成功，则返回 **TRUE**如果失败或用户取消此操作，则返回 **FALSE**。</span><span class="sxs-lookup"><span data-stu-id="d78a6-271">A command always returns **Boolean** **TRUE** if it is successful, or **FALSE** if it failed or the user canceled it.</span></span> 
  
## <a name="number-of-subsequent-arguments-count"></a><span data-ttu-id="d78a6-272">后续参数数量：count</span><span class="sxs-lookup"><span data-stu-id="d78a6-272">Number of Subsequent Arguments: count</span></span>

<span data-ttu-id="d78a6-273">_count_ 是回调的第三个参数，它是一个 32 位的带符号整数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-273">The  _count_ argument is the third argument to the callbacks and is a 32-bit signed integer.</span></span> <span data-ttu-id="d78a6-274">应将其设置为后续参数数量（从 1 开始计数）。</span><span class="sxs-lookup"><span data-stu-id="d78a6-274">It should be set to the number of subsequent arguments, counting from 1.</span></span> <span data-ttu-id="d78a6-275">如果函数或命令不采用任何参数，则应设置为 0。</span><span class="sxs-lookup"><span data-stu-id="d78a6-275">If a function or command takes no arguments, it should be set to zero.</span></span> <span data-ttu-id="d78a6-276">在 Microsoft Office Excel 2003 中，任意函数可采用的参数不得超过 30 个，但大多数函数使用更少的参数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-276">In Microsoft Office Excel 2003, the maximum number of arguments that any function can take is 30, although most take fewer than this.</span></span> <span data-ttu-id="d78a6-277">自 Excel 2007 起，任意函数可采用的参数数目上限增加至 255 个。</span><span class="sxs-lookup"><span data-stu-id="d78a6-277">Starting in Excel 2007, the maximum number of arguments that any function can take was increased to 255.</span></span> 
  
<span data-ttu-id="d78a6-278">使用 **Excel4** 和 **Excel12** 时，_count_ 是指向正在传递的 **XLOPER** 或 **XLOPER12** 值的指针数量。</span><span class="sxs-lookup"><span data-stu-id="d78a6-278">With **Excel4** and **Excel12**,  _count_ is the number of pointers to **XLOPER** or **XLOPER12** values that are being passed.</span></span> <span data-ttu-id="d78a6-279">应小心谨慎，不要传递比 _count_ 所设值更少的参数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-279">You should be very careful not to pass fewer arguments than the value that  _count_ is set to.</span></span> <span data-ttu-id="d78a6-280">否则，会导致 Excel 先于堆栈进行读取并尝试处理无效的 **XLOPER** 或 **XLOPER12** 值，而这会导致应用程序崩溃。</span><span class="sxs-lookup"><span data-stu-id="d78a6-280">This would result in Excel reading ahead into the stack and trying to process invalid **XLOPER** or **XLOPER12** values, which could cause an application crash.</span></span> 
  
<span data-ttu-id="d78a6-281">使用 **Excel4v** 和 **Excel12v** 时，_count_ 是指向要传递为下一个且最后一个参数的 **XLOPER** 或 **XLOPER12** 值的数组大小。</span><span class="sxs-lookup"><span data-stu-id="d78a6-281">With **Excel4v** and **Excel12v**,  _count_ is the size of the array of pointers to **XLOPER** or **XLOPER12** values that is being passed as the next and final argument.</span></span> <span data-ttu-id="d78a6-282">同样，应注意不要传递大小小于 _count_ 元素的数组，因此这会导致溢出数组边界。</span><span class="sxs-lookup"><span data-stu-id="d78a6-282">Again, you should be very careful not to pass a smaller array than  _count_ elements in size, as this will result in the bounds of the array being overrun.</span></span> 
  
## <a name="passing-arguments-to-c-api-functions"></a><span data-ttu-id="d78a6-283">向 C API 函数传递参数</span><span class="sxs-lookup"><span data-stu-id="d78a6-283">Passing Arguments to C API Functions</span></span>

<span data-ttu-id="d78a6-284">**Excel4** 和 **Excel12** 均在 _count_ 后面使用变量长度参数列表，它们被分别解释为指向 **XLOPER** 和 **XLOPER12** 值的指针。</span><span class="sxs-lookup"><span data-stu-id="d78a6-284">Both **Excel4** and **Excel12** take variable length argument lists, after  _count_, which are interpreted as pointers to **XLOPER** and **XLOPER12** values, respectively.</span></span> <span data-ttu-id="d78a6-285">**Excel4v** 和 **Excel12v** 在 _count_ 后面使用单个参数，它是指向 **XLOPER** 值（若为 **Excel4v**）和指向 **XLOPER12** 值（若为 **Excel12v**）的指针数组。</span><span class="sxs-lookup"><span data-stu-id="d78a6-285">**Excel4v** and **Excel12v** take a single argument, after  _count_, which is a pointer to an array of pointers to **XLOPER** values in the case of **Excel4v**, and to **XLOPER12** values in the case of **Excel12v**.</span></span>
  
<span data-ttu-id="d78a6-286">借助 **Excel4v** 和 **Excel12v** 数组形式，可在参数数目是一个变量时明确编码对 C API 的调用。</span><span class="sxs-lookup"><span data-stu-id="d78a6-286">The array forms, **Excel4v** and **Excel12v**, enable you to code a call to the C API cleanly when the number of arguments is variable.</span></span> <span data-ttu-id="d78a6-287">下例显示了一个函数，它采用由变量确定大小的数字数组，并通过 C API 使用 Excel 工作表函数计算总和、平均值、最大值和最小值。</span><span class="sxs-lookup"><span data-stu-id="d78a6-287">The following example shows a function that takes a variable-sized array of numbers and uses Excel worksheet functions, via the C API, to calculate the sum, average, minimum, and maximum.</span></span> 
  
```cs
void Excel12v_example(double *dbl_array, int size, double &sum, double &average, double &min, double &max)
{
// 30 is the limit in Excel 2003. 255 is the limit in Excel 2007.
// Use the lower limit to be safe, although it is better to make
// the function version-aware and use the correct limit.
    if(size < 1 || size > 30)
        return;
// Create an array of XLOPER12 values.
    XLOPER12 *xOpArray = (XLOPER12 *)malloc(size * sizeof(XLOPER12));
// Create an array of pointers to XLOPER12 values.
    LPXLOPER12 *xPtrArray =
        (LPXLOPER12 *)malloc(size * sizeof(LPXLOPER12));
// Initialize and populate the array of XLOPER12 values
// and set up the pointers in the pointer array.
    for(int i = 0; i < size; i++)
    {
        xOpArray[i].xltype = xltypeNum;
        xOpArray[i].val.num = dbl_array[i];
        xPtrArray[i] = xOpArray + i;
    }
    XLOPER12 xResult;
    int retval;
    int fn[4] = {xlfSum, xlfAverage, xlfMin, xlfMax};
    double *result_ptr[4] = {&sum, &average, &min, &max};
    for(i = 0; i < 4; i++)
    {
        retval = Excel12v(fn[i], &xResult, size, xPtrArray);
        if(retval == xlretSuccess && xResult.xltype == xltypeNum)
            *result_ptr[i] = xResult.val.num;
    }
    free(xPtrArray);
    free(xOpArray);
}

```

<span data-ttu-id="d78a6-288">如果在先前代码中将对 **XLOPER12** 值的引用替换为 **XLOPER**，并将 **Excel12v** 替换为 **Excel4v**，则会导致出现一个适合所有 Excel 版本的函数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-288">Replacing references to **XLOPER12** values with **XLOPER**, and **Excel12v** with **Excel4v**, in the preceding code would result in a function that would work with all versions of Excel.</span></span> <span data-ttu-id="d78a6-289">Excel 函数 **SUM**、**AVERAGE**、**MIN** 和 **MAX** 的此操作足够简单，因此可使用 C 更高效地编码它们，同时避免因准备参数和调用 Excel 而产生的开销。</span><span class="sxs-lookup"><span data-stu-id="d78a6-289">This operation of the Excel functions **SUM**, **AVERAGE**, **MIN**, and **MAX** is simple enough that it would be more efficient to code them in C and avoid the overhead of preparing the arguments and calling into Excel.</span></span> <span data-ttu-id="d78a6-290">但是，Excel 包含的很多函数更加复杂，这使得此方法在某些情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="d78a6-290">However, many of the functions Excel contains are more complex, making this approach useful in some cases.</span></span> 
  
<span data-ttu-id="d78a6-291">[xlfRegister](xlfregister-form-1.md) 主题另外提供了一个 **Excel4v** 和 **Excel12v** 使用示例。</span><span class="sxs-lookup"><span data-stu-id="d78a6-291">The [xlfRegister](xlfregister-form-1.md) topic provides another example of working with **Excel4v** and **Excel12v**.</span></span> <span data-ttu-id="d78a6-292">注册 XLL 工作表函数时，可为“**粘贴函数**”对话框中的使用的每个参数应用描述性字符串。</span><span class="sxs-lookup"><span data-stu-id="d78a6-292">When registering an XLL worksheet function, you can supply a descriptive string for each argument that is used in the **Paste Function** dialog box.</span></span> <span data-ttu-id="d78a6-293">因此，要应用于 **xlfRegister** 的参数总数由 XLL 函数使用的参数数量而定，且随函数而异。</span><span class="sxs-lookup"><span data-stu-id="d78a6-293">Therefore, the number of total arguments being supplied to **xlfRegister** depends on the number of arguments your XLL function takes and will vary from one function to the next.</span></span> 
  
<span data-ttu-id="d78a6-294">如果始终调用具有相同参数数量的 C API 或命令，则需要避免额外的步骤（即，为这些参数创建指针数组）。</span><span class="sxs-lookup"><span data-stu-id="d78a6-294">Where you always call a C API function or command with the same number of arguments, you want to avoid the extra step of creating an array of pointers for those arguments.</span></span> <span data-ttu-id="d78a6-295">在这些情况下，使用 **Excel4** 和 **Excel12** 时操作更简单、界面更清晰。</span><span class="sxs-lookup"><span data-stu-id="d78a6-295">In those cases, it is simpler and cleaner to use **Excel4** and **Excel12**.</span></span> <span data-ttu-id="d78a6-296">例如，注册 XLL 函数和命令时，需要提供 DLL 或 XLL 的完整路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="d78a6-296">For example, when registering XLL functions and commands, you need to supply the full path and file name of the DLL or XLL.</span></span> <span data-ttu-id="d78a6-297">可通过对 **xlfGetName** 的调用获取文件名，然后通过对 **xlFree** 的调用释放它，如 **Excel4** 和 **Excel12** 的下述示例所示。</span><span class="sxs-lookup"><span data-stu-id="d78a6-297">You can obtain the file name in a call to **xlfGetName** and then release it with a call to **xlFree**, as shown in the following example for both **Excel4** and **Excel12**.</span></span>
  
```cs
XLOPER xDllName;
if(Excel4(xlfGetName, &xDllName, 0) == xlretSuccess)
{
    // Use the name, and 
    // then free the memory that Excel allocated for the string.
    Excel4(xlFree, 0, 1, &xDllName);
}
XLOPER12 xDllName;
if(Excel12(xlfGetName, &xDllName, 0) == xlretSuccess)
{
    // Use the name, and
    // then free the memory that Excel allocated for the string.
    Excel12(xlFree, 0, 1, &xDllName);
}

```

<span data-ttu-id="d78a6-298">实际上，通过创建一个 **xltypeMulti** **XLOPER12** 参数并使用 **Excel12** 调用 C API，可更高效地对函数 **Excel12v_example** 进行编码，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="d78a6-298">In practice, the function, **Excel12v_example**, could be coded more efficiently by creating a single **xltypeMulti** **XLOPER12** argument, and calling the C API by using **Excel12**, as shown in the following example.</span></span>
  
```cs
void Excel12_example(double *dbl_array, int size, double &sum, double &average, double &min, double &max)
{
// In this implementation, the upper limit is the largest
// single column array (equals 2^20, or 1048576, rows in Excel 2007).
    if(size < 1 || size > 1048576)
        return;
// Create an array of XLOPER12 values.
    XLOPER12 *xOpArray = (XLOPER12 *)malloc(size * sizeof(XLOPER12));
// Create and initialize an xltypeMulti array
// that represents a one-column array.
    XLOPER12 xOpMulti;
    xOpMulti.xltype = xltypeMulti;
    xOpMulti.val.array.lparray = xOpArray;
    xOpMulti.val.array.columns = 1;
    xOpMulti.val.array.rows = size;
// Initialize and populate the array of XLOPER12 values.
    for(int i = 0; i < size; i++)
    {
        xOpArray[i].xltype = xltypeNum;
        xOpArray[i].val.num = dbl_array[i];
    }
    XLOPER12 xResult;
    int fn[4] = {xlfSum, xlfAverage, xlfMin, xlfMax};
    double *result_ptr[4] = {&sum, &average, &min, &max};
    for(i = 0; i < 4; i++)
    {
        Excel12(fn[i], &xResult, 1, &xOpMulti);
        if(xResult.xltype == xltypeNum)
            *result_ptr[i] = xResult.val.num;
    }
    free(xOpArray);
}

```

> [!NOTE]
> <span data-ttu-id="d78a6-299">在本例中，将忽略 **Excel12** 的返回值。</span><span class="sxs-lookup"><span data-stu-id="d78a6-299">In this case, the return value of **Excel12** is ignored.</span></span> <span data-ttu-id="d78a6-300">代码改为检查所返回的 **XLOPER12** 是否为 **xltypeNum**，从而确定调用是否成功。</span><span class="sxs-lookup"><span data-stu-id="d78a6-300">The code instead checks that the returned **XLOPER12** is **xltypeNum** to determine whether the call was successful.</span></span> 
  
## <a name="xlcallver"></a><span data-ttu-id="d78a6-301">XLCallVer</span><span class="sxs-lookup"><span data-stu-id="d78a6-301">XLCallVer</span></span>

<span data-ttu-id="d78a6-302">除了回调 **Excel4**、**Excel4v**、**Excel12** 和 **Excel12v**，Excel 还将导出函数 **XLCallVer**，它会返回 C API 当前正在运行的版本。</span><span class="sxs-lookup"><span data-stu-id="d78a6-302">In addition to the callbacks **Excel4**, **Excel4v**, **Excel12**, and **Excel12v**, Excel exports a function **XLCallVer**, which returns the version of the C API currently running.</span></span>
  
<span data-ttu-id="d78a6-303">函数原型如下：</span><span class="sxs-lookup"><span data-stu-id="d78a6-303">The function prototype is as follows:</span></span>
  
 `int pascal XLCallVer(void);`
  
<span data-ttu-id="d78a6-304">可通过任意 XLL 命令或函数调用此函数（它是线程安全的）。</span><span class="sxs-lookup"><span data-stu-id="d78a6-304">You can call this function, which is thread safe, from any XLL command or function.</span></span>
  
<span data-ttu-id="d78a6-305">在 Excel 97 至 Excel 2003 中，**XLCallVer** 返回 1280 = 0x0500 hex = 5 x 256，它表示 Excel 版本 5。</span><span class="sxs-lookup"><span data-stu-id="d78a6-305">In Excel 97 through Excel 2003, **XLCallVer** returns 1280 = 0x0500 hex = 5 x 256, which indicates Excel version 5.</span></span> <span data-ttu-id="d78a6-306">自 Excel 2007 起，它返回 3072 = 0x0c00 hex = 12 x 256，这表示版本 12。</span><span class="sxs-lookup"><span data-stu-id="d78a6-306">Starting in Excel 2007, it returns 3072 = 0x0c00 hex = 12 x 256, which similarly indicates version 12.</span></span>
  
<span data-ttu-id="d78a6-307">虽然可使用此项来确定能否在运行时使用新的 C API，但你可能偏向于使用 `Excel4(xlfGetWorkspace, &version, 1, &arg)` 来检测正在运行的 Excel 版本，其中 `arg` 是一个设置为 2 的数值 **XLOPER**。</span><span class="sxs-lookup"><span data-stu-id="d78a6-307">Although you can use this to determine whether the new C API is available at run time, you might prefer to detect the running version of Excel by using  `Excel4(xlfGetWorkspace, &version, 1, &arg)`, where  `arg` is a numeric **XLOPER** set to 2.</span></span> <span data-ttu-id="d78a6-308">该函数返回一个字符串 **XLOPER**，它表示版本且随后可强制转换为整数。</span><span class="sxs-lookup"><span data-stu-id="d78a6-308">The function returns a string **XLOPER**, version, which can then be coerced to an integer.</span></span> <span data-ttu-id="d78a6-309">依赖于 Excel 版本而非 C API 版本的原因在于，加载项同样可能需要检测的 Excel 2000、Excel 2002 和 Excel 2003 之间存在差异。</span><span class="sxs-lookup"><span data-stu-id="d78a6-309">The reason for relying on the Excel version rather than the C API version is that there are differences between Excel 2000, Excel 2002, and Excel 2003 that your add-in may also need to detect.</span></span> <span data-ttu-id="d78a6-310">例如，部分统计函数的准确性进行了更改。</span><span class="sxs-lookup"><span data-stu-id="d78a6-310">For example, changes were made to the accuracy of some of the statistics functions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d78a6-311">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d78a6-311">See also</span></span>

- [<span data-ttu-id="d78a6-312">创建 XLL</span><span class="sxs-lookup"><span data-stu-id="d78a6-312">Creating XLLs</span></span>](creating-xlls.md)  
- [<span data-ttu-id="d78a6-313">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="d78a6-313">Accessing XLL Code in Excel</span></span>](accessing-xll-code-in-excel.md)  
- [<span data-ttu-id="d78a6-314">Excel XLL SDK API 函数引用</span><span class="sxs-lookup"><span data-stu-id="d78a6-314">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)  
- [<span data-ttu-id="d78a6-315">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="d78a6-315">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md)  
- [<span data-ttu-id="d78a6-316">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="d78a6-316">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

