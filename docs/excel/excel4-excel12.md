---
title: Excel4/Excel12
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12
- Excel4
keywords:
- excel4 函数 [excel 2007], Excel12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 2404f10d-8641-4ee6-a909-1c5a26610f80
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7c3af5f380ae4144890b1f7b486a61a05c19de74
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429444"
---
# <a name="excel4excel12"></a><span data-ttu-id="33e92-104">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="33e92-104">Excel4/Excel12</span></span>

<span data-ttu-id="33e92-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="33e92-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="33e92-106">从 DLL/XLL 或代码资源中调用内部 Microsoft Excel 工作表函数、宏工作表函数或命令, 或仅 XLL 特殊函数或命令。</span><span class="sxs-lookup"><span data-stu-id="33e92-106">Calls an internal Microsoft Excel worksheet function, macro sheet function or command, or XLL-only special function or command, from within a DLL/XLL or code resource.</span></span>
  
<span data-ttu-id="33e92-107">Excel 的所有最新版本都支持**Excel4**。</span><span class="sxs-lookup"><span data-stu-id="33e92-107">All recent versions of Excel support **Excel4**.</span></span> <span data-ttu-id="33e92-108">从 Excel 2007 开始, 支持**Excel12** 。</span><span class="sxs-lookup"><span data-stu-id="33e92-108">Starting in Excel 2007, **Excel12** is supported.</span></span> 
  
<span data-ttu-id="33e92-109">只有当 Excel 已将控制传递给 DLL 或 XLL 时, 才能调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-109">These functions can be called only when Excel has passed control to the DLL or XLL.</span></span> <span data-ttu-id="33e92-110">当 Excel 通过对 Visual Basic for Applications (VBA) 的调用间接传递控制时, 也可以调用它们。</span><span class="sxs-lookup"><span data-stu-id="33e92-110">They can also be called when Excel has passed control indirectly via a call to Visual Basic for Applications (VBA).</span></span> <span data-ttu-id="33e92-111">任何时候都不能调用它们。</span><span class="sxs-lookup"><span data-stu-id="33e92-111">They cannot be called at any other time.</span></span> <span data-ttu-id="33e92-112">例如, 在调用[DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain)函数期间或其他操作系统调用 dll 的线程或由 DLL 创建的线程中, 不能调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-112">For example, they cannot be called during calls to the [DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain) function or other times when the operating system has called the DLL, or from a thread created by the DLL.</span></span> 
  
<span data-ttu-id="33e92-113">[Excel4v 和 Excel12v](excel4v-excel12v.md)函数接受其参数作为数组, 而**Excel4**和**Excel12**函数接受其参数作为堆栈上的可变长度列表。</span><span class="sxs-lookup"><span data-stu-id="33e92-113">The [Excel4v and Excel12v](excel4v-excel12v.md) functions accept their arguments as an array, whereas the **Excel4** and **Excel12** functions accept their arguments as a variable-length list on the stack.</span></span> <span data-ttu-id="33e92-114">在所有其他方面, **Excel4**的行为与**Excel4v**相同, **Excel12**的行为与**Excel12v**相同。</span><span class="sxs-lookup"><span data-stu-id="33e92-114">In all other respects, **Excel4** behaves the same as **Excel4v**, and **Excel12** behaves the same as **Excel12v**.</span></span>
  
```cs
int Excel4(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER argument1, ...);
int Excel12(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a><span data-ttu-id="33e92-115">参数</span><span class="sxs-lookup"><span data-stu-id="33e92-115">Parameters</span></span>

 <span data-ttu-id="33e92-116">_iFunction_(**int**)</span><span class="sxs-lookup"><span data-stu-id="33e92-116">_iFunction_ (**int**)</span></span>
  
<span data-ttu-id="33e92-117">一个数字, 指示要调用的命令、函数或特殊函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-117">A number that indicates the command, function, or special function you want to call.</span></span> <span data-ttu-id="33e92-118">有关有效_iFunction_值的列表, 请参阅以下备注部分。</span><span class="sxs-lookup"><span data-stu-id="33e92-118">For a list of valid  _iFunction_ values, see the following Remarks section.</span></span> 
  
 <span data-ttu-id="33e92-119">_pxRes_(**LPXLOPER**或**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="33e92-119">_pxRes_ (**LPXLOPER** or **LPXLOPER12**)</span></span>
  
<span data-ttu-id="33e92-120">指向**XLOPER** (带有**Excel4**) 的指针或将包含计算函数结果的**XLOPER12** (带有**Excel12**)。</span><span class="sxs-lookup"><span data-stu-id="33e92-120">A pointer to an **XLOPER** (with **Excel4**) or an **XLOPER12** (with **Excel12**) that will hold the result of the evaluated function.</span></span>
  
 <span data-ttu-id="33e92-121">_iCount_(**int**)</span><span class="sxs-lookup"><span data-stu-id="33e92-121">_iCount_ (**int**)</span></span>
  
<span data-ttu-id="33e92-122">将传递给函数的后续参数的数目。</span><span class="sxs-lookup"><span data-stu-id="33e92-122">The number of subsequent arguments that will be passed to the function.</span></span> <span data-ttu-id="33e92-123">在 Excel 的 Excel 版本中, 最多为 2003, 可以是0到30之间的任意数字。</span><span class="sxs-lookup"><span data-stu-id="33e92-123">In versions of Excel up to 2003, this can be any number from 0 through 30.</span></span> <span data-ttu-id="33e92-124">从 Excel 2007 开始, 可以是0到255之间的任意数字。</span><span class="sxs-lookup"><span data-stu-id="33e92-124">Starting in Excel 2007, this can be any number from 0 through 255.</span></span>
  
 <span data-ttu-id="33e92-125">_argument1 ..._(**LPXLOPER**或**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="33e92-125">_argument1, ..._ (**LPXLOPER** or **LPXLOPER12**)</span></span>
  
<span data-ttu-id="33e92-126">函数的可选参数。</span><span class="sxs-lookup"><span data-stu-id="33e92-126">The optional arguments to the function.</span></span> <span data-ttu-id="33e92-127">所有参数都必须是指向**XLOPER**或**XLOPER12**值的指针。</span><span class="sxs-lookup"><span data-stu-id="33e92-127">All arguments must be pointers to **XLOPER** or **XLOPER12** values.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="33e92-128">返回值</span><span class="sxs-lookup"><span data-stu-id="33e92-128">Return value</span></span>

<span data-ttu-id="33e92-129">返回以下整数 (**int**) 值之一。</span><span class="sxs-lookup"><span data-stu-id="33e92-129">Returns one of the following integer (**int**) values.</span></span>
  
|<span data-ttu-id="33e92-130">**值**</span><span class="sxs-lookup"><span data-stu-id="33e92-130">**Value**</span></span>|<span data-ttu-id="33e92-131">**返回代码**</span><span class="sxs-lookup"><span data-stu-id="33e92-131">**Return code**</span></span>|<span data-ttu-id="33e92-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="33e92-132">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33e92-133">0</span><span class="sxs-lookup"><span data-stu-id="33e92-133">0</span></span>  <br/> |<span data-ttu-id="33e92-134">**xlretSuccess**</span><span class="sxs-lookup"><span data-stu-id="33e92-134">**xlretSuccess**</span></span> <br/> |<span data-ttu-id="33e92-135">成功调用函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-135">The function was called successfully.</span></span> <span data-ttu-id="33e92-136">这并不意味着函数不返回 Excel 错误值;若要找到该参数, 您必须查看生成的_pxRes_参数的类型和值。</span><span class="sxs-lookup"><span data-stu-id="33e92-136">This does not mean that the function did not return an Excel error value; to find that out, you must look at the type and value of the resulting  _pxRes_ parameter.</span></span>  <br/> |
|<span data-ttu-id="33e92-137">1</span><span class="sxs-lookup"><span data-stu-id="33e92-137">1</span></span>  <br/> |<span data-ttu-id="33e92-138">**xlretAbort**</span><span class="sxs-lookup"><span data-stu-id="33e92-138">**xlretAbort**</span></span> <br/> |<span data-ttu-id="33e92-139">命令或函数异常终止 (内部终止)。</span><span class="sxs-lookup"><span data-stu-id="33e92-139">The command or function was terminated abnormally (internal abort).</span></span> <span data-ttu-id="33e92-140">如果 XLM 宏工作表通过调用**CLOSE**或 Excel 内存不足, 则会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="33e92-140">This can occur if an XLM macro sheet closes itself by calling **CLOSE**, or if Excel is out of memory.</span></span> <span data-ttu-id="33e92-141">如果 Excel 返回此错误, 则调用函数必须立即退出。</span><span class="sxs-lookup"><span data-stu-id="33e92-141">If Excel returns this error, the calling function must exit immediately.</span></span> <span data-ttu-id="33e92-142">仅允许 DLL 在退出之前调用**xlFree** 。</span><span class="sxs-lookup"><span data-stu-id="33e92-142">The DLL is permitted to call **xlFree** only before exiting.</span></span> <span data-ttu-id="33e92-143">不允许对 C API 进行其他所有调用。</span><span class="sxs-lookup"><span data-stu-id="33e92-143">All other calls to the C API are not permitted.</span></span> <span data-ttu-id="33e92-144">用户可以使用 "**文件**" 菜单上的 "**保存**" 命令, 以交互方式保存任何工作。</span><span class="sxs-lookup"><span data-stu-id="33e92-144">The user can save any work interactively by using the **Save** command on the **File** menu.</span></span>  <br/> |
|<span data-ttu-id="33e92-145">双面</span><span class="sxs-lookup"><span data-stu-id="33e92-145">2</span></span>  <br/> |<span data-ttu-id="33e92-146">**xlretInvXlfn**</span><span class="sxs-lookup"><span data-stu-id="33e92-146">**xlretInvXlfn**</span></span> <br/> |<span data-ttu-id="33e92-147">提供了无效的函数编号。</span><span class="sxs-lookup"><span data-stu-id="33e92-147">An invalid function number was supplied.</span></span> <span data-ttu-id="33e92-148">如果使用的是 xlcall.h 头文件中的常量, 则不应发生此情况, 除非您调用的是运行的 Excel 版本中不支持的内容。</span><span class="sxs-lookup"><span data-stu-id="33e92-148">If you are using constants from the Xlcall.h header file, this should not occur unless you are calling something that is not supported in the version of Excel you are running.</span></span>  <br/> |
|<span data-ttu-id="33e92-149">4</span><span class="sxs-lookup"><span data-stu-id="33e92-149">4</span></span>  <br/> |<span data-ttu-id="33e92-150">**xlretInvCount**</span><span class="sxs-lookup"><span data-stu-id="33e92-150">**xlretInvCount**</span></span> <br/> |<span data-ttu-id="33e92-151">输入的参数数目无效。</span><span class="sxs-lookup"><span data-stu-id="33e92-151">An invalid number of arguments was entered.</span></span> <span data-ttu-id="33e92-152">在最高版本为 Excel 2003 的情况下, 任何函数可以执行的最大参数数为30个。</span><span class="sxs-lookup"><span data-stu-id="33e92-152">In versions up to Excel 2003, the maximum number of arguments any function can take is 30.</span></span> <span data-ttu-id="33e92-153">从 Excel 2007 开始, 最大数目为255。</span><span class="sxs-lookup"><span data-stu-id="33e92-153">Starting in Excel 2007, the maximum number is 255.</span></span> <span data-ttu-id="33e92-154">有些参数需要固定的或最少的参数数目。</span><span class="sxs-lookup"><span data-stu-id="33e92-154">Some require a fixed or minimum number of arguments.</span></span>  <br/> |
|<span data-ttu-id="33e92-155">utf-8</span><span class="sxs-lookup"><span data-stu-id="33e92-155">8</span></span>  <br/> |<span data-ttu-id="33e92-156">**xlretInvXloper**</span><span class="sxs-lookup"><span data-stu-id="33e92-156">**xlretInvXloper**</span></span> <br/> |<span data-ttu-id="33e92-157">向函数传递了无效的**XLOPER**或**XLOPER12** , 或者使用了错误类型的参数。</span><span class="sxs-lookup"><span data-stu-id="33e92-157">An invalid **XLOPER** or **XLOPER12** was passed to the function, or an argument of the wrong type was used.</span></span>  <br/> |
|<span data-ttu-id="33e92-158">16 </span><span class="sxs-lookup"><span data-stu-id="33e92-158">16</span></span>  <br/> |<span data-ttu-id="33e92-159">**xlretStackOvfl**</span><span class="sxs-lookup"><span data-stu-id="33e92-159">**xlretStackOvfl**</span></span> <br/> |<span data-ttu-id="33e92-160">堆栈溢出发生。</span><span class="sxs-lookup"><span data-stu-id="33e92-160">A stack overflow occurred.</span></span> <span data-ttu-id="33e92-161">使用**xlStack**监视堆栈上留下的空间量。</span><span class="sxs-lookup"><span data-stu-id="33e92-161">Use **xlStack** to monitor the amount of room left on the stack.</span></span> <span data-ttu-id="33e92-162">尽可能避免在堆栈上分配非常大的本地 (自动) 数组和结构。使其成为静态的。</span><span class="sxs-lookup"><span data-stu-id="33e92-162">Avoid allocating very large local (automatic) arrays and structures on the stack where possible; make them static.</span></span> <span data-ttu-id="33e92-163">(请注意, 在未检测到堆栈溢出的情况下可能会发生。)</span><span class="sxs-lookup"><span data-stu-id="33e92-163">(Note that a stack overflow might occur without being detected.)</span></span>  <br/> |
|<span data-ttu-id="33e92-164">32</span><span class="sxs-lookup"><span data-stu-id="33e92-164">32</span></span>  <br/> |<span data-ttu-id="33e92-165">**xlretFailed**</span><span class="sxs-lookup"><span data-stu-id="33e92-165">**xlretFailed**</span></span> <br/> |<span data-ttu-id="33e92-166">命令等效的函数失败。</span><span class="sxs-lookup"><span data-stu-id="33e92-166">A command-equivalent function failed.</span></span> <span data-ttu-id="33e92-167">这与显示 "宏错误警告" 对话框的宏命令是等效的。</span><span class="sxs-lookup"><span data-stu-id="33e92-167">This is equivalent to a macro command displaying the macro error alert dialog box.</span></span>  <br/> |
|<span data-ttu-id="33e92-168">64</span><span class="sxs-lookup"><span data-stu-id="33e92-168">64</span></span>  <br/> |<span data-ttu-id="33e92-169">**xlretUncalced**</span><span class="sxs-lookup"><span data-stu-id="33e92-169">**xlretUncalced**</span></span> <br/> |<span data-ttu-id="33e92-170">试图对尚未计算的单元格进行取消引用, 因为它计划在当前单元格后重新计算。</span><span class="sxs-lookup"><span data-stu-id="33e92-170">An attempt was made to dereference a cell that has not been calculated yet, because it is scheduled to be recalculated after the current cell.</span></span> <span data-ttu-id="33e92-171">在这种情况下, DLL 应立即将控制返回到 Excel。</span><span class="sxs-lookup"><span data-stu-id="33e92-171">In this case, the DLL should return control to Excel immediately.</span></span> <span data-ttu-id="33e92-172">仅允许 DLL 在退出之前调用**xlFree** 。</span><span class="sxs-lookup"><span data-stu-id="33e92-172">The DLL is permitted to call **xlFree** only before exiting.</span></span> <span data-ttu-id="33e92-173">不允许对 C API 进行其他所有调用。</span><span class="sxs-lookup"><span data-stu-id="33e92-173">All other calls to the C API are not permitted.</span></span> <span data-ttu-id="33e92-174">有关哪些函数可以和无法访问尚未重新计算的单元格的值的详细信息, 请参阅[Excel 命令、函数和状态](excel-commands-functions-and-states.md)。</span><span class="sxs-lookup"><span data-stu-id="33e92-174">For more information about which functions can and cannot access the values of cells that have not been recalculated, see [Excel Commands, Functions, and States](excel-commands-functions-and-states.md).</span></span>  <br/> |
|<span data-ttu-id="33e92-175">128</span><span class="sxs-lookup"><span data-stu-id="33e92-175">128</span></span>  <br/> |<span data-ttu-id="33e92-176">**xlretNotThreadSafe**</span><span class="sxs-lookup"><span data-stu-id="33e92-176">**xlretNotThreadSafe**</span></span> <br/> |<span data-ttu-id="33e92-177">试图调用在工作簿的多线程重新计算期间线程安全的函数 (或可能不是线程安全)。</span><span class="sxs-lookup"><span data-stu-id="33e92-177">An attempt was made to call a function that is not, or might not be, thread safe during a multithreaded recalculation of the workbook.</span></span>  <br/> <span data-ttu-id="33e92-178">从 Excel 2007 开始, 将返回此值, 并且仅在声明为线程安全的 XLL 工作表函数中。</span><span class="sxs-lookup"><span data-stu-id="33e92-178">Starting in Excel 2007, this value is returned, and only within XLL worksheet functions declared as thread safe.</span></span>  <br/> |
|<span data-ttu-id="33e92-179">256</span><span class="sxs-lookup"><span data-stu-id="33e92-179">256</span></span>  <br/> |<span data-ttu-id="33e92-180">**xlRetInvAsynchronousContext**</span><span class="sxs-lookup"><span data-stu-id="33e92-180">**xlRetInvAsynchronousContext**</span></span> <br/> |<span data-ttu-id="33e92-181">异步函数句柄无效。</span><span class="sxs-lookup"><span data-stu-id="33e92-181">The asynchronous function handle is invalid.</span></span>  <br/> <span data-ttu-id="33e92-182">此值仅由 Excel 2010 使用。</span><span class="sxs-lookup"><span data-stu-id="33e92-182">This value is used only by Excel 2010.</span></span>  <br/> |
|<span data-ttu-id="33e92-183">512</span><span class="sxs-lookup"><span data-stu-id="33e92-183">512</span></span>  <br/> |<span data-ttu-id="33e92-184">**xlRetNotClusterSafe**</span><span class="sxs-lookup"><span data-stu-id="33e92-184">**xlRetNotClusterSafe**</span></span> <br/> |<span data-ttu-id="33e92-185">群集上不支持该呼叫。</span><span class="sxs-lookup"><span data-stu-id="33e92-185">The call is not supported on clusters.</span></span>  <br/> <span data-ttu-id="33e92-186">此值仅由 Excel 2010 使用。</span><span class="sxs-lookup"><span data-stu-id="33e92-186">This value is used only by Excel 2010.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="33e92-187">说明</span><span class="sxs-lookup"><span data-stu-id="33e92-187">Remarks</span></span>

### <a name="valid-ifunction-values"></a><span data-ttu-id="33e92-188">有效的 iFunction 值</span><span class="sxs-lookup"><span data-stu-id="33e92-188">Valid iFunction values</span></span>

<span data-ttu-id="33e92-189">有效的**iFunction**值为 xlcall.h 头文件中定义的任意 **.xlf**或 **.xlc**常量, 或以下任何特殊函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-189">Valid **iFunction** values are any of the **xlf...** or **xlc...** constants defined in the Xlcall.h header file or any of the following special functions.</span></span> 
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="33e92-190">**xlAbort**</span><span class="sxs-lookup"><span data-stu-id="33e92-190">**xlAbort**</span></span> <br/> |<span data-ttu-id="33e92-191">**xlEnableXLMsgs**</span><span class="sxs-lookup"><span data-stu-id="33e92-191">**xlEnableXLMsgs**</span></span> <br/> |<span data-ttu-id="33e92-192">**xlGetInst**</span><span class="sxs-lookup"><span data-stu-id="33e92-192">**xlGetInst**</span></span> <br/> |<span data-ttu-id="33e92-193">**xlSheetNm**</span><span class="sxs-lookup"><span data-stu-id="33e92-193">**xlSheetNm**</span></span> <br/> |
|<span data-ttu-id="33e92-194">**xlCoerce**</span><span class="sxs-lookup"><span data-stu-id="33e92-194">**xlCoerce**</span></span> <br/> |<span data-ttu-id="33e92-195">**xlFree**</span><span class="sxs-lookup"><span data-stu-id="33e92-195">**xlFree**</span></span> <br/> |<span data-ttu-id="33e92-196">**xlGetName**</span><span class="sxs-lookup"><span data-stu-id="33e92-196">**xlGetName**</span></span> <br/> |<span data-ttu-id="33e92-197">**xlStack**</span><span class="sxs-lookup"><span data-stu-id="33e92-197">**xlStack**</span></span> <br/> |
|<span data-ttu-id="33e92-198">**xlDefineBinaryName**</span><span class="sxs-lookup"><span data-stu-id="33e92-198">**xlDefineBinaryName**</span></span> <br/> |<span data-ttu-id="33e92-199">**xlGetBinaryName**</span><span class="sxs-lookup"><span data-stu-id="33e92-199">**xlGetBinaryName**</span></span> <br/> |<span data-ttu-id="33e92-200">**xlSet**</span><span class="sxs-lookup"><span data-stu-id="33e92-200">**xlSet**</span></span> <br/> |<span data-ttu-id="33e92-201">**xlUDF**</span><span class="sxs-lookup"><span data-stu-id="33e92-201">**xlUDF**</span></span> <br/> |
|<span data-ttu-id="33e92-202">**xlDisableXLMsgs**</span><span class="sxs-lookup"><span data-stu-id="33e92-202">**xlDisableXLMsgs**</span></span> <br/> |<span data-ttu-id="33e92-203">**xlGetHwnd**</span><span class="sxs-lookup"><span data-stu-id="33e92-203">**xlGetHwnd**</span></span> <br/> |<span data-ttu-id="33e92-204">**xlSheetId**</span><span class="sxs-lookup"><span data-stu-id="33e92-204">**xlSheetId**</span></span> <br/> ||
   
### <a name="different-types-of-functions"></a><span data-ttu-id="33e92-205">不同类型的函数</span><span class="sxs-lookup"><span data-stu-id="33e92-205">Different Types of Functions</span></span>

 <span data-ttu-id="33e92-206">**Excel4**和**Excel12**区分三类函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-206">**Excel4** and **Excel12** distinguish among three classes of functions.</span></span> <span data-ttu-id="33e92-207">根据 Excel 可能调用 DLL 的三种状态对函数进行分类。</span><span class="sxs-lookup"><span data-stu-id="33e92-207">The functions are classified according to the three states in which Excel might call the DLL.</span></span> 
  
- <span data-ttu-id="33e92-208">当从工作表中调用 DLL 作为重新计算的结果时, 将应用类1。</span><span class="sxs-lookup"><span data-stu-id="33e92-208">Class 1 applies when the DLL is called from a worksheet as a result of recalculation.</span></span> 
    
- <span data-ttu-id="33e92-209">当从函数宏或工作表中调用 DLL 时, 类2适用于在键入文本中用数字符号 (#) 注册的工作表。</span><span class="sxs-lookup"><span data-stu-id="33e92-209">Class 2 applies when the DLL is called from within a function macro or from a worksheet where it was registered with a number sign (#) in the type text.</span></span>
    
- <span data-ttu-id="33e92-210">当从对象、宏、菜单、工具栏、快捷键、 **ExecuteExcel4Macro**方法或**工具/宏/运行**命令调用 DLL 时, 将应用类3。</span><span class="sxs-lookup"><span data-stu-id="33e92-210">Class 3 applies when a DLL is called from an object, macro, menu, toolbar, shortcut key, **ExecuteExcel4Macro** method, or the **Tools/Macro/Run** command.</span></span> <span data-ttu-id="33e92-211">有关详细信息, 请参阅[Excel 命令、函数和状态](excel-commands-functions-and-states.md)。</span><span class="sxs-lookup"><span data-stu-id="33e92-211">For more information, see [Excel Commands, Functions, and States](excel-commands-functions-and-states.md).</span></span>
    
<span data-ttu-id="33e92-212">下表显示了每个类中的有效函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-212">The following table shows what functions are valid in each class.</span></span>
  
|<span data-ttu-id="33e92-213">**1 类**</span><span class="sxs-lookup"><span data-stu-id="33e92-213">**Class 1**</span></span>|<span data-ttu-id="33e92-214">**2 类**</span><span class="sxs-lookup"><span data-stu-id="33e92-214">**Class 2**</span></span>|<span data-ttu-id="33e92-215">**3 类**</span><span class="sxs-lookup"><span data-stu-id="33e92-215">**Class 3**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33e92-216">任何工作表函数</span><span class="sxs-lookup"><span data-stu-id="33e92-216">Any worksheet function</span></span>  <br/> <span data-ttu-id="33e92-217">除**xlSet**外的任何仅 XLL **xl ...** 函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-217">Any XLL-only **xl...** function except **xlSet**.</span></span>  <br/> <span data-ttu-id="33e92-218">**xlfCaller**</span><span class="sxs-lookup"><span data-stu-id="33e92-218">**xlfCaller**</span></span> <br/> |<span data-ttu-id="33e92-219">任何工作表函数</span><span class="sxs-lookup"><span data-stu-id="33e92-219">Any worksheet function</span></span>  <br/> <span data-ttu-id="33e92-220">除**xlSet**以外的任何**xl**函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-220">Any **xl...** function except **xlSet**.</span></span>  <br/> <span data-ttu-id="33e92-221">宏工作表函数 (包括**xlfCaller**) 返回一个值, 但不执行影响工作区或任何打开的工作簿的操作。</span><span class="sxs-lookup"><span data-stu-id="33e92-221">Macro sheet functions, including **xlfCaller**, that return a value but perform no action that affects the workspace or any open workbook.</span></span>  <br/> |<span data-ttu-id="33e92-222">任何函数, 包括**xlSet**和命令等效的函数。</span><span class="sxs-lookup"><span data-stu-id="33e92-222">Any function, including **xlSet** and command-equivalent functions.</span></span>  <br/> |
   
### <a name="displaying-the-dialog-box-for-a-command-equivalent-function"></a><span data-ttu-id="33e92-223">显示等效于命令的函数的对话框</span><span class="sxs-lookup"><span data-stu-id="33e92-223">Displaying the Dialog Box for a Command-Equivalent Function</span></span>

<span data-ttu-id="33e92-224">如果等效命令的函数有关联的对话框, 则可以在**iFunction**中设置**xlPrompt**位。</span><span class="sxs-lookup"><span data-stu-id="33e92-224">If a command-equivalent function has an associated dialog box, you can set the **xlPrompt** bit in **iFunction**.</span></span> <span data-ttu-id="33e92-225">这意味着在执行此命令之前, Excel 将显示相应的对话框。</span><span class="sxs-lookup"><span data-stu-id="33e92-225">This means that Excel displays the appropriate dialog box before carrying out the command.</span></span>
  
### <a name="writing-international-dlls"></a><span data-ttu-id="33e92-226">编写国际 dll</span><span class="sxs-lookup"><span data-stu-id="33e92-226">Writing International DLLs</span></span>

<span data-ttu-id="33e92-227">如果在**iFunction**中设置**xlIntl**位, 则会执行函数或命令, 就像它是从国际宏表中调用一样。</span><span class="sxs-lookup"><span data-stu-id="33e92-227">If you set the **xlIntl** bit in **iFunction**, the function or command is carried out as if it were being called from an International Macro Sheet.</span></span> <span data-ttu-id="33e92-228">这意味着该命令的行为与 Excel 的美国版本相同, 即使它在国际 (本地化) 版本上运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="33e92-228">This means that the command behaves as it would on the U.S. version of Excel, even if it is running on an international (localized) version.</span></span>
  
### <a name="xlretuncalced-or-xlretabort"></a><span data-ttu-id="33e92-229">xlretUncalced 或 xlretAbort</span><span class="sxs-lookup"><span data-stu-id="33e92-229">xlretUncalced or xlretAbort</span></span>

<span data-ttu-id="33e92-230">在接收到这些返回值之一之后, 您的 DLL 必须立即清除控件并将其返回到 Excel。</span><span class="sxs-lookup"><span data-stu-id="33e92-230">After receiving one of these return values, your DLL must clean up and return control to Excel immediately.</span></span> <span data-ttu-id="33e92-231">在接收到这些返回值之一后, 通过 C API 对 Excel 的回调 ( **xlFree**除外) 将被禁用。</span><span class="sxs-lookup"><span data-stu-id="33e92-231">Callbacks into Excel via the C API, except **xlFree**, are disabled after receiving one of these return values.</span></span>
  
## <a name="example"></a><span data-ttu-id="33e92-232">示例</span><span class="sxs-lookup"><span data-stu-id="33e92-232">Example</span></span>

<span data-ttu-id="33e92-233">下面的示例使用**Excel12**函数选择从中调用它的单元格。</span><span class="sxs-lookup"><span data-stu-id="33e92-233">The following example uses the **Excel12** function to select the cell from which it was called.</span></span> 
  
<span data-ttu-id="33e92-234">此代码示例是 Excel 2010 XLL SDK 中提供的更大示例的一部分, 该示例位于您安装 SDK 的以下位置:</span><span class="sxs-lookup"><span data-stu-id="33e92-234">This code example is part of a larger example provided in the Excel 2010 XLL SDK, at the following location where you installed the SDK:</span></span>
  
<span data-ttu-id="33e92-235">\Samples\Example\Example.c。</span><span class="sxs-lookup"><span data-stu-id="33e92-235">\Samples\Example\Example.c.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33e92-236">此函数调用命令宏 (xlcSelect), 因此, 仅当从 XLM 宏表中调用该宏时, 才会运行该宏。</span><span class="sxs-lookup"><span data-stu-id="33e92-236">This function calls a command macro (xlcSelect) and, therefore, works only if it is called from an XLM macro sheet.</span></span> 
  
```cs
short WINAPI Excel12Example(void)
{
    XLOPER12 xRes;
    Excel12(xlfCaller, &xRes, 0);
    Excel12(xlcSelect, 0, 1, (LPXLOPER12)&xRes);
    Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="33e92-237">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33e92-237">See also</span></span>



[<span data-ttu-id="33e92-238">Excel4v/Excel12v</span><span class="sxs-lookup"><span data-stu-id="33e92-238">Excel4v/Excel12v</span></span>](excel4v-excel12v.md)

