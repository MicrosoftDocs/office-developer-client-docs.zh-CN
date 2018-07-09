---
title: 从 DLL 或 XLL 调用 Excel
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- 对话框 [excel 2007]，调用 excel 命令、 Dll [Excel 2007]，导入 Excel，向 C API 函数 [Excel 2007]，传递参数调用命令 [Excel 2007] 中，调用带有对话框，命令 [Excel 2007]，可以从 DLL/XLL，Excel4 访问函数 [Excel 2007 中]，Excel12 函数 [Excel 2007，] XLCallVer 函数 [Excel 2007]，operRes 参数 [Excel 2007]、 函数 [Excel 2007]，可以从 DLL/XLL，Excel12v 访问函数 [Excel 2007] 中，仅 DLL 传递函数 [Excel 2007]，C API [Excel 2007]参数计数参数 [Excel 2007]、 国际版本中调用命令 [Excel 2007，]、 仅 DLL 命令 [Excel 2007]、 国际版本 [Excel 2007]、 调用函数和命令，将调用 Excel，Excel 4v 函数 [Xll [Excel 2007]Excel 2007] xlfn 参数 [Excel 2007]，[Excel 2007]，函数调用国际版本中
localization_priority: Normal
ms.assetid: 616e3def-e4ec-4f3c-bc65-3b92710da1e6
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 3f36d2f59b7f5bef9f9ffdca4d13e95c788bf113
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773689"
---
# <a name="calling-into-excel-from-the-dll-or-xll"></a><span data-ttu-id="cc8aa-104">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="cc8aa-104">Calling into Excel from the DLL or XLL</span></span>

<span data-ttu-id="cc8aa-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc8aa-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="cc8aa-106">Microsoft Excel 使您能够访问内置 Excel 命令、 工作表功能和宏工作表函数的 DLL。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-106">Microsoft Excel enables your DLL to access built-in Excel commands, worksheet functions, and macro sheet functions.</span></span> <span data-ttu-id="cc8aa-107">这些是可同时从 DLL 命令和从 Visual Basic for Applications (VBA)，并从注册的 XLL 命令和由 Excel 直接调用的函数调用的函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-107">These are available both from DLL commands and functions called from Visual Basic for Applications (VBA), and from registered XLL commands and functions called directly by Excel.</span></span>
  
## <a name="excel4-excel4v-excel12-and-excel12v-functions"></a><span data-ttu-id="cc8aa-108">Excel4、 Excel4v、 Excel12 和 Excel12v 函数</span><span class="sxs-lookup"><span data-stu-id="cc8aa-108">Excel4, Excel4v, Excel12, and Excel12v Functions</span></span>

<span data-ttu-id="cc8aa-109">Excel 启用 DLL 以通过[Excel4](excel4-excel12.md)、 [Excel4v](excel4v-excel12v.md)、 [Excel12](excel4-excel12.md)和[Excel12v](excel4v-excel12v.md)的回调函数中访问的命令和功能。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-109">Excel enables your DLL to access the commands and functions through the callback functions [Excel4](excel4-excel12.md), [Excel4v](excel4v-excel12v.md), [Excel12](excel4-excel12.md), and [Excel12v](excel4v-excel12v.md).</span></span>
  
<span data-ttu-id="cc8aa-110">Excel 版本 4 中引入的**Excel4**和**Excel4v**函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-110">The **Excel4** and **Excel4v** functions were introduced in Excel version 4.</span></span> <span data-ttu-id="cc8aa-111">他们使用**XLOPER**数据结构。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-111">They work with the **XLOPER** data structure.</span></span> <span data-ttu-id="cc8aa-112">Excel 2007 中引入的两个新回调函数， **Excel12**和**Excel12v**，使用**XLOPER12**数据结构。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-112">Excel 2007 introduced two new callback functions, **Excel12** and **Excel12v**, which work with the **XLOPER12** data structure.</span></span> <span data-ttu-id="cc8aa-113">由库 Xlcall32.lib，必须包括在您的 DLL 或 XLL 项目导出的**Excel4**和**Excel4v**函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-113">The **Excel4** and **Excel4v** functions are exported by the library Xlcall32.lib, which must be included in your DLL or XLL project.</span></span> <span data-ttu-id="cc8aa-114">在 SDK c + + 源文件 Xlcall.cpp，如果您想要使用**XLOPER12**结构访问 Excel 功能必须包含在您的项目中包含**Excel12**和**Excel12v** 。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-114">**Excel12** and **Excel12v** are included in the SDK C++ source file Xlcall.cpp, which must be included in your project if you want to access Excel functionality by using **XLOPER12** structures.</span></span> 
  
<span data-ttu-id="cc8aa-115">下面的代码演示以下四个函数的函数的原型。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-115">The following code shows the function prototypes for these four functions.</span></span> <span data-ttu-id="cc8aa-116">第二个参数是一个指向中的第一对**XLOPER**和一个指向中的第二个对**XLOPER12**处在于前, 三个参数都是相同的。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-116">The first three arguments are the same except that the second argument is a pointer to an **XLOPER** in the first pair and a pointer to an **XLOPER12** in the second pair.</span></span> <span data-ttu-id="cc8aa-117">调用约定 **_cdecl** **Excel4**和**Excel12**允许变量参数列表中。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-117">The calling convention is **_cdecl** in **Excel4** and **Excel12** to permit the variable argument lists.</span></span> <span data-ttu-id="cc8aa-118">省略号表示为**Excel4** **XLOPER**值和**Excel12** **XLOPER12**值的指针。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-118">The ellipsis represents pointers to **XLOPER** values for **Excel4** and **XLOPER12** values for **Excel12**.</span></span> <span data-ttu-id="cc8aa-119">指针数等于_计数_参数的值。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-119">The number of pointers equals the value of the  _count_ parameter.</span></span> 
  
<span data-ttu-id="cc8aa-120">**所有版本的 Excel**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-120">**All versions of Excel**</span></span>
  
 `int _cdecl Excel4(int xlfn, LPXLOPER operRes, int count,... );`
  
 `int pascal Excel4v(int xlfn, LPXLOPER operRes, int count, LPXLOPER opers[]);`
  
<span data-ttu-id="cc8aa-121">**从 Excel 2007**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-121">**Starting in Excel 2007**</span></span>
  
 `int _cdecl Excel12(int xlfn, LPXLOPER12 operRes, int count,... );`
  
 `int pascal Excel12v(int xlfn, LPXLOPER12 operRes, int count, LPXLOPER12 opers[]);`
  
<span data-ttu-id="cc8aa-122">为了能够调用**Excel4**、 **Excel4v**、 **Excel12**或**Excel12v**DLL，Excel 必须对 DLL 通过控件。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-122">For the DLL to be able to call **Excel4**, **Excel4v**, **Excel12**, or **Excel12v**, Excel must pass control to the DLL.</span></span> <span data-ttu-id="cc8aa-123">这意味着这些 C API 回调，可以调用仅在以下方案：</span><span class="sxs-lookup"><span data-stu-id="cc8aa-123">This means that these C API callbacks can be called only in the following scenarios:</span></span>
  
- <span data-ttu-id="cc8aa-124">从 Excel XLL 命令呼叫直接或通过 VBA。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-124">From within an XLL command that Excel has called directly or via VBA.</span></span>
    
- <span data-ttu-id="cc8aa-125">从 XLL 工作表或宏工作表函数中的 Excel 呼叫直接或通过 VBA。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-125">From within an XLL worksheet or macro sheet function that Excel has called directly or via VBA.</span></span>
    
<span data-ttu-id="cc8aa-126">在下列情况下，不能调用 Excel C API:</span><span class="sxs-lookup"><span data-stu-id="cc8aa-126">You cannot call the Excel C API in the following scenarios:</span></span>
  
- <span data-ttu-id="cc8aa-127">从操作系统事件 （例如，从[DllMain](http://msdn.microsoft.com/library/base.dllmain%28Office.15%29.aspx)函数）。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-127">From an operating system event (for example, from the [DllMain](http://msdn.microsoft.com/library/base.dllmain%28Office.15%29.aspx) function).</span></span> 
    
- <span data-ttu-id="cc8aa-128">从您的 DLL 创建后台线程。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-128">From a background thread that your DLL created.</span></span>
    
### <a name="return-values"></a><span data-ttu-id="cc8aa-129">返回值</span><span class="sxs-lookup"><span data-stu-id="cc8aa-129">Return values</span></span>

<span data-ttu-id="cc8aa-130">所有四个这些函数都返回一个整数值，以告知呼叫者的函数或命令是否成功调用。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-130">All four of these functions return an integer value that informs the caller whether the function or command was called successfully.</span></span> <span data-ttu-id="cc8aa-131">返回的值可以是以下任一项：</span><span class="sxs-lookup"><span data-stu-id="cc8aa-131">The values returned can be any of the following:</span></span>
  
|<span data-ttu-id="cc8aa-132">**返回值**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-132">**Return value**</span></span>|<span data-ttu-id="cc8aa-133">**作为 Xlcall.h 中定义**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-133">**Defined in Xlcall.h as**</span></span>|<span data-ttu-id="cc8aa-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-134">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cc8aa-135">0</span><span class="sxs-lookup"><span data-stu-id="cc8aa-135">0</span></span>  <br/> |<span data-ttu-id="cc8aa-136">**xlretSuccess**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-136">**xlretSuccess**</span></span> <br/> |<span data-ttu-id="cc8aa-137">该函数或命令成功执行。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-137">The function or command executed successfully.</span></span> <span data-ttu-id="cc8aa-138">这并不意味着执行已出现错误。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-138">This does not mean that the execution was error free.</span></span> <span data-ttu-id="cc8aa-139">例如， **Excel4**无法返回**xlretSuccess**时调用的函数**查找**，即使为将对它求值 **#VALUE ！**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-139">For example, **Excel4** could return **xlretSuccess** when calling the function **FIND**, even though it evaluated to **#VALUE!**</span></span> <span data-ttu-id="cc8aa-140">因为找不到搜索文本。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-140">because the search text could not be found.</span></span> <span data-ttu-id="cc8aa-141">您应该检查的类型和值返回**XLOPER/XLOPER12**这种可能性。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-141">You should inspect the type and value of the returned **XLOPER/XLOPER12** where this is a possibility.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-142">1</span><span class="sxs-lookup"><span data-stu-id="cc8aa-142">1</span></span>  <br/> |<span data-ttu-id="cc8aa-143">**xlretAbort**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-143">**xlretAbort**</span></span> <br/> |<span data-ttu-id="cc8aa-144">用户单击**取消**按钮，或按 ESC 键停止命令宏。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-144">A command macro was stopped by the user clicking the **CANCEL** button or pressing the ESC key.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-145">2</span><span class="sxs-lookup"><span data-stu-id="cc8aa-145">2</span></span>  <br/> |<span data-ttu-id="cc8aa-146">**xlretInvXlfn**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-146">**xlretInvXlfn**</span></span> <br/> |<span data-ttu-id="cc8aa-147">提供的函数或命令代码无效。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-147">The supplied function or command code is not valid.</span></span> <span data-ttu-id="cc8aa-148">调用函数没有调用的函数或命令的权限时，会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-148">This error can occur when the calling function does not have permission to call the function or command.</span></span> <span data-ttu-id="cc8aa-149">例如，工作表函数不能调用宏工作表信息函数或命令函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-149">For example, a worksheet function cannot call a macro sheet information function or a command function.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-150">4</span><span class="sxs-lookup"><span data-stu-id="cc8aa-150">4</span></span>  <br/> |<span data-ttu-id="cc8aa-151">**xlretInvCount**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-151">**xlretInvCount**</span></span> <br/> |<span data-ttu-id="cc8aa-152">不正确的调用中提供的参数数目。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-152">The number of arguments supplied in the call is not correct.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-153">8</span><span class="sxs-lookup"><span data-stu-id="cc8aa-153">8</span></span>  <br/> |<span data-ttu-id="cc8aa-154">**xlretInvXloper**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-154">**xlretInvXloper**</span></span> <br/> |<span data-ttu-id="cc8aa-155">一个或多个参数**XLOPER**或**XLOPER12**值是不正确地形成或填充。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-155">One or more of the argument **XLOPER** or **XLOPER12** values are not properly formed or populated.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-156">16</span><span class="sxs-lookup"><span data-stu-id="cc8aa-156">16</span></span>  <br/> |<span data-ttu-id="cc8aa-157">**xlretStackOvfl**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-157">**xlretStackOvfl**</span></span> <br/> |<span data-ttu-id="cc8aa-158">Excel 检测到风险操作可能溢出其堆栈和，因此，不调用此函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-158">Excel detected a risk that the operation might overflow its stack and, therefore, did not call the function.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-159">32</span><span class="sxs-lookup"><span data-stu-id="cc8aa-159">32</span></span>  <br/> |<span data-ttu-id="cc8aa-160">**xlretFailed**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-160">**xlretFailed**</span></span> <br/> |<span data-ttu-id="cc8aa-161">命令或函数失败原因不描述其他返回值之一。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-161">The command or function failed for a reason not described by one of the other return values.</span></span> <span data-ttu-id="cc8aa-162">操作需要太多的内存，例如，将失败并出现此错误。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-162">An operation that would require too much memory, for example, would fail with this error.</span></span> <span data-ttu-id="cc8aa-163">这可能是在试图将一个非常大**xltypeMulti**数组引用转换使用[xlCoerce](http://msdn.microsoft.com/library/guid_9d47c16c-a7e7-4998-b594-9cf001827b7b%28Office.15%29.aspx)函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-163">This could happen during an attempt to convert a very large reference to an **xltypeMulti** array by using the [xlCoerce](http://msdn.microsoft.com/library/guid_9d47c16c-a7e7-4998-b594-9cf001827b7b%28Office.15%29.aspx) function.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-164">64</span><span class="sxs-lookup"><span data-stu-id="cc8aa-164">64</span></span>  <br/> |<span data-ttu-id="cc8aa-165">**xlretUncalced**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-165">**xlretUncalced**</span></span> <br/> |<span data-ttu-id="cc8aa-166">尝试检索未计算的单元格的值的操作。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-166">The operation attempted to retrieve the value of an uncalculated cell.</span></span> <span data-ttu-id="cc8aa-167">若要保留在 Excel 中的重新计算完整性，工作表函数不允许这样做。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-167">To preserve recalculation integrity in Excel, worksheet functions are not permitted to do this.</span></span> <span data-ttu-id="cc8aa-168">但是，XLL 命令和函数注册为宏工作表函数允许访问未计算的单元格的值。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-168">However, XLL commands and functions registered as macro sheet functions are permitted to access uncalculated cell values.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-169">128</span><span class="sxs-lookup"><span data-stu-id="cc8aa-169">128</span></span>  <br/> |<span data-ttu-id="cc8aa-170">**xlretNotThreadSafe**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-170">**xlretNotThreadSafe**</span></span> <br/> |<span data-ttu-id="cc8aa-171">（在 Excel 2007 中从开始）注册为线程安全的 XLL 工作表函数尝试调用的 C API 函数，不是线程安全。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-171">(Starting in Excel 2007) An XLL worksheet function registered as thread safe attempted to call a C API function that is not thread safe.</span></span> <span data-ttu-id="cc8aa-172">例如，线程安全函数不能调用 XLM 函数**xlfGetCell**。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-172">For example, a thread-safe function cannot call the XLM function **xlfGetCell**.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-173">256</span><span class="sxs-lookup"><span data-stu-id="cc8aa-173">256</span></span>  <br/> |<span data-ttu-id="cc8aa-174">**xlRetInvAsynchronousContext**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-174">**xlRetInvAsynchronousContext**</span></span> <br/> |<span data-ttu-id="cc8aa-175">（从开始在 Excel 2010 中）无效的异步函数句柄。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-175">(Starting in Excel 2010) The asynchronous function handle is invalid.</span></span>  <br/> |
|<span data-ttu-id="cc8aa-176">512</span><span class="sxs-lookup"><span data-stu-id="cc8aa-176">512</span></span>  <br/> |<span data-ttu-id="cc8aa-177">**xlretNotClusterSafe**</span><span class="sxs-lookup"><span data-stu-id="cc8aa-177">**xlretNotClusterSafe**</span></span> <br/> |<span data-ttu-id="cc8aa-178">（从开始在 Excel 2010 中）在群集上不支持呼叫。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-178">(Starting in Excel 2010) The call is not supported on clusters.</span></span>  <br/> |
   
<span data-ttu-id="cc8aa-179">如果该函数返回故障值之一表中 （即，它不会返回**xlretSuccess**），也将被**XLOPER**或**XLOPER12**返回值设置为 **#VALUE ！**。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-179">If the function returns one of the failure values in the table (that is, it does not return **xlretSuccess**), the **XLOPER** or **XLOPER12** return value will also be set to **#VALUE!**.</span></span> <span data-ttu-id="cc8aa-180">在某些情况下，检查的这可能是足够测试的成功，但应注意呼叫可以返回两个**xlretSuccess**和 **#VALUE ！**。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-180">In certain circumstances, checking for this might be a sufficient test of success, but you should note that a call can return both **xlretSuccess** and **#VALUE!**.</span></span>
  
<span data-ttu-id="cc8aa-181">如果**xlretUncalced**或**xlretAbort**中的 C API 结果调用，DLL 或 XLL 代码应返回控件联接 Excel （而非[xlfree](http://msdn.microsoft.com/library/guid_8ce2eef2-0138-495d-b6cb-bbb727a3cda4%28Office.15%29.aspx)函数调用发布 Excel 分配内存的任何其他 C API 调用之前资源中**XLOPER**和**XLOPER12**值）。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-181">If a call to the C API results in either **xlretUncalced** or **xlretAbort**, your DLL or XLL code should return control to Excel before making any other C API calls (other than calls to the [xlfree](http://msdn.microsoft.com/library/guid_8ce2eef2-0138-495d-b6cb-bbb727a3cda4%28Office.15%29.aspx) function to release Excel-allocated memory resources in **XLOPER** and **XLOPER12** values).</span></span> 
  
### <a name="command-or-function-enumeration-argument-xlfn"></a><span data-ttu-id="cc8aa-182">命令或函数枚举参数： xlfn</span><span class="sxs-lookup"><span data-stu-id="cc8aa-182">Command or Function Enumeration Argument: xlfn</span></span>

<span data-ttu-id="cc8aa-183">_Xlfn_参数是第一个参数给回调函数和是 32 位有符号的整数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-183">The  _xlfn_ argument is the first argument to the callback functions and is a 32-bit signed integer.</span></span> <span data-ttu-id="cc8aa-184">下面的示例中所示，其值应为 Xlcall.h，SDK 标头文件中定义的函数或命令枚举之一。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-184">Its value should be one of the function or command enumerations defined in the SDK header file Xlcall.h, as shown in the following example.</span></span> 
  
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

<span data-ttu-id="cc8aa-185">所有的工作表和宏工作表函数位于范围为 0 (**xlfCount**) 通过 0x0fff 十六进制，虽然，最大分配 Excel 2013 中的号码是 547 小数，0x0223 十六进制 (**xlfFloor_precise**)。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-185">All worksheet and macro sheet functions are in the range from 0 (**xlfCount**) through 0x0fff hexadecimal, although the highest assigned number in Excel 2013 is 547 decimal, 0x0223 hexadecimal (**xlfFloor_precise**).</span></span>
  
<span data-ttu-id="cc8aa-186">所有命令函数都是介于 0x8000 十六进制 (**xlcBeep**) 通过 0x8fff 十六进制，尽管 Excel 2013 中的最大分配的数字 0x8328 十六进制 (**xlcHideallInkannots**)。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-186">All command functions are in the range from 0x8000 hexadecimal (**xlcBeep**) through 0x8fff hexadecimal, although the highest assigned number in Excel 2013 is 0x8328 hexadecimal (**xlcHideallInkannots**).</span></span> <span data-ttu-id="cc8aa-187">这些为标头文件中定义`(n | xlCommand)`其中`n`是十进制数大于或等于 0 和**xlCommand**定义为 0x8000 十六进制。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-187">These are defined in the header file as  `(n | xlCommand)` where  `n` is a decimal number greater than or equal to 0 and **xlCommand** is defined as 0x8000 hexadecimal.</span></span> 
  
### <a name="invoking-excel-commands-that-use-dialog-boxes"></a><span data-ttu-id="cc8aa-188">调用 Excel 命令使用对话框</span><span class="sxs-lookup"><span data-stu-id="cc8aa-188">Invoking Excel Commands that Use Dialog Boxes</span></span>

<span data-ttu-id="cc8aa-189">一些命令代码对应于在 Excel 中使用对话框的操作。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-189">Some of the command codes correspond to actions in Excel that use dialog boxes.</span></span> <span data-ttu-id="cc8aa-190">例如， **xlcFileDelete**采用单个参数： 文件名或掩码。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-190">For example, **xlcFileDelete** takes a single argument: a file name or mask.</span></span> <span data-ttu-id="cc8aa-191">这可以调用与对话框中，以便用户有机会取消或修改删除操作。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-191">This can be invoked with the dialog box so that the user has the opportunity to cancel or modify the delete operation.</span></span> <span data-ttu-id="cc8aa-192">它还可以调用对话框的情况下没有任何进一步的交互，假定存在和呼叫者具有的权限在这种情况下删除的文件。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-192">It can also be called without the dialog box, in which case the file or files are deleted without any further interaction, assuming they exist and the caller has permission.</span></span> <span data-ttu-id="cc8aa-193">若要在其对话框窗体中调用此类命令，必须按 0x1000 (**xlPrompt**) 中使用按位 OR 运算组合枚举的命令。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-193">To call such commands in their dialog box form, the command enumeration must be combined by using the bitwise OR operation with 0x1000 (**xlPrompt**).</span></span>
  
<span data-ttu-id="cc8aa-194">下面的代码示例删除匹配掩码 my_data 在当前目录中的文件\*.bak，参数为 true 时才显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-194">The following code example deletes files in the current directory matching the mask my_data\*.bak, displaying a dialog box only if the argument is true.</span></span>
  
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

### <a name="calling-functions-and-commands-in-international-versions"></a><span data-ttu-id="cc8aa-195">调用的函数和国际版本中的命令</span><span class="sxs-lookup"><span data-stu-id="cc8aa-195">Calling Functions and Commands in International Versions</span></span>

<span data-ttu-id="cc8aa-196">您可以配置 Excel 以多种语言显示函数和 XLM 命令名称。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-196">You can configure Excel to display functions and XLM command names in a variety of languages.</span></span> <span data-ttu-id="cc8aa-197">某些 C API 命令和函数运行对解释为函数或命令名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-197">Some C API commands and functions operate on strings that are interpreted as function or command names.</span></span> <span data-ttu-id="cc8aa-198">例如， **xlcFormula**采用字符串参数的旨在放置在指定的单元格。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-198">For example, **xlcFormula** takes a string argument that is intended to be placed in a specified cell.</span></span> <span data-ttu-id="cc8aa-199">为您外接程序来处理所有语言设置，可以提供英语字符串名称和函数或命令枚举中设置的位 0x2000 (**xlIntl**)。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-199">For your add-in to work with all language settings, you can supply the English string names and set the bit 0x2000 (**xlIntl**) in the function or command enumeration.</span></span>
  
<span data-ttu-id="cc8aa-200">下面的代码示例将放在的等效项`=SUM(X1:X100)`活动工作表的单元格 A2 中。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-200">The following code example places the equivalent of  `=SUM(X1:X100)` in cell A2 on the active sheet.</span></span> <span data-ttu-id="cc8aa-201">请注意，它使用框架函数， **TempActiveRef**，来创建的临时外部引用**XLOPER**。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-201">Note that it uses the Framework function, **TempActiveRef**, to create a temporary external reference **XLOPER**.</span></span> <span data-ttu-id="cc8aa-202">公式中 A2 显示正确的区域设置确定语言 (例如，`=SOMME(X1:X100)`如果语言是法语)。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-202">The formula will appear in A2 in the correct locale-determined language (for example,  `=SOMME(X1:X100)` if the language is French).</span></span> 
  
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
> <span data-ttu-id="cc8aa-203">到**Excel12**调用的结果不是必需的因为无法作为第二个参数，而不是**xResult**的地址传递零 (NULL)。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-203">Because the result of the call to **Excel12** is not required, zero (NULL) could be passed as the second argument instead of the address of **xResult**.</span></span> <span data-ttu-id="cc8aa-204">这是详细讨论一节中。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-204">This is discussed more in the next section.</span></span> 
  
### <a name="dll-only-functions-and-commands"></a><span data-ttu-id="cc8aa-205">仅 DLL 函数和命令</span><span class="sxs-lookup"><span data-stu-id="cc8aa-205">DLL-Only Functions and Commands</span></span>

<span data-ttu-id="cc8aa-206">Excel 支持函数只能从 DLL 或 XLL 可访问的一个小数字。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-206">Excel supports a small number of functions that are only accessible from a DLL or XLL.</span></span> <span data-ttu-id="cc8aa-207">这些为标头文件中定义`(n | xlSpecial)`其中`n`是十进制数大于或等于 0 和`xlSpecial`定义为 0x4000 十六进制。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-207">These are defined in the header file as  `(n | xlSpecial)` where  `n` is a decimal number greater than or equal to 0 and  `xlSpecial` is defined as 0x4000 hexadecimal.</span></span> <span data-ttu-id="cc8aa-208">下表中列出并[API 函数引用](excel-xll-sdk-api-function-reference.md)中记录这些函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-208">These functions are listed in the following table and documented in the [API Function Reference](excel-xll-sdk-api-function-reference.md).</span></span>
  
||||
|:-----|:-----|:-----|
|[<span data-ttu-id="cc8aa-209">xlFree</span><span class="sxs-lookup"><span data-stu-id="cc8aa-209">xlFree</span></span>](xlfree.md) <br/> |<span data-ttu-id="cc8aa-210">0</span><span class="sxs-lookup"><span data-stu-id="cc8aa-210">0</span></span> | <span data-ttu-id="cc8aa-211">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-211">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-212">释放 Excel 分配内存资源。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-212">Frees Excel-allocated memory resources.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-213">xlStack</span><span class="sxs-lookup"><span data-stu-id="cc8aa-213">xlStack</span></span>](xlstack.md) <br/> |<span data-ttu-id="cc8aa-214">1</span><span class="sxs-lookup"><span data-stu-id="cc8aa-214">1</span></span> | <span data-ttu-id="cc8aa-215">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-215">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-216">返回 Excel 堆栈上的可用空间。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-216">Returns the free space on the Excel stack.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-217">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="cc8aa-217">xlCoerce</span></span>](xlcoerce.md) <br/> |<span data-ttu-id="cc8aa-218">2</span><span class="sxs-lookup"><span data-stu-id="cc8aa-218">2</span></span> | <span data-ttu-id="cc8aa-219">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-219">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-220">**XLOPER**和**XLOPER12**类型之间进行转换</span><span class="sxs-lookup"><span data-stu-id="cc8aa-220">Converts between **XLOPER** and **XLOPER12** types</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-221">xlset，则</span><span class="sxs-lookup"><span data-stu-id="cc8aa-221">xlSet</span></span>](xlset.md) <br/> |<span data-ttu-id="cc8aa-222">3</span><span class="sxs-lookup"><span data-stu-id="cc8aa-222">3</span></span> | <span data-ttu-id="cc8aa-223">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-223">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-224">提供快速设置单元格的值的方法。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-224">Provides a fast method of setting cell values.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-225">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="cc8aa-225">xlSheetId</span></span>](xlsheetid.md) <br/> |<span data-ttu-id="cc8aa-226">4</span><span class="sxs-lookup"><span data-stu-id="cc8aa-226">4</span></span> | <span data-ttu-id="cc8aa-227">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-227">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-228">从内部 ID 获取工作表名称</span><span class="sxs-lookup"><span data-stu-id="cc8aa-228">Obtains a worksheet name from its internal ID.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-229">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="cc8aa-229">xlSheetNm</span></span>](xlsheetnm.md) <br/> |<span data-ttu-id="cc8aa-230">5</span><span class="sxs-lookup"><span data-stu-id="cc8aa-230">5</span></span> | <span data-ttu-id="cc8aa-231">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-231">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-232">从其名称中获取工作表内部 ID。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-232">Obtains a worksheet internal ID from its name.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-233">xlAbort</span><span class="sxs-lookup"><span data-stu-id="cc8aa-233">xlAbort</span></span>](xlabort.md) <br/> |<span data-ttu-id="cc8aa-234">6</span><span class="sxs-lookup"><span data-stu-id="cc8aa-234">6</span></span> | <span data-ttu-id="cc8aa-235">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-235">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-236">验证用户是否单击**取消**按钮，或者按 ESC 键。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-236">Verifies whether the user clicked the **CANCEL** button or pressed the ESC key.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-237">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="cc8aa-237">xlGetInst</span></span>](xlgetinst.md) <br/> |<span data-ttu-id="cc8aa-238">7</span><span class="sxs-lookup"><span data-stu-id="cc8aa-238">7</span></span> | <span data-ttu-id="cc8aa-239">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-239">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-240">获取 Excel 实例句柄。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-240">Gets the Excel instance handle.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-241">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="cc8aa-241">xlGetHwnd</span></span>](xlgethwnd.md) <br/> |<span data-ttu-id="cc8aa-242">8</span><span class="sxs-lookup"><span data-stu-id="cc8aa-242">8</span></span> | <span data-ttu-id="cc8aa-243">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-243">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-244">获取 Excel 主窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-244">Gets the Excel main window handle.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-245">xlGetName</span><span class="sxs-lookup"><span data-stu-id="cc8aa-245">xlGetName</span></span>](xlgetname.md) <br/> |<span data-ttu-id="cc8aa-246">9</span><span class="sxs-lookup"><span data-stu-id="cc8aa-246">9</span></span> | <span data-ttu-id="cc8aa-247">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-247">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-248">获取 DLL 的路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-248">Gets the path and file name of the DLL.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-249">xlEnableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="cc8aa-249">xlEnableXLMsgs</span></span>](xlenablexlmsgs.md) <br/> |<span data-ttu-id="cc8aa-250">10</span><span class="sxs-lookup"><span data-stu-id="cc8aa-250">10</span></span> | <span data-ttu-id="cc8aa-251">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-251">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-252">此函数已被弃用，并且不再需要调用。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-252">This function is deprecated and no longer needs to be called.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-253">xlDisableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="cc8aa-253">xlDisableXLMsgs</span></span>](xldisablexlmsgs.md) <br/> |<span data-ttu-id="cc8aa-254">11</span><span class="sxs-lookup"><span data-stu-id="cc8aa-254">11</span></span> | <span data-ttu-id="cc8aa-255">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-255">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-256">此函数已被弃用，并且不再需要调用。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-256">This function is deprecated and no longer needs to be called.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-257">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="cc8aa-257">xlDefineBinaryName</span></span>](xldefinebinaryname.md) <br/> |<span data-ttu-id="cc8aa-258">12</span><span class="sxs-lookup"><span data-stu-id="cc8aa-258">12</span></span> | <span data-ttu-id="cc8aa-259">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-259">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-260">定义持久二进制存储名称。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-260">Defines a persistent binary storage name.</span></span>  <br/> |
|[<span data-ttu-id="cc8aa-261">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="cc8aa-261">xlGetBinaryName</span></span>](xlgetbinaryname.md) <br/> |<span data-ttu-id="cc8aa-262">13</span><span class="sxs-lookup"><span data-stu-id="cc8aa-262">13</span></span> | <span data-ttu-id="cc8aa-263">xlSpecial</span><span class="sxs-lookup"><span data-stu-id="cc8aa-263">xlSpecial</span></span>  <br/> |<span data-ttu-id="cc8aa-264">获取的持久性二进制存储区名称数据。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-264">Gets a persistent binary storage name's data.</span></span>  <br/> |
   
## <a name="return-value-xloperxloper12-operres"></a><span data-ttu-id="cc8aa-265">返回值 XLOPER/XLOPER12: operRes</span><span class="sxs-lookup"><span data-stu-id="cc8aa-265">Return value XLOPER/XLOPER12: operRes</span></span>

<span data-ttu-id="cc8aa-266">_OperRes_参数是回调到第二个参数，并且指向**XLOPER** （**Excel4**和**Excel4v**） 或**XLOPER12** （**Excel12**和**Excel12v**） 的指针。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-266">The  _operRes_ argument is the second argument to the callbacks and is a pointer to an **XLOPER** (**Excel4** and **Excel4v**) or **XLOPER12** (**Excel12** and **Excel12v**).</span></span> <span data-ttu-id="cc8aa-267">成功调用后，它包含的函数或命令的返回值。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-267">After a successful call, it contains the return value of the function or command.</span></span> <span data-ttu-id="cc8aa-268">如果没有返回值，则需要，可以是**operRes**设置为零 （NULL 指针）。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-268">**operRes** can be set to zero (NULL pointer) if no return value is required.</span></span> <span data-ttu-id="cc8aa-269">以前的**operRes**内容将覆盖以便必须呼叫以避免出现内存泄漏之前释放以前指向任何内存。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-269">The previous contents of **operRes** are overwritten so that any memory previously pointed to must be freed before to the call to avoid memory leaks.</span></span> 
  
<span data-ttu-id="cc8aa-270">**OperRes**如果 （例如，如果参数不正确），则不能调用的函数或命令，将设置为错误 **#VALUE ！**。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-270">If the function or command cannot be called (for example, if the arguments are incorrect), **operRes** is set to the error **#VALUE!**.</span></span> <span data-ttu-id="cc8aa-271">如果成功，或**FALSE**如果失败或用户取消该命令始终返回**布尔值** **，则返回 TRUE** 。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-271">A command always returns **Boolean** **TRUE** if it is successful, or **FALSE** if it failed or the user canceled it.</span></span> 
  
## <a name="number-of-subsequent-arguments-count"></a><span data-ttu-id="cc8aa-272">随后参数数目错误： 计数</span><span class="sxs-lookup"><span data-stu-id="cc8aa-272">Number of Subsequent Arguments: count</span></span>

<span data-ttu-id="cc8aa-273">_Count_参数是回调的第三个参数，并且是 32 位有符号的整数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-273">The  _count_ argument is the third argument to the callbacks and is a 32-bit signed integer.</span></span> <span data-ttu-id="cc8aa-274">它应设置为后续参数，从 1 开始计数的数目。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-274">It should be set to the number of subsequent arguments, counting from 1.</span></span> <span data-ttu-id="cc8aa-275">如果函数或命令不采用任何参数，它应设置为零。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-275">If a function or command takes no arguments, it should be set to zero.</span></span> <span data-ttu-id="cc8aa-276">在 Microsoft Office Excel 2003 中，可以采取任何函数的参数的最大数目是 30，但是大部分采用少于这。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-276">In Microsoft Office Excel 2003, the maximum number of arguments that any function can take is 30, although most take fewer than this.</span></span> <span data-ttu-id="cc8aa-277">从 Excel 2007 开始，可以执行任何函数的参数的最大数量增加到 255。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-277">Starting in Excel 2007, the maximum number of arguments that any function can take was increased to 255.</span></span> 
  
<span data-ttu-id="cc8aa-278">使用**Excel4**和**Excel12**， _count_是指向**XLOPER**或**XLOPER12**传递的值的数目。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-278">With **Excel4** and **Excel12**,  _count_ is the number of pointers to **XLOPER** or **XLOPER12** values that are being passed.</span></span> <span data-ttu-id="cc8aa-279">您应该谨慎以传递的_计数_的值比少参数设置为。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-279">You should be very careful not to pass fewer arguments than the value that  _count_ is set to.</span></span> <span data-ttu-id="cc8aa-280">这会导致 Excel 读取提前堆栈和尝试处理无效**XLOPER**或**XLOPER12**值，可能会导致应用程序崩溃。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-280">This would result in Excel reading ahead into the stack and trying to process invalid **XLOPER** or **XLOPER12** values, which could cause an application crash.</span></span> 
  
<span data-ttu-id="cc8aa-281">使用**Excel4v**和**Excel12v**， _count_是数组的作为下一个和最后一个参数传递的指向**XLOPER**或**XLOPER12**值的大小。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-281">With **Excel4v** and **Excel12v**,  _count_ is the size of the array of pointers to **XLOPER** or **XLOPER12** values that is being passed as the next and final argument.</span></span> <span data-ttu-id="cc8aa-282">同样，您应该谨慎以传递较小比大小的_count_元素数组，因为这将导致的数组正在溢出边界。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-282">Again, you should be very careful not to pass a smaller array than  _count_ elements in size, as this will result in the bounds of the array being overrun.</span></span> 
  
## <a name="passing-arguments-to-c-api-functions"></a><span data-ttu-id="cc8aa-283">向 C API 函数传递参数</span><span class="sxs-lookup"><span data-stu-id="cc8aa-283">Passing Arguments to C API Functions</span></span>

<span data-ttu-id="cc8aa-284">**Excel4**和**Excel12**采用可变长度参数列表后_计数_，其分别解释为指向**XLOPER**和**XLOPER12**值。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-284">Both **Excel4** and **Excel12** take variable length argument lists, after  _count_, which are interpreted as pointers to **XLOPER** and **XLOPER12** values, respectively.</span></span> <span data-ttu-id="cc8aa-285">**Excel4v**和**Excel12v**采用单个参数后_计数_，它是一个指向的指针到**Excel4v**，对于**XLOPER**值和对于**Excel12v** **XLOPER12**值的数组。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-285">**Excel4v** and **Excel12v** take a single argument, after  _count_, which is a pointer to an array of pointers to **XLOPER** values in the case of **Excel4v**, and to **XLOPER12** values in the case of **Excel12v**.</span></span>
  
<span data-ttu-id="cc8aa-286">数组窗体、 **Excel4v**和**Excel12v**，使您能够变量的参数数目时完全代码 C API 调用。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-286">The array forms, **Excel4v** and **Excel12v**, enable you to code a call to the C API cleanly when the number of arguments is variable.</span></span> <span data-ttu-id="cc8aa-287">下面的示例演示一个函数，采用大小可变的数组的号码，并使用 Excel 工作表函数，通过 C API，计算 sum、 平均、 最小和最大。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-287">The following example shows a function that takes a variable-sized array of numbers and uses Excel worksheet functions, via the C API, to calculate the sum, average, minimum, and maximum.</span></span> 
  
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

<span data-ttu-id="cc8aa-288">替换**XLOPER**，并使用**Excel4v** **Excel12v** **XLOPER12**值的引用，在前面的代码将导致在将处理所有版本的 Excel 函数中。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-288">Replacing references to **XLOPER12** values with **XLOPER**, and **Excel12v** with **Excel4v**, in the preceding code would result in a function that would work with all versions of Excel.</span></span> <span data-ttu-id="cc8aa-289">此操作的 Excel 函数**SUM**、**平均**、**最小值**，和**最大**相当简单，就像它们中 C 的代码，并避免准备参数和调用 Excel 的开销更有效。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-289">This operation of the Excel functions **SUM**, **AVERAGE**, **MIN**, and **MAX** is simple enough that it would be more efficient to code them in C and avoid the overhead of preparing the arguments and calling into Excel.</span></span> <span data-ttu-id="cc8aa-290">但是，许多 Excel 中包含的功能是更复杂，使有用在某些情况下，此方法。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-290">However, many of the functions Excel contains are more complex, making this approach useful in some cases.</span></span> 
  
<span data-ttu-id="cc8aa-291">[XlfRegister](http://msdn.microsoft.com/library/guid_c730124c-1886-4a0f-8f06-79763025537d%28Office.15%29.aspx)主题提供了使用**Excel4v**和**Excel12v**的另一个示例。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-291">The [xlfRegister](http://msdn.microsoft.com/library/guid_c730124c-1886-4a0f-8f06-79763025537d%28Office.15%29.aspx) topic provides another example of working with **Excel4v** and **Excel12v**.</span></span> <span data-ttu-id="cc8aa-292">当注册 XLL 工作表函数，您可以提供**粘贴函数**对话框中使用的每个参数的描述性字符串。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-292">When registering an XLL worksheet function, you can supply a descriptive string for each argument that is used in the **Paste Function** dialog box.</span></span> <span data-ttu-id="cc8aa-293">因此，要提供给**xlfRegister**的总参数数目取决于 XLL 函数的参数数目，并且将因到下一个函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-293">Therefore, the number of total arguments being supplied to **xlfRegister** depends on the number of arguments your XLL function takes and will vary from one function to the next.</span></span> 
  
<span data-ttu-id="cc8aa-294">如果您始终调用的 C API 函数或命令具有相同数量的参数，您想要避免创建数组为这些参数的指针的额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-294">Where you always call a C API function or command with the same number of arguments, you want to avoid the extra step of creating an array of pointers for those arguments.</span></span> <span data-ttu-id="cc8aa-295">在这种情况下，会使用**Excel4**和**Excel12**更加简练。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-295">In those cases, it is simpler and cleaner to use **Excel4** and **Excel12**.</span></span> <span data-ttu-id="cc8aa-296">例如，当注册 XLL 函数和命令，您需要提供的 DLL 或 XLL 的完整路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-296">For example, when registering XLL functions and commands, you need to supply the full path and file name of the DLL or XLL.</span></span> <span data-ttu-id="cc8aa-297">您可以获取**xlfGetName**调用中的文件名称，然后将它与**xlFree**，调用释放如**Excel4**和**Excel12**下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-297">You can obtain the file name in a call to **xlfGetName** and then release it with a call to **xlFree**, as shown in the following example for both **Excel4** and **Excel12**.</span></span>
  
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

<span data-ttu-id="cc8aa-298">实际上，该函数， **Excel12v_example**，无法通过创建单个**xltypeMulti** **XLOPER12**参数，并使用**Excel12**，调用 C API，如下面的示例中所示更有效地编码。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-298">In practice, the function, **Excel12v_example**, could be coded more efficiently by creating a single **xltypeMulti** **XLOPER12** argument, and calling the C API by using **Excel12**, as shown in the following example.</span></span>
  
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
> <span data-ttu-id="cc8aa-299">在这种情况下， **Excel12**返回值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-299">In this case, the return value of **Excel12** is ignored.</span></span> <span data-ttu-id="cc8aa-300">该代码改为检查返回的**XLOPER12**是**xltypeNum**确定呼叫是否成功。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-300">The code instead checks that the returned **XLOPER12** is **xltypeNum** to determine whether the call was successful.</span></span> 
  
## <a name="xlcallver"></a><span data-ttu-id="cc8aa-301">XLCallVer</span><span class="sxs-lookup"><span data-stu-id="cc8aa-301">XLCallVer</span></span>

<span data-ttu-id="cc8aa-302">除了回调**Excel4**、 **Excel4v**、 **Excel12**和**Excel12v**Excel 导出函数**XLCallVer**，它返回当前正在运行的 C API 的版本。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-302">In addition to the callbacks **Excel4**, **Excel4v**, **Excel12**, and **Excel12v**, Excel exports a function **XLCallVer**, which returns the version of the C API currently running.</span></span>
  
<span data-ttu-id="cc8aa-303">函数原型如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc8aa-303">The function prototype is as follows:</span></span>
  
 `int pascal XLCallVer(void);`
  
<span data-ttu-id="cc8aa-304">您可以调用此函数，它是线程安全的从任何 XLL 命令或函数。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-304">You can call this function, which is thread safe, from any XLL command or function.</span></span>
  
<span data-ttu-id="cc8aa-305">在 Excel 97 至 Excel 2003， **XLCallVer**返回 1280 = 0x0500 十六进制 = 5 x 256，这表明 Excel 版本 5。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-305">In Excel 97 through Excel 2003, **XLCallVer** returns 1280 = 0x0500 hex = 5 x 256, which indicates Excel version 5.</span></span> <span data-ttu-id="cc8aa-306">从 Excel 2007 开始，返回 3072 = 0x0c00 十六进制 = 12 x 256，同样指示版本 12。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-306">Starting in Excel 2007, it returns 3072 = 0x0c00 hex = 12 x 256, which similarly indicates version 12.</span></span>
  
<span data-ttu-id="cc8aa-307">尽管您可以使用此方法来确定新的 C API 在运行时是否可用，但您可能希望使用检测正在运行的 Excel 版本`Excel4(xlfGetWorkspace, &version, 1, &arg)`，其中`arg`是**XLOPER**设置为 2 的数字。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-307">Although you can use this to determine whether the new C API is available at run time, you might prefer to detect the running version of Excel by using  `Excel4(xlfGetWorkspace, &version, 1, &arg)`, where  `arg` is a numeric **XLOPER** set to 2.</span></span> <span data-ttu-id="cc8aa-308">此函数返回字符串**XLOPER**，版本，然后可以强制为一个整数值。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-308">The function returns a string **XLOPER**, version, which can then be coerced to an integer.</span></span> <span data-ttu-id="cc8aa-309">依赖的 Excel 版本，而不是 C API 版本的原因是 Excel 2000、 Excel 2002 和 Excel 2003 的加载项可能还需要检测之间的差异。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-309">The reason for relying on the Excel version rather than the C API version is that there are differences between Excel 2000, Excel 2002, and Excel 2003 that your add-in may also need to detect.</span></span> <span data-ttu-id="cc8aa-310">例如，更改的统计信息功能的一些准确性。</span><span class="sxs-lookup"><span data-stu-id="cc8aa-310">For example, changes were made to the accuracy of some of the statistics functions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc8aa-311">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc8aa-311">See also</span></span>



[<span data-ttu-id="cc8aa-312">创建 xll</span><span class="sxs-lookup"><span data-stu-id="cc8aa-312">Creating XLLs</span></span>](creating-xlls.md)
  
[<span data-ttu-id="cc8aa-313">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="cc8aa-313">Accessing XLL Code in Excel</span></span>](accessing-xll-code-in-excel.md)
  
[<span data-ttu-id="cc8aa-314">Excel XLL SDK API Function Reference</span><span class="sxs-lookup"><span data-stu-id="cc8aa-314">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)
  
[<span data-ttu-id="cc8aa-315">C API Callback Functions Excel4, Excel12</span><span class="sxs-lookup"><span data-stu-id="cc8aa-315">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md)
  
[<span data-ttu-id="cc8aa-316">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="cc8aa-316">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

