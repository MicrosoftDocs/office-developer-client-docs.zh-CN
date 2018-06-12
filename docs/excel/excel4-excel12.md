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
- excel4 函数 [excel 2007，] Excel12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 2404f10d-8641-4ee6-a909-1c5a26610f80
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 1c2c775cc7c5b051e4a1381df09ef29e79e2aca4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773736"
---
# <a name="excel4excel12"></a><span data-ttu-id="24fdc-104">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="24fdc-104">Excel4/Excel12</span></span>

 <span data-ttu-id="24fdc-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24fdc-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="24fdc-106">内部 Microsoft Excel 工作表函数、 宏工作表函数或命令或仅 XLL 特殊函数或命令，从调用 DLL/XLL 或代码资源中。</span><span class="sxs-lookup"><span data-stu-id="24fdc-106">Calls an internal Microsoft Excel worksheet function, macro sheet function or command, or XLL-only special function or command, from within a DLL/XLL or code resource.</span></span>
  
<span data-ttu-id="24fdc-107">所有的最新版本的 Excel 支持**Excel4**。</span><span class="sxs-lookup"><span data-stu-id="24fdc-107">All recent versions of Excel support **Excel4**.</span></span> <span data-ttu-id="24fdc-108">从 Excel 2007 开始，支持**Excel12** 。</span><span class="sxs-lookup"><span data-stu-id="24fdc-108">Starting in Excel 2007, **Excel12** is supported.</span></span> 
  
<span data-ttu-id="24fdc-109">仅当 Excel 已传递给 DLL 或 XLL 的控件时，可调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-109">These functions can be called only when Excel has passed control to the DLL or XLL.</span></span> <span data-ttu-id="24fdc-110">他们也称为 Excel 过后控件间接通过调用 Visual Basic for Applications (VBA)。</span><span class="sxs-lookup"><span data-stu-id="24fdc-110">They can also be called when Excel has passed control indirectly via a call to Visual Basic for Applications (VBA).</span></span> <span data-ttu-id="24fdc-111">他们不能在其他任何时间调用。</span><span class="sxs-lookup"><span data-stu-id="24fdc-111">They cannot be called at any other time.</span></span> <span data-ttu-id="24fdc-112">例如，他们不能调用为[DllMain](http://msdn.microsoft.com/library/base.dllmain%28Office.15%29.aspx)函数或其他时间在呼叫过程中时操作系统已调用 dll 文件，或从由 DLL 中创建的线程。</span><span class="sxs-lookup"><span data-stu-id="24fdc-112">For example, they cannot be called during calls to the [DllMain](http://msdn.microsoft.com/library/base.dllmain%28Office.15%29.aspx) function or other times when the operating system has called the DLL, or from a thread created by the DLL.</span></span> 
  
<span data-ttu-id="24fdc-113">[Excel4v 和 Excel12v](excel4v-excel12v.md)函数接受及其参数作为数组，，而**Excel4**和**Excel12**函数接受堆栈长度可变列表及其参数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-113">The [Excel4v and Excel12v](excel4v-excel12v.md) functions accept their arguments as an array, whereas the **Excel4** and **Excel12** functions accept their arguments as a variable-length list on the stack.</span></span> <span data-ttu-id="24fdc-114">在所有其他方面， **Excel4** **Excel4v**，相同的行为和**Excel12**行为与**Excel12v**相同。</span><span class="sxs-lookup"><span data-stu-id="24fdc-114">In all other respects, **Excel4** behaves the same as **Excel4v**, and **Excel12** behaves the same as **Excel12v**.</span></span>
  
```cs
int Excel4(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER argument1, ...);
int Excel12(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a><span data-ttu-id="24fdc-115">参数</span><span class="sxs-lookup"><span data-stu-id="24fdc-115">Parameters</span></span>

 <span data-ttu-id="24fdc-116">_iFunction_(**int**)</span><span class="sxs-lookup"><span data-stu-id="24fdc-116">_iFunction_ (**int**)</span></span>
  
<span data-ttu-id="24fdc-117">一个数字，指示命令、 函数或您要呼叫的特殊函数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-117">A number that indicates the command, function, or special function you want to call.</span></span> <span data-ttu-id="24fdc-118">有效_iFunction_值的列表，请参阅下的备注部分。</span><span class="sxs-lookup"><span data-stu-id="24fdc-118">For a list of valid  _iFunction_ values, see the following Remarks section.</span></span> 
  
 <span data-ttu-id="24fdc-119">_pxRes_（**LPXLOPER**或**LPXLOPER12**）</span><span class="sxs-lookup"><span data-stu-id="24fdc-119">_pxRes_ (**LPXLOPER** or **LPXLOPER12**)</span></span>
  
<span data-ttu-id="24fdc-120">一个指向 （与**Excel4**) **XLOPER**或**XLOPER12** （与**Excel12**) 将保存计算函数的结果。</span><span class="sxs-lookup"><span data-stu-id="24fdc-120">A pointer to an **XLOPER** (with **Excel4**) or an **XLOPER12** (with **Excel12**) that will hold the result of the evaluated function.</span></span>
  
 <span data-ttu-id="24fdc-121">_iCount_(**int**)</span><span class="sxs-lookup"><span data-stu-id="24fdc-121">_iCount_ (**int**)</span></span>
  
<span data-ttu-id="24fdc-122">将传递给函数的后续参数的数目。</span><span class="sxs-lookup"><span data-stu-id="24fdc-122">The number of subsequent arguments that will be passed to the function.</span></span> <span data-ttu-id="24fdc-123">在最多为 2003年版本的 Excel，这可以是介于 0 到 30 任意数量。</span><span class="sxs-lookup"><span data-stu-id="24fdc-123">In versions of Excel up to 2003, this can be any number from 0 through 30.</span></span> <span data-ttu-id="24fdc-124">从 Excel 2007 开始，这可以是任何介于 0 到 255。</span><span class="sxs-lookup"><span data-stu-id="24fdc-124">Starting in Excel 2007, this can be any number from 0 through 255.</span></span>
  
 <span data-ttu-id="24fdc-125">_argument1..._（**LPXLOPER**或**LPXLOPER12**）</span><span class="sxs-lookup"><span data-stu-id="24fdc-125">_argument1, ..._ (**LPXLOPER** or **LPXLOPER12**)</span></span>
  
<span data-ttu-id="24fdc-126">函数的可选参数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-126">The optional arguments to the function.</span></span> <span data-ttu-id="24fdc-127">所有参数都必须为**XLOPER**或**XLOPER12**值的指针。</span><span class="sxs-lookup"><span data-stu-id="24fdc-127">All arguments must be pointers to **XLOPER** or **XLOPER12** values.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="24fdc-128">返回值</span><span class="sxs-lookup"><span data-stu-id="24fdc-128">Return value</span></span>

<span data-ttu-id="24fdc-129">返回下列的整数 (**int**) 值之一。</span><span class="sxs-lookup"><span data-stu-id="24fdc-129">Returns one of the following integer (**int**) values.</span></span>
  
|<span data-ttu-id="24fdc-130">**值**</span><span class="sxs-lookup"><span data-stu-id="24fdc-130">**Value**</span></span>|<span data-ttu-id="24fdc-131">**返回代码**</span><span class="sxs-lookup"><span data-stu-id="24fdc-131">**Return code**</span></span>|<span data-ttu-id="24fdc-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="24fdc-132">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="24fdc-133">0</span><span class="sxs-lookup"><span data-stu-id="24fdc-133">0</span></span>  <br/> |<span data-ttu-id="24fdc-134">**xlretSuccess**</span><span class="sxs-lookup"><span data-stu-id="24fdc-134">**xlretSuccess**</span></span> <br/> |<span data-ttu-id="24fdc-135">已成功调用的函数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-135">The function was called successfully.</span></span> <span data-ttu-id="24fdc-136">这并不意味着函数没有返回 Excel 错误值;若要了解，您必须查看的类型和生成_pxRes_参数的值。</span><span class="sxs-lookup"><span data-stu-id="24fdc-136">This does not mean that the function did not return an Excel error value; to find that out, you must look at the type and value of the resulting  _pxRes_ parameter.</span></span>  <br/> |
|<span data-ttu-id="24fdc-137">1</span><span class="sxs-lookup"><span data-stu-id="24fdc-137">1</span></span>  <br/> |<span data-ttu-id="24fdc-138">**xlretAbort**</span><span class="sxs-lookup"><span data-stu-id="24fdc-138">**xlretAbort**</span></span> <br/> |<span data-ttu-id="24fdc-139">异常终止的命令或函数 （内部中止）。</span><span class="sxs-lookup"><span data-stu-id="24fdc-139">The command or function was terminated abnormally (internal abort).</span></span> <span data-ttu-id="24fdc-140">发生这种如果 XLM 宏工作表关闭本身通过调用**CLOSE**，或者 Excel 内存不足。</span><span class="sxs-lookup"><span data-stu-id="24fdc-140">This can occur if an XLM macro sheet closes itself by calling **CLOSE**, or if Excel is out of memory.</span></span> <span data-ttu-id="24fdc-141">如果 Excel 返回此错误，则必须立即退出调用的函数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-141">If Excel returns this error, the calling function must exit immediately.</span></span> <span data-ttu-id="24fdc-142">允许仅在退出之前调用**xlFree** DLL。</span><span class="sxs-lookup"><span data-stu-id="24fdc-142">The DLL is permitted to call **xlFree** only before exiting.</span></span> <span data-ttu-id="24fdc-143">不允许与 C API 的所有其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="24fdc-143">All other calls to the C API are not permitted.</span></span> <span data-ttu-id="24fdc-144">用户可以通过使用**文件**菜单上的**保存**命令以交互方式保存任何工作。</span><span class="sxs-lookup"><span data-stu-id="24fdc-144">The user can save any work interactively by using the **Save** command on the **File** menu.</span></span>  <br/> |
|<span data-ttu-id="24fdc-145">2</span><span class="sxs-lookup"><span data-stu-id="24fdc-145">2</span></span>  <br/> |<span data-ttu-id="24fdc-146">**xlretInvXlfn**</span><span class="sxs-lookup"><span data-stu-id="24fdc-146">**xlretInvXlfn**</span></span> <br/> |<span data-ttu-id="24fdc-147">提供无效的函数号。</span><span class="sxs-lookup"><span data-stu-id="24fdc-147">An invalid function number was supplied.</span></span> <span data-ttu-id="24fdc-148">如果使用 Xlcall.h 头文件中的常量，这不应发生除非您正在呼叫中的 Excel 运行版本不支持的内容。</span><span class="sxs-lookup"><span data-stu-id="24fdc-148">If you are using constants from the Xlcall.h header file, this should not occur unless you are calling something that is not supported in the version of Excel you are running.</span></span>  <br/> |
|<span data-ttu-id="24fdc-149">4</span><span class="sxs-lookup"><span data-stu-id="24fdc-149">4</span></span>  <br/> |<span data-ttu-id="24fdc-150">**xlretInvCount**</span><span class="sxs-lookup"><span data-stu-id="24fdc-150">**xlretInvCount**</span></span> <br/> |<span data-ttu-id="24fdc-151">输入无效的参数个数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-151">An invalid number of arguments was entered.</span></span> <span data-ttu-id="24fdc-152">在最多为 Excel 2003 的版本中，可以执行任何函数的参数的最大数量为 30。</span><span class="sxs-lookup"><span data-stu-id="24fdc-152">In versions up to Excel 2003, the maximum number of arguments any function can take is 30.</span></span> <span data-ttu-id="24fdc-153">启动 Excel 2007 中的最大数目为 255。</span><span class="sxs-lookup"><span data-stu-id="24fdc-153">Starting in Excel 2007, the maximum number is 255.</span></span> <span data-ttu-id="24fdc-154">一些需要固定或最小的参数数目。</span><span class="sxs-lookup"><span data-stu-id="24fdc-154">Some require a fixed or minimum number of arguments.</span></span>  <br/> |
|<span data-ttu-id="24fdc-155">8</span><span class="sxs-lookup"><span data-stu-id="24fdc-155">8</span></span>  <br/> |<span data-ttu-id="24fdc-156">**xlretInvXloper**</span><span class="sxs-lookup"><span data-stu-id="24fdc-156">**xlretInvXloper**</span></span> <br/> |<span data-ttu-id="24fdc-157">无效的**XLOPER**或**XLOPER12**已传递给该函数，或使用了错误类型的参数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-157">An invalid **XLOPER** or **XLOPER12** was passed to the function, or an argument of the wrong type was used.</span></span>  <br/> |
|<span data-ttu-id="24fdc-158">16</span><span class="sxs-lookup"><span data-stu-id="24fdc-158">16</span></span>  <br/> |<span data-ttu-id="24fdc-159">**xlretStackOvfl**</span><span class="sxs-lookup"><span data-stu-id="24fdc-159">**xlretStackOvfl**</span></span> <br/> |<span data-ttu-id="24fdc-160">栈溢出出现。</span><span class="sxs-lookup"><span data-stu-id="24fdc-160">A stack overflow occurred.</span></span> <span data-ttu-id="24fdc-161">使用**xlStack**监视堆栈中的聊天室左量。</span><span class="sxs-lookup"><span data-stu-id="24fdc-161">Use **xlStack** to monitor the amount of room left on the stack.</span></span> <span data-ttu-id="24fdc-162">避免在可能的情况下; 分配非常大的本地 （自动） 数组和堆栈上的结构使其静态。</span><span class="sxs-lookup"><span data-stu-id="24fdc-162">Avoid allocating very large local (automatic) arrays and structures on the stack where possible; make them static.</span></span> <span data-ttu-id="24fdc-163">（请注意，可能会被发现发生堆栈溢出）。</span><span class="sxs-lookup"><span data-stu-id="24fdc-163">(Note that a stack overflow might occur without being detected.)</span></span>  <br/> |
|<span data-ttu-id="24fdc-164">32</span><span class="sxs-lookup"><span data-stu-id="24fdc-164">32</span></span>  <br/> |<span data-ttu-id="24fdc-165">**xlretFailed**</span><span class="sxs-lookup"><span data-stu-id="24fdc-165">**xlretFailed**</span></span> <br/> |<span data-ttu-id="24fdc-166">一个命令等效函数失败。</span><span class="sxs-lookup"><span data-stu-id="24fdc-166">A command-equivalent function failed.</span></span> <span data-ttu-id="24fdc-167">这是等价于宏命令显示的宏错误警报对话框。</span><span class="sxs-lookup"><span data-stu-id="24fdc-167">This is equivalent to a macro command displaying the macro error alert dialog box.</span></span>  <br/> |
|<span data-ttu-id="24fdc-168">64</span><span class="sxs-lookup"><span data-stu-id="24fdc-168">64</span></span>  <br/> |<span data-ttu-id="24fdc-169">**xlretUncalced**</span><span class="sxs-lookup"><span data-stu-id="24fdc-169">**xlretUncalced**</span></span> <br/> |<span data-ttu-id="24fdc-170">尝试取消，尚未计算的单元格的引用，因为它计划的当前单元格之后重新计算。</span><span class="sxs-lookup"><span data-stu-id="24fdc-170">An attempt was made to dereference a cell that has not been calculated yet, because it is scheduled to be recalculated after the current cell.</span></span> <span data-ttu-id="24fdc-171">在这种情况下，将 DLL 应返回控件到 Excel 立即。</span><span class="sxs-lookup"><span data-stu-id="24fdc-171">In this case, the DLL should return control to Excel immediately.</span></span> <span data-ttu-id="24fdc-172">允许仅在退出之前调用**xlFree** DLL。</span><span class="sxs-lookup"><span data-stu-id="24fdc-172">The DLL is permitted to call **xlFree** only before exiting.</span></span> <span data-ttu-id="24fdc-173">不允许与 C API 的所有其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="24fdc-173">All other calls to the C API are not permitted.</span></span> <span data-ttu-id="24fdc-174">有关哪些函数可以和无法访问尚未重新计算的单元格的值的详细信息，请参阅[Excel 命令、 函数和状态](excel-commands-functions-and-states.md)。</span><span class="sxs-lookup"><span data-stu-id="24fdc-174">For more information about which functions can and cannot access the values of cells that have not been recalculated, see [Excel Commands, Functions, and States](excel-commands-functions-and-states.md).</span></span>  <br/> |
|<span data-ttu-id="24fdc-175">128</span><span class="sxs-lookup"><span data-stu-id="24fdc-175">128</span></span>  <br/> |<span data-ttu-id="24fdc-176">**xlretNotThreadSafe**</span><span class="sxs-lookup"><span data-stu-id="24fdc-176">**xlretNotThreadSafe**</span></span> <br/> |<span data-ttu-id="24fdc-177">尝试调用的函数，不工作，也可能不是，线程安全多线程重新计算工作簿的过程。</span><span class="sxs-lookup"><span data-stu-id="24fdc-177">An attempt was made to call a function that is not, or might not be, thread safe during a multithreaded recalculation of the workbook.</span></span>  <br/> <span data-ttu-id="24fdc-178">从 Excel 2007 开始，返回此值，并且仅在 XLL 工作表函数声明中 as 线程安全。</span><span class="sxs-lookup"><span data-stu-id="24fdc-178">Starting in Excel 2007, this value is returned, and only within XLL worksheet functions declared as thread safe.</span></span>  <br/> |
|<span data-ttu-id="24fdc-179">256</span><span class="sxs-lookup"><span data-stu-id="24fdc-179">256</span></span>  <br/> |<span data-ttu-id="24fdc-180">**xlRetInvAsynchronousContext**</span><span class="sxs-lookup"><span data-stu-id="24fdc-180">**xlRetInvAsynchronousContext**</span></span> <br/> |<span data-ttu-id="24fdc-181">无效的异步函数句柄。</span><span class="sxs-lookup"><span data-stu-id="24fdc-181">The asynchronous function handle is invalid.</span></span>  <br/> <span data-ttu-id="24fdc-182">此值只使用 Excel 2010。</span><span class="sxs-lookup"><span data-stu-id="24fdc-182">This value is used only by Excel 2010.</span></span>  <br/> |
|<span data-ttu-id="24fdc-183">512</span><span class="sxs-lookup"><span data-stu-id="24fdc-183">512</span></span>  <br/> |<span data-ttu-id="24fdc-184">**xlRetNotClusterSafe**</span><span class="sxs-lookup"><span data-stu-id="24fdc-184">**xlRetNotClusterSafe**</span></span> <br/> |<span data-ttu-id="24fdc-185">在群集上不支持呼叫。</span><span class="sxs-lookup"><span data-stu-id="24fdc-185">The call is not supported on clusters.</span></span>  <br/> <span data-ttu-id="24fdc-186">此值只使用 Excel 2010。</span><span class="sxs-lookup"><span data-stu-id="24fdc-186">This value is used only by Excel 2010.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="24fdc-187">备注</span><span class="sxs-lookup"><span data-stu-id="24fdc-187">Remarks</span></span>

### <a name="valid-ifunction-values"></a><span data-ttu-id="24fdc-188">有效 iFunction 值</span><span class="sxs-lookup"><span data-stu-id="24fdc-188">Valid iFunction values</span></span>

<span data-ttu-id="24fdc-189">有效**iFunction**值为任何 Xlcall.h 头文件或任何以下特殊功能中定义的**xlf...** 或**xlc...** 常量。</span><span class="sxs-lookup"><span data-stu-id="24fdc-189">Valid **iFunction** values are any of the **xlf...** or **xlc...** constants defined in the Xlcall.h header file or any of the following special functions.</span></span> 
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24fdc-190">**xlAbort**</span><span class="sxs-lookup"><span data-stu-id="24fdc-190">**xlAbort**</span></span> <br/> |<span data-ttu-id="24fdc-191">**xlEnableXLMsgs**</span><span class="sxs-lookup"><span data-stu-id="24fdc-191">**xlEnableXLMsgs**</span></span> <br/> |<span data-ttu-id="24fdc-192">**xlGetInst**</span><span class="sxs-lookup"><span data-stu-id="24fdc-192">**xlGetInst**</span></span> <br/> |<span data-ttu-id="24fdc-193">**xlSheetNm**</span><span class="sxs-lookup"><span data-stu-id="24fdc-193">**xlSheetNm**</span></span> <br/> |
|<span data-ttu-id="24fdc-194">**xlCoerce**</span><span class="sxs-lookup"><span data-stu-id="24fdc-194">**xlCoerce**</span></span> <br/> |<span data-ttu-id="24fdc-195">**xlFree**</span><span class="sxs-lookup"><span data-stu-id="24fdc-195">**xlFree**</span></span> <br/> |<span data-ttu-id="24fdc-196">**xlGetName**</span><span class="sxs-lookup"><span data-stu-id="24fdc-196">**xlGetName**</span></span> <br/> |<span data-ttu-id="24fdc-197">**xlStack**</span><span class="sxs-lookup"><span data-stu-id="24fdc-197">**xlStack**</span></span> <br/> |
|<span data-ttu-id="24fdc-198">**xlDefineBinaryName**</span><span class="sxs-lookup"><span data-stu-id="24fdc-198">**xlDefineBinaryName**</span></span> <br/> |<span data-ttu-id="24fdc-199">**xlGetBinaryName**</span><span class="sxs-lookup"><span data-stu-id="24fdc-199">**xlGetBinaryName**</span></span> <br/> |<span data-ttu-id="24fdc-200">**xlset，则**</span><span class="sxs-lookup"><span data-stu-id="24fdc-200">**xlSet**</span></span> <br/> |<span data-ttu-id="24fdc-201">**xlUDF**</span><span class="sxs-lookup"><span data-stu-id="24fdc-201">**xlUDF**</span></span> <br/> |
|<span data-ttu-id="24fdc-202">**xlDisableXLMsgs**</span><span class="sxs-lookup"><span data-stu-id="24fdc-202">**xlDisableXLMsgs**</span></span> <br/> |<span data-ttu-id="24fdc-203">**xlGetHwnd**</span><span class="sxs-lookup"><span data-stu-id="24fdc-203">**xlGetHwnd**</span></span> <br/> |<span data-ttu-id="24fdc-204">**xlSheetId**</span><span class="sxs-lookup"><span data-stu-id="24fdc-204">**xlSheetId**</span></span> <br/> ||
   
### <a name="different-types-of-functions"></a><span data-ttu-id="24fdc-205">不同类型的函数</span><span class="sxs-lookup"><span data-stu-id="24fdc-205">Different Types of Functions</span></span>

 <span data-ttu-id="24fdc-206">**Excel4**和**Excel12**区分三个类的函数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-206">**Excel4** and **Excel12** distinguish among three classes of functions.</span></span> <span data-ttu-id="24fdc-207">函数分类根据 Excel 可能在其中调用 DLL 的三种状态。</span><span class="sxs-lookup"><span data-stu-id="24fdc-207">The functions are classified according to the three states in which Excel might call the DLL.</span></span> 
  
- <span data-ttu-id="24fdc-208">DLL 调用从由于重新计算工作表时，将应用类 1。</span><span class="sxs-lookup"><span data-stu-id="24fdc-208">Class 1 applies when the DLL is called from a worksheet as a result of recalculation.</span></span> 
    
- <span data-ttu-id="24fdc-209">DLL 调用从函数宏内或从工作表它已注册以井号 （#） 中键入文本时，将应用类 2。</span><span class="sxs-lookup"><span data-stu-id="24fdc-209">Class 2 applies when the DLL is called from within a function macro or from a worksheet where it was registered with a number sign (#) in the type text.</span></span>
    
- <span data-ttu-id="24fdc-210">DLL 调用从对象、 宏、 菜单、 工具栏、 快捷键、 **ExecuteExcel4Macro**方法或**工具 / 宏 / 运行**命令时，将应用类 3。</span><span class="sxs-lookup"><span data-stu-id="24fdc-210">Class 3 applies when a DLL is called from an object, macro, menu, toolbar, shortcut key, **ExecuteExcel4Macro** method, or the **Tools/Macro/Run** command.</span></span> <span data-ttu-id="24fdc-211">有关详细信息，请参阅[Excel 命令、 函数和状态](excel-commands-functions-and-states.md)。</span><span class="sxs-lookup"><span data-stu-id="24fdc-211">For more information, see [Excel Commands, Functions, and States](excel-commands-functions-and-states.md).</span></span>
    
<span data-ttu-id="24fdc-212">下表显示了哪些功能可在每个类。</span><span class="sxs-lookup"><span data-stu-id="24fdc-212">The following table shows what functions are valid in each class.</span></span>
  
|<span data-ttu-id="24fdc-213">**类 1**</span><span class="sxs-lookup"><span data-stu-id="24fdc-213">**Class 1**</span></span>|<span data-ttu-id="24fdc-214">**类 2**</span><span class="sxs-lookup"><span data-stu-id="24fdc-214">**Class 2**</span></span>|<span data-ttu-id="24fdc-215">**类 3**</span><span class="sxs-lookup"><span data-stu-id="24fdc-215">**Class 3**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="24fdc-216">任何工作表函数</span><span class="sxs-lookup"><span data-stu-id="24fdc-216">Any worksheet function</span></span>  <br/> <span data-ttu-id="24fdc-217">除**xlset，则**任何仅 XLL **xl...** 函数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-217">Any XLL-only **xl...** function except **xlSet**.</span></span>  <br/> <span data-ttu-id="24fdc-218">**xlfCaller**</span><span class="sxs-lookup"><span data-stu-id="24fdc-218">**xlfCaller**</span></span> <br/> |<span data-ttu-id="24fdc-219">任何工作表函数</span><span class="sxs-lookup"><span data-stu-id="24fdc-219">Any worksheet function</span></span>  <br/> <span data-ttu-id="24fdc-220">除**xlset，则**任何**xl...** 函数。</span><span class="sxs-lookup"><span data-stu-id="24fdc-220">Any **xl...** function except **xlSet**.</span></span>  <br/> <span data-ttu-id="24fdc-221">宏工作表的功能，包括**xlfCaller**，返回一个值，但不会影响工作区的操作或任何打开的工作簿执行。</span><span class="sxs-lookup"><span data-stu-id="24fdc-221">Macro sheet functions, including **xlfCaller**, that return a value but perform no action that affects the workspace or any open workbook.</span></span>  <br/> |<span data-ttu-id="24fdc-222">任何函数，包括**xlset，则**和命令等效功能。</span><span class="sxs-lookup"><span data-stu-id="24fdc-222">Any function, including **xlSet** and command-equivalent functions.</span></span>  <br/> |
   
### <a name="displaying-the-dialog-box-for-a-command-equivalent-function"></a><span data-ttu-id="24fdc-223">对于命令等效函数显示对话框</span><span class="sxs-lookup"><span data-stu-id="24fdc-223">Displaying the Dialog Box for a Command-Equivalent Function</span></span>

<span data-ttu-id="24fdc-224">如果命令等效函数具有关联的对话框中，您可以设置**iFunction** **xlPrompt**位。</span><span class="sxs-lookup"><span data-stu-id="24fdc-224">If a command-equivalent function has an associated dialog box, you can set the **xlPrompt** bit in **iFunction**.</span></span> <span data-ttu-id="24fdc-225">这意味着 Excel 在执行命令之前显示适当的对话框。</span><span class="sxs-lookup"><span data-stu-id="24fdc-225">This means that Excel displays the appropriate dialog box before carrying out the command.</span></span>
  
### <a name="writing-international-dlls"></a><span data-ttu-id="24fdc-226">编写国际 Dll</span><span class="sxs-lookup"><span data-stu-id="24fdc-226">Writing International DLLs</span></span>

<span data-ttu-id="24fdc-227">如果在**iFunction**设置**xlIntl**位，函数或命令执行，如果已从国际宏工作表被调用。</span><span class="sxs-lookup"><span data-stu-id="24fdc-227">If you set the **xlIntl** bit in **iFunction**, the function or command is carried out as if it were being called from an International Macro Sheet.</span></span> <span data-ttu-id="24fdc-228">这意味着命令行为像在美国版本的 Excel，即使国际 （本地化） 版本上运行它。</span><span class="sxs-lookup"><span data-stu-id="24fdc-228">This means that the command behaves as it would on the U.S. version of Excel, even if it is running on an international (localized) version.</span></span>
  
### <a name="xlretuncalced-or-xlretabort"></a><span data-ttu-id="24fdc-229">xlretUncalced 或 xlretAbort</span><span class="sxs-lookup"><span data-stu-id="24fdc-229">xlretUncalced or xlretAbort</span></span>

<span data-ttu-id="24fdc-230">后接收这些返回的值之一，您的 DLL 必须清除并立即返回到 Excel 的控件。</span><span class="sxs-lookup"><span data-stu-id="24fdc-230">After receiving one of these return values, your DLL must clean up and return control to Excel immediately.</span></span> <span data-ttu-id="24fdc-231">导入 Excel 通过 C API，除**xlFree**，回调后接收其中一个返回值将被禁用。</span><span class="sxs-lookup"><span data-stu-id="24fdc-231">Callbacks into Excel via the C API, except **xlFree**, are disabled after receiving one of these return values.</span></span>
  
## <a name="example"></a><span data-ttu-id="24fdc-232">示例</span><span class="sxs-lookup"><span data-stu-id="24fdc-232">Example</span></span>

<span data-ttu-id="24fdc-233">下面的示例使用**Excel12**函数选择单元格调用它。</span><span class="sxs-lookup"><span data-stu-id="24fdc-233">The following example uses the **Excel12** function to select the cell from which it was called.</span></span> 
  
<span data-ttu-id="24fdc-234">此代码示例是示例的一个更大 Excel 2010 XLL SDK 安装 SDK 的以下位置中提供的一部分：</span><span class="sxs-lookup"><span data-stu-id="24fdc-234">This code example is part of a larger example provided in the Excel 2010 XLL SDK, at the following location where you installed the SDK:</span></span>
  
<span data-ttu-id="24fdc-235">\Samples\Example\Example.c。</span><span class="sxs-lookup"><span data-stu-id="24fdc-235">\Samples\Example\Example.c.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24fdc-236">此函数调用命令宏 (xlcSelect)，并因此，只有调用从 XLM 宏工作表。</span><span class="sxs-lookup"><span data-stu-id="24fdc-236">This function calls a command macro (xlcSelect) and, therefore, works only if it is called from an XLM macro sheet.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="24fdc-237">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24fdc-237">See also</span></span>



[<span data-ttu-id="24fdc-238">Excel4v/Excel12v</span><span class="sxs-lookup"><span data-stu-id="24fdc-238">Excel4v/Excel12v</span></span>](excel4v-excel12v.md)

