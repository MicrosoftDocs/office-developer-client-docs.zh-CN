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
- excel4 函数 [excel 2007]，Excel12 函数 [Excel 2007]
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
# <a name="excel4excel12"></a><span data-ttu-id="2a175-104">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="2a175-104">Excel4/Excel12</span></span>

<span data-ttu-id="2a175-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a175-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2a175-106">从 DLL/XLL 或代码Microsoft Excel调用内部工作表函数、宏工作表函数或命令或仅 XLL 的特殊函数或命令。</span><span class="sxs-lookup"><span data-stu-id="2a175-106">Calls an internal Microsoft Excel worksheet function, macro sheet function or command, or XLL-only special function or command, from within a DLL/XLL or code resource.</span></span>
  
<span data-ttu-id="2a175-107">所有最新版本的 Excel都支持 **Excel4。**</span><span class="sxs-lookup"><span data-stu-id="2a175-107">All recent versions of Excel support **Excel4**.</span></span> <span data-ttu-id="2a175-108">从 2007 Excel开始，**支持 Excel12。**</span><span class="sxs-lookup"><span data-stu-id="2a175-108">Starting in Excel 2007, **Excel12** is supported.</span></span> 
  
<span data-ttu-id="2a175-109">只有在将控件传递给 DLL Excel XLL 时，才能调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="2a175-109">These functions can be called only when Excel has passed control to the DLL or XLL.</span></span> <span data-ttu-id="2a175-110">当通过调用 VBA Excel间接传递控制权时，也可以Visual Basic for Applications (这些) 。</span><span class="sxs-lookup"><span data-stu-id="2a175-110">They can also be called when Excel has passed control indirectly via a call to Visual Basic for Applications (VBA).</span></span> <span data-ttu-id="2a175-111">无法在其他时间调用它们。</span><span class="sxs-lookup"><span data-stu-id="2a175-111">They cannot be called at any other time.</span></span> <span data-ttu-id="2a175-112">例如，在调用 [DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain) 函数期间或操作系统调用 DLL 时的其他时间，或者从 DLL 创建的线程调用它们时，无法调用它们。</span><span class="sxs-lookup"><span data-stu-id="2a175-112">For example, they cannot be called during calls to the [DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain) function or other times when the operating system has called the DLL, or from a thread created by the DLL.</span></span> 
  
<span data-ttu-id="2a175-113">[Excel4v 和 Excel12v](excel4v-excel12v.md)函数接受其参数作为数组，**而 Excel4** 和 **Excel12** 函数接受其参数作为堆栈上的可变长度列表。</span><span class="sxs-lookup"><span data-stu-id="2a175-113">The [Excel4v and Excel12v](excel4v-excel12v.md) functions accept their arguments as an array, whereas the **Excel4** and **Excel12** functions accept their arguments as a variable-length list on the stack.</span></span> <span data-ttu-id="2a175-114">在所有其他方面 **，Excel4** 的行为与 **Excel4v** 相同， **而 Excel12** 的行为与 **Excel12v 相同**。</span><span class="sxs-lookup"><span data-stu-id="2a175-114">In all other respects, **Excel4** behaves the same as **Excel4v**, and **Excel12** behaves the same as **Excel12v**.</span></span>
  
```cs
int Excel4(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER argument1, ...);
int Excel12(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a><span data-ttu-id="2a175-115">参数</span><span class="sxs-lookup"><span data-stu-id="2a175-115">Parameters</span></span>

 <span data-ttu-id="2a175-116">_iFunction_ (**int)**</span><span class="sxs-lookup"><span data-stu-id="2a175-116">_iFunction_ (**int**)</span></span>
  
<span data-ttu-id="2a175-117">指示要调用的命令、函数或特殊函数的编号。</span><span class="sxs-lookup"><span data-stu-id="2a175-117">A number that indicates the command, function, or special function you want to call.</span></span> <span data-ttu-id="2a175-118">有关有效  _iFunction_ 值的列表，请参阅以下"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="2a175-118">For a list of valid  _iFunction_ values, see the following Remarks section.</span></span> 
  
 <span data-ttu-id="2a175-119">_pxRes_ (**LPXLOPER** 或 **LPXLOPER12**) </span><span class="sxs-lookup"><span data-stu-id="2a175-119">_pxRes_ (**LPXLOPER** or **LPXLOPER12**)</span></span>
  
<span data-ttu-id="2a175-120">指向包含 **Excel4** (的 **XLOPER**) 或包含 Excel12 (的 **XLOPER12** **) ，** 其中将保存计算函数的结果。</span><span class="sxs-lookup"><span data-stu-id="2a175-120">A pointer to an **XLOPER** (with **Excel4**) or an **XLOPER12** (with **Excel12**) that will hold the result of the evaluated function.</span></span>
  
 <span data-ttu-id="2a175-121">_iCount_ (**int)**</span><span class="sxs-lookup"><span data-stu-id="2a175-121">_iCount_ (**int**)</span></span>
  
<span data-ttu-id="2a175-122">将传递给函数的后续参数的数量。</span><span class="sxs-lookup"><span data-stu-id="2a175-122">The number of subsequent arguments that will be passed to the function.</span></span> <span data-ttu-id="2a175-123">在 2003 Excel版本中，它可以是 0 到 30 的任何数字。</span><span class="sxs-lookup"><span data-stu-id="2a175-123">In versions of Excel up to 2003, this can be any number from 0 through 30.</span></span> <span data-ttu-id="2a175-124">从 Excel 2007 开始，可以是从 0 到 255 的任何数字。</span><span class="sxs-lookup"><span data-stu-id="2a175-124">Starting in Excel 2007, this can be any number from 0 through 255.</span></span>
  
 <span data-ttu-id="2a175-125">_argument1， ..._ (**LPXLOPER** 或 **LPXLOPER12**) </span><span class="sxs-lookup"><span data-stu-id="2a175-125">_argument1, ..._ (**LPXLOPER** or **LPXLOPER12**)</span></span>
  
<span data-ttu-id="2a175-126">函数的可选参数。</span><span class="sxs-lookup"><span data-stu-id="2a175-126">The optional arguments to the function.</span></span> <span data-ttu-id="2a175-127">所有参数都必须是指向 **XLOPER** 或 **XLOPER12 值的** 指针。</span><span class="sxs-lookup"><span data-stu-id="2a175-127">All arguments must be pointers to **XLOPER** or **XLOPER12** values.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="2a175-128">返回值</span><span class="sxs-lookup"><span data-stu-id="2a175-128">Return value</span></span>

<span data-ttu-id="2a175-129">返回整数值中的 (**整数)** 之一。</span><span class="sxs-lookup"><span data-stu-id="2a175-129">Returns one of the following integer (**int**) values.</span></span>
  
|<span data-ttu-id="2a175-130">**值**</span><span class="sxs-lookup"><span data-stu-id="2a175-130">**Value**</span></span>|<span data-ttu-id="2a175-131">**返回代码**</span><span class="sxs-lookup"><span data-stu-id="2a175-131">**Return code**</span></span>|<span data-ttu-id="2a175-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a175-132">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a175-133">0</span><span class="sxs-lookup"><span data-stu-id="2a175-133">0</span></span>  <br/> |<span data-ttu-id="2a175-134">**xlretSuccess**</span><span class="sxs-lookup"><span data-stu-id="2a175-134">**xlretSuccess**</span></span> <br/> |<span data-ttu-id="2a175-135">函数已成功调用。</span><span class="sxs-lookup"><span data-stu-id="2a175-135">The function was called successfully.</span></span> <span data-ttu-id="2a175-136">这并不意味着函数未返回错误Excel错误值;若要了解这一点，您必须查看生成的 _pxRes_ 参数的类型和值。</span><span class="sxs-lookup"><span data-stu-id="2a175-136">This does not mean that the function did not return an Excel error value; to find that out, you must look at the type and value of the resulting  _pxRes_ parameter.</span></span>  <br/> |
|<span data-ttu-id="2a175-137">1</span><span class="sxs-lookup"><span data-stu-id="2a175-137">1</span></span>  <br/> |<span data-ttu-id="2a175-138">**xlretAbort**</span><span class="sxs-lookup"><span data-stu-id="2a175-138">**xlretAbort**</span></span> <br/> |<span data-ttu-id="2a175-139">命令或函数在内部中止 (异常) 。</span><span class="sxs-lookup"><span data-stu-id="2a175-139">The command or function was terminated abnormally (internal abort).</span></span> <span data-ttu-id="2a175-140">如果 XLM 宏表通过调用 **CLOSE** 来关闭自身，或者如果 Excel内存不足，则会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="2a175-140">This can occur if an XLM macro sheet closes itself by calling **CLOSE**, or if Excel is out of memory.</span></span> <span data-ttu-id="2a175-141">如果Excel返回此错误，则调用函数必须立即退出。</span><span class="sxs-lookup"><span data-stu-id="2a175-141">If Excel returns this error, the calling function must exit immediately.</span></span> <span data-ttu-id="2a175-142">仅在退出之前，DLL 才允许调用 **xlFree。**</span><span class="sxs-lookup"><span data-stu-id="2a175-142">The DLL is permitted to call **xlFree** only before exiting.</span></span> <span data-ttu-id="2a175-143">不允许对 C API 进行所有其他调用。</span><span class="sxs-lookup"><span data-stu-id="2a175-143">All other calls to the C API are not permitted.</span></span> <span data-ttu-id="2a175-144">用户可以使用"文件"菜单上的"保存 **"** 命令以交互方式保存 **任何** 工作。</span><span class="sxs-lookup"><span data-stu-id="2a175-144">The user can save any work interactively by using the **Save** command on the **File** menu.</span></span>  <br/> |
|<span data-ttu-id="2a175-145">2</span><span class="sxs-lookup"><span data-stu-id="2a175-145">2</span></span>  <br/> |<span data-ttu-id="2a175-146">**xlretInvXlfn**</span><span class="sxs-lookup"><span data-stu-id="2a175-146">**xlretInvXlfn**</span></span> <br/> |<span data-ttu-id="2a175-147">提供了无效的函数编号。</span><span class="sxs-lookup"><span data-stu-id="2a175-147">An invalid function number was supplied.</span></span> <span data-ttu-id="2a175-148">如果使用 Xlcall.h 头文件的常量，则不应发生这种情况，除非调用的项在所运行的 Excel版本中不受支持。</span><span class="sxs-lookup"><span data-stu-id="2a175-148">If you are using constants from the Xlcall.h header file, this should not occur unless you are calling something that is not supported in the version of Excel you are running.</span></span>  <br/> |
|<span data-ttu-id="2a175-149">4 </span><span class="sxs-lookup"><span data-stu-id="2a175-149">4</span></span>  <br/> |<span data-ttu-id="2a175-150">**xlretInvCount**</span><span class="sxs-lookup"><span data-stu-id="2a175-150">**xlretInvCount**</span></span> <br/> |<span data-ttu-id="2a175-151">输入的参数数目无效。</span><span class="sxs-lookup"><span data-stu-id="2a175-151">An invalid number of arguments was entered.</span></span> <span data-ttu-id="2a175-152">在 2003 Excel版本中，任何函数可以接受的参数的最大数量为 30。</span><span class="sxs-lookup"><span data-stu-id="2a175-152">In versions up to Excel 2003, the maximum number of arguments any function can take is 30.</span></span> <span data-ttu-id="2a175-153">从 2007 Excel，最大数量为 255。</span><span class="sxs-lookup"><span data-stu-id="2a175-153">Starting in Excel 2007, the maximum number is 255.</span></span> <span data-ttu-id="2a175-154">一些参数需要固定或最小数量的参数。</span><span class="sxs-lookup"><span data-stu-id="2a175-154">Some require a fixed or minimum number of arguments.</span></span>  <br/> |
|<span data-ttu-id="2a175-155">8 </span><span class="sxs-lookup"><span data-stu-id="2a175-155">8</span></span>  <br/> |<span data-ttu-id="2a175-156">**xlretInvXloper**</span><span class="sxs-lookup"><span data-stu-id="2a175-156">**xlretInvXloper**</span></span> <br/> |<span data-ttu-id="2a175-157">向函数 **传递了无效的 XLOPER** 或 **XLOPER12，** 或者使用了错误类型的参数。</span><span class="sxs-lookup"><span data-stu-id="2a175-157">An invalid **XLOPER** or **XLOPER12** was passed to the function, or an argument of the wrong type was used.</span></span>  <br/> |
|<span data-ttu-id="2a175-158">16 </span><span class="sxs-lookup"><span data-stu-id="2a175-158">16</span></span>  <br/> |<span data-ttu-id="2a175-159">**xlretStackOvfl**</span><span class="sxs-lookup"><span data-stu-id="2a175-159">**xlretStackOvfl**</span></span> <br/> |<span data-ttu-id="2a175-160">发生堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="2a175-160">A stack overflow occurred.</span></span> <span data-ttu-id="2a175-161">使用 **xlStack** 监视堆栈上留下的空间量。</span><span class="sxs-lookup"><span data-stu-id="2a175-161">Use **xlStack** to monitor the amount of room left on the stack.</span></span> <span data-ttu-id="2a175-162">如果可能，避免 (在) 数组和结构上自动分配非常大的本地数组和结构;使其静态。</span><span class="sxs-lookup"><span data-stu-id="2a175-162">Avoid allocating very large local (automatic) arrays and structures on the stack where possible; make them static.</span></span> <span data-ttu-id="2a175-163"> (请注意，可能不会检测到堆栈溢出。) </span><span class="sxs-lookup"><span data-stu-id="2a175-163">(Note that a stack overflow might occur without being detected.)</span></span>  <br/> |
|<span data-ttu-id="2a175-164">32</span><span class="sxs-lookup"><span data-stu-id="2a175-164">32</span></span>  <br/> |<span data-ttu-id="2a175-165">**xlretFailed**</span><span class="sxs-lookup"><span data-stu-id="2a175-165">**xlretFailed**</span></span> <br/> |<span data-ttu-id="2a175-166">命令等效函数失败。</span><span class="sxs-lookup"><span data-stu-id="2a175-166">A command-equivalent function failed.</span></span> <span data-ttu-id="2a175-167">这等效于显示宏错误警告对话框的宏命令。</span><span class="sxs-lookup"><span data-stu-id="2a175-167">This is equivalent to a macro command displaying the macro error alert dialog box.</span></span>  <br/> |
|<span data-ttu-id="2a175-168">64</span><span class="sxs-lookup"><span data-stu-id="2a175-168">64</span></span>  <br/> |<span data-ttu-id="2a175-169">**xlretUncalced**</span><span class="sxs-lookup"><span data-stu-id="2a175-169">**xlretUncalced**</span></span> <br/> |<span data-ttu-id="2a175-170">试图取消引用尚未计算的单元格，因为它计划在当前单元格之后重新计算。</span><span class="sxs-lookup"><span data-stu-id="2a175-170">An attempt was made to dereference a cell that has not been calculated yet, because it is scheduled to be recalculated after the current cell.</span></span> <span data-ttu-id="2a175-171">在这种情况下，DLL 应立即将控件返回Excel。</span><span class="sxs-lookup"><span data-stu-id="2a175-171">In this case, the DLL should return control to Excel immediately.</span></span> <span data-ttu-id="2a175-172">仅在退出之前，DLL 才允许调用 **xlFree。**</span><span class="sxs-lookup"><span data-stu-id="2a175-172">The DLL is permitted to call **xlFree** only before exiting.</span></span> <span data-ttu-id="2a175-173">不允许对 C API 进行所有其他调用。</span><span class="sxs-lookup"><span data-stu-id="2a175-173">All other calls to the C API are not permitted.</span></span> <span data-ttu-id="2a175-174">有关哪些函数可以访问和无法访问尚未重新计算的单元格的值的信息，请参阅Excel、[函数和状态。](excel-commands-functions-and-states.md)</span><span class="sxs-lookup"><span data-stu-id="2a175-174">For more information about which functions can and cannot access the values of cells that have not been recalculated, see [Excel Commands, Functions, and States](excel-commands-functions-and-states.md).</span></span>  <br/> |
|<span data-ttu-id="2a175-175">128</span><span class="sxs-lookup"><span data-stu-id="2a175-175">128</span></span>  <br/> |<span data-ttu-id="2a175-176">**xlretNotThreadSafe**</span><span class="sxs-lookup"><span data-stu-id="2a175-176">**xlretNotThreadSafe**</span></span> <br/> |<span data-ttu-id="2a175-177">尝试在多线程重新计算工作簿期间调用非线程安全函数，也可能不是线程安全函数。</span><span class="sxs-lookup"><span data-stu-id="2a175-177">An attempt was made to call a function that is not, or might not be, thread safe during a multithreaded recalculation of the workbook.</span></span>  <br/> <span data-ttu-id="2a175-178">从 Excel 2007 开始，将返回此值，并且仅在声明为线程安全的 XLL 工作表函数中返回此值。</span><span class="sxs-lookup"><span data-stu-id="2a175-178">Starting in Excel 2007, this value is returned, and only within XLL worksheet functions declared as thread safe.</span></span>  <br/> |
|<span data-ttu-id="2a175-179">256</span><span class="sxs-lookup"><span data-stu-id="2a175-179">256</span></span>  <br/> |<span data-ttu-id="2a175-180">**xlRetInvAsynchronousContext**</span><span class="sxs-lookup"><span data-stu-id="2a175-180">**xlRetInvAsynchronousContext**</span></span> <br/> |<span data-ttu-id="2a175-181">异步函数句柄无效。</span><span class="sxs-lookup"><span data-stu-id="2a175-181">The asynchronous function handle is invalid.</span></span>  <br/> <span data-ttu-id="2a175-182">此值仅由 Excel 2010 使用。</span><span class="sxs-lookup"><span data-stu-id="2a175-182">This value is used only by Excel 2010.</span></span>  <br/> |
|<span data-ttu-id="2a175-183">512</span><span class="sxs-lookup"><span data-stu-id="2a175-183">512</span></span>  <br/> |<span data-ttu-id="2a175-184">**xlRetNotClusterSafe**</span><span class="sxs-lookup"><span data-stu-id="2a175-184">**xlRetNotClusterSafe**</span></span> <br/> |<span data-ttu-id="2a175-185">群集上不支持此调用。</span><span class="sxs-lookup"><span data-stu-id="2a175-185">The call is not supported on clusters.</span></span>  <br/> <span data-ttu-id="2a175-186">此值仅由 Excel 2010 使用。</span><span class="sxs-lookup"><span data-stu-id="2a175-186">This value is used only by Excel 2010.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2a175-187">备注</span><span class="sxs-lookup"><span data-stu-id="2a175-187">Remarks</span></span>

### <a name="valid-ifunction-values"></a><span data-ttu-id="2a175-188">有效的 iFunction 值</span><span class="sxs-lookup"><span data-stu-id="2a175-188">Valid iFunction values</span></span>

<span data-ttu-id="2a175-189">有效的 **iFunction** 值是 Xlcall.h 头文件中定义的任何 **xlf...** 或 **xlc...** 常量或以下任何特殊函数。</span><span class="sxs-lookup"><span data-stu-id="2a175-189">Valid **iFunction** values are any of the **xlf...** or **xlc...** constants defined in the Xlcall.h header file or any of the following special functions.</span></span> 
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a175-190">**xlAbort**</span><span class="sxs-lookup"><span data-stu-id="2a175-190">**xlAbort**</span></span> <br/> |<span data-ttu-id="2a175-191">**xlEnableXLMsgs**</span><span class="sxs-lookup"><span data-stu-id="2a175-191">**xlEnableXLMsgs**</span></span> <br/> |<span data-ttu-id="2a175-192">**xlGetInst**</span><span class="sxs-lookup"><span data-stu-id="2a175-192">**xlGetInst**</span></span> <br/> |<span data-ttu-id="2a175-193">**xlSheetNm**</span><span class="sxs-lookup"><span data-stu-id="2a175-193">**xlSheetNm**</span></span> <br/> |
|<span data-ttu-id="2a175-194">**xlCoerce**</span><span class="sxs-lookup"><span data-stu-id="2a175-194">**xlCoerce**</span></span> <br/> |<span data-ttu-id="2a175-195">**xlFree**</span><span class="sxs-lookup"><span data-stu-id="2a175-195">**xlFree**</span></span> <br/> |<span data-ttu-id="2a175-196">**xlGetName**</span><span class="sxs-lookup"><span data-stu-id="2a175-196">**xlGetName**</span></span> <br/> |<span data-ttu-id="2a175-197">**xlStack**</span><span class="sxs-lookup"><span data-stu-id="2a175-197">**xlStack**</span></span> <br/> |
|<span data-ttu-id="2a175-198">**xlDefineBinaryName**</span><span class="sxs-lookup"><span data-stu-id="2a175-198">**xlDefineBinaryName**</span></span> <br/> |<span data-ttu-id="2a175-199">**xlGetBinaryName**</span><span class="sxs-lookup"><span data-stu-id="2a175-199">**xlGetBinaryName**</span></span> <br/> |<span data-ttu-id="2a175-200">**xlSet**</span><span class="sxs-lookup"><span data-stu-id="2a175-200">**xlSet**</span></span> <br/> |<span data-ttu-id="2a175-201">**xlUDF**</span><span class="sxs-lookup"><span data-stu-id="2a175-201">**xlUDF**</span></span> <br/> |
|<span data-ttu-id="2a175-202">**xlDisableXLMsgs**</span><span class="sxs-lookup"><span data-stu-id="2a175-202">**xlDisableXLMsgs**</span></span> <br/> |<span data-ttu-id="2a175-203">**xlGetHwnd**</span><span class="sxs-lookup"><span data-stu-id="2a175-203">**xlGetHwnd**</span></span> <br/> |<span data-ttu-id="2a175-204">**xlSheetId**</span><span class="sxs-lookup"><span data-stu-id="2a175-204">**xlSheetId**</span></span> <br/> ||
   
### <a name="different-types-of-functions"></a><span data-ttu-id="2a175-205">不同类型的函数</span><span class="sxs-lookup"><span data-stu-id="2a175-205">Different Types of Functions</span></span>

 <span data-ttu-id="2a175-206">**Excel4** 和 **Excel12** 区分三类函数。</span><span class="sxs-lookup"><span data-stu-id="2a175-206">**Excel4** and **Excel12** distinguish among three classes of functions.</span></span> <span data-ttu-id="2a175-207">这些函数根据三种状态进行分类，Excel调用 DLL。</span><span class="sxs-lookup"><span data-stu-id="2a175-207">The functions are classified according to the three states in which Excel might call the DLL.</span></span> 
  
- <span data-ttu-id="2a175-208">当由于重新计算而从工作表调用 DLL 时，类 1 适用。</span><span class="sxs-lookup"><span data-stu-id="2a175-208">Class 1 applies when the DLL is called from a worksheet as a result of recalculation.</span></span> 
    
- <span data-ttu-id="2a175-209">当从函数宏中或从在类型文本中用数字符号 (#) 注册的工作表中调用 DLL 时，类 2 适用。</span><span class="sxs-lookup"><span data-stu-id="2a175-209">Class 2 applies when the DLL is called from within a function macro or from a worksheet where it was registered with a number sign (#) in the type text.</span></span>
    
- <span data-ttu-id="2a175-210">从对象、宏、菜单、工具栏、快捷键 **、ExecuteExcel4Macro** 方法或 **工具/宏/运行** 命令调用 DLL 时，类 3 适用。</span><span class="sxs-lookup"><span data-stu-id="2a175-210">Class 3 applies when a DLL is called from an object, macro, menu, toolbar, shortcut key, **ExecuteExcel4Macro** method, or the **Tools/Macro/Run** command.</span></span> <span data-ttu-id="2a175-211">有关详细信息，请参阅[Excel、函数和状态](excel-commands-functions-and-states.md)。</span><span class="sxs-lookup"><span data-stu-id="2a175-211">For more information, see [Excel Commands, Functions, and States](excel-commands-functions-and-states.md).</span></span>
    
<span data-ttu-id="2a175-212">下表显示了每个类中的有效函数。</span><span class="sxs-lookup"><span data-stu-id="2a175-212">The following table shows what functions are valid in each class.</span></span>
  
|<span data-ttu-id="2a175-213">**1 类**</span><span class="sxs-lookup"><span data-stu-id="2a175-213">**Class 1**</span></span>|<span data-ttu-id="2a175-214">**2 类**</span><span class="sxs-lookup"><span data-stu-id="2a175-214">**Class 2**</span></span>|<span data-ttu-id="2a175-215">**3 类**</span><span class="sxs-lookup"><span data-stu-id="2a175-215">**Class 3**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a175-216">任何工作表函数</span><span class="sxs-lookup"><span data-stu-id="2a175-216">Any worksheet function</span></span>  <br/> <span data-ttu-id="2a175-217">除 **xlSet** 之外的任何仅 **XLL xl...** 函数。</span><span class="sxs-lookup"><span data-stu-id="2a175-217">Any XLL-only **xl...** function except **xlSet**.</span></span>  <br/> <span data-ttu-id="2a175-218">**xlfCaller**</span><span class="sxs-lookup"><span data-stu-id="2a175-218">**xlfCaller**</span></span> <br/> |<span data-ttu-id="2a175-219">任何工作表函数</span><span class="sxs-lookup"><span data-stu-id="2a175-219">Any worksheet function</span></span>  <br/> <span data-ttu-id="2a175-220">除 **xlSet** 之外的任何 **xl... 函数**。</span><span class="sxs-lookup"><span data-stu-id="2a175-220">Any **xl...** function except **xlSet**.</span></span>  <br/> <span data-ttu-id="2a175-221">宏表函数（包括 **xlfCaller）** 返回值，但不执行影响工作区或任何打开的工作簿的操作。</span><span class="sxs-lookup"><span data-stu-id="2a175-221">Macro sheet functions, including **xlfCaller**, that return a value but perform no action that affects the workspace or any open workbook.</span></span>  <br/> |<span data-ttu-id="2a175-222">任何函数，包括 **xlSet** 和命令等效函数。</span><span class="sxs-lookup"><span data-stu-id="2a175-222">Any function, including **xlSet** and command-equivalent functions.</span></span>  <br/> |
   
### <a name="displaying-the-dialog-box-for-a-command-equivalent-function"></a><span data-ttu-id="2a175-223">显示活动函数Command-Equivalent对话框</span><span class="sxs-lookup"><span data-stu-id="2a175-223">Displaying the Dialog Box for a Command-Equivalent Function</span></span>

<span data-ttu-id="2a175-224">如果命令等效函数具有关联的对话框，可以在 **iFunction** 中设置 **xlPrompt** 位。</span><span class="sxs-lookup"><span data-stu-id="2a175-224">If a command-equivalent function has an associated dialog box, you can set the **xlPrompt** bit in **iFunction**.</span></span> <span data-ttu-id="2a175-225">这意味着，Excel命令之前显示相应的对话框。</span><span class="sxs-lookup"><span data-stu-id="2a175-225">This means that Excel displays the appropriate dialog box before carrying out the command.</span></span>
  
### <a name="writing-international-dlls"></a><span data-ttu-id="2a175-226">编写国际 DLL</span><span class="sxs-lookup"><span data-stu-id="2a175-226">Writing International DLLs</span></span>

<span data-ttu-id="2a175-227">如果在 **iFunction** 中设置 **xlIntl** 位，将执行函数或命令，就像从国际宏表调用它一样。</span><span class="sxs-lookup"><span data-stu-id="2a175-227">If you set the **xlIntl** bit in **iFunction**, the function or command is carried out as if it were being called from an International Macro Sheet.</span></span> <span data-ttu-id="2a175-228">这意味着该命令的行为与在美国版本的 Excel 上的行为一样，即使它运行在本地化版本上的 (也) 运行。</span><span class="sxs-lookup"><span data-stu-id="2a175-228">This means that the command behaves as it would on the U.S. version of Excel, even if it is running on an international (localized) version.</span></span>
  
### <a name="xlretuncalced-or-xlretabort"></a><span data-ttu-id="2a175-229">xlretUncalced 或 xlretAbort</span><span class="sxs-lookup"><span data-stu-id="2a175-229">xlretUncalced or xlretAbort</span></span>

<span data-ttu-id="2a175-230">收到这些返回值之一后，DLL 必须清除并返回控件，以Excel控件。</span><span class="sxs-lookup"><span data-stu-id="2a175-230">After receiving one of these return values, your DLL must clean up and return control to Excel immediately.</span></span> <span data-ttu-id="2a175-231">在收到这些Excel值之一后，将禁用通过 C API 的回调 **（xlFree** 除外）。</span><span class="sxs-lookup"><span data-stu-id="2a175-231">Callbacks into Excel via the C API, except **xlFree**, are disabled after receiving one of these return values.</span></span>
  
## <a name="example"></a><span data-ttu-id="2a175-232">示例</span><span class="sxs-lookup"><span data-stu-id="2a175-232">Example</span></span>

<span data-ttu-id="2a175-233">以下示例使用 **Excel12** 函数选择从中调用该函数的单元格。</span><span class="sxs-lookup"><span data-stu-id="2a175-233">The following example uses the **Excel12** function to select the cell from which it was called.</span></span> 
  
<span data-ttu-id="2a175-234">此代码示例是 Excel 2010 XLL SDK 中提供的较大示例的一部分，位于安装 SDK 的以下位置：</span><span class="sxs-lookup"><span data-stu-id="2a175-234">This code example is part of a larger example provided in the Excel 2010 XLL SDK, at the following location where you installed the SDK:</span></span>
  
<span data-ttu-id="2a175-235">\Samples\Example\Example.c.</span><span class="sxs-lookup"><span data-stu-id="2a175-235">\Samples\Example\Example.c.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a175-236">此函数在 xlcSelect (调用命令宏) 因此，它仅在从 XLM 宏表调用时有效。</span><span class="sxs-lookup"><span data-stu-id="2a175-236">This function calls a command macro (xlcSelect) and, therefore, works only if it is called from an XLM macro sheet.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="2a175-237">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a175-237">See also</span></span>



[<span data-ttu-id="2a175-238">Excel4v/Excel12v</span><span class="sxs-lookup"><span data-stu-id="2a175-238">Excel4v/Excel12v</span></span>](excel4v-excel12v.md)

