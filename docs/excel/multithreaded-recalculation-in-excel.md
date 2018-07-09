---
title: 在 Excel 中的多线程重新计算
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- 线程安全 [excel 2007] 的单元格，Excel，并发任务 [Excel 2007]，[Excel 2007] 的线程安全功能，多线程重新计算 [Excel 2007，] MTR [Excel 2007]，XLL 函数 [Excel 2007]，注册为线程安全的重新计算 [多线程Excel 2007 中]，多线程，内存争用 [Excel 2007]，注册 XLL 函数，如线程安全 [Excel 2007]，不安全的功能 [Excel 2007]
localization_priority: Normal
ms.assetid: c6c831f1-4be1-4dcc-a0fa-c26052ec53c9
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 010a1029e0bf5ba1a36b324ebd402f6e90603fb9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773802"
---
# <a name="multithreaded-recalculation-in-excel"></a><span data-ttu-id="a3ee3-104">在 Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="a3ee3-104">Multithreaded recalculation in Excel</span></span>

<span data-ttu-id="a3ee3-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a3ee3-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a3ee3-106">Microsoft Office Excel 2007 是 Excel 使用多线程重新计算 (MTR) 的工作表的第一版。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-106">Microsoft Office Excel 2007 was the first version of Excel to use multithreaded recalculation (MTR) of worksheets.</span></span> <span data-ttu-id="a3ee3-107">您可以配置 Excel 时要使用最多为 1024年并发线程重新计算，无论在计算机上的处理器内核处理器的数量。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-107">You can configure Excel to use up to 1024 concurrent threads when recalculating, regardless of the number of processors or processor cores on the computer.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a3ee3-108">没有与每个线程，开销关联，因此不应配置 Excel 使用更多需要线程操作系统。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-108">There is an operating system overhead associated with each thread, so you should not configure Excel to use more threads than you need.</span></span> 
  
<span data-ttu-id="a3ee3-109">如果计算机有多个处理器或处理器内核，操作系统所需的最适合您的方式分配给处理器线程的责任。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-109">If the computer has multiple processors or processor cores, the operating system takes responsibility for allocating the threads to the processors in the most efficient way.</span></span>
  
## <a name="excel-mtr-overview"></a><span data-ttu-id="a3ee3-110">Excel MTR 概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="a3ee3-110">Excel MTR overview</span></span>

<span data-ttu-id="a3ee3-111">Excel 尝试确定可以在不同线程同时重新计算的计算链部分。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-111">Excel tries to identify parts of the calculation chain that can be recalculated concurrently on different threads.</span></span> <span data-ttu-id="a3ee3-112">以下非常简单树 （其中 x ← y 意味着 y 仅取决于 x） 显示此示例。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-112">The following very simple tree (where x ← y means y only depends on x) shows an example of this.</span></span>
  
<span data-ttu-id="a3ee3-113">**图 1。在不同线程上同时计算**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-113">**Figure 1. Calculating concurrently on different threads**</span></span>

<span data-ttu-id="a3ee3-114">![在不同线程上同时计算](media/12b5a52b-6308-420c-b6cf-492bd1f195ce.gif "在不同线程上同时计算")</span><span class="sxs-lookup"><span data-stu-id="a3ee3-114">![Calculating concurrently on different threads](media/12b5a52b-6308-420c-b6cf-492bd1f195ce.gif "Calculating concurrently on different threads")</span></span>
  
<span data-ttu-id="a3ee3-115">计算 A1 后，A2 然后 A3 可以计算一个线程上同时 B1 然后 C1 可以计算另一个，假定所有单元格都安全的线程。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-115">After A1 is calculated, A2 and then A3 can be calculated on one thread, while B1 and then C1 can be calculated on another, assuming all the cells are thread safe.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a3ee3-116">术语线程安全单元格表示仅包含线程安全函数的单元格。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-116">The term thread-safe cell means a cell that only contains thread-safe functions.</span></span> <span data-ttu-id="a3ee3-117">将详细介绍什么是而不是线程安全[新增和是不被视为线程安全由 Excel](#xl2007xllsdk_threadsafe)。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-117">What is and is not thread-safe is detailed [What Is and Is Not Considered Thread Safe by Excel](#xl2007xllsdk_threadsafe).</span></span> 
  
<span data-ttu-id="a3ee3-118">大多数实际工作簿包含更复杂的依赖项树比此示例。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-118">Most practical workbooks contain far more complex dependency trees than this example.</span></span> <span data-ttu-id="a3ee3-119">此外，直到计算完成和可能相差根据函数的参数，则无法知道单元格的重新计算时间。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-119">Moreover, the recalculation time of a cell cannot be known until a calculation is done and can vary greatly depending on the functions' arguments.</span></span> <span data-ttu-id="a3ee3-120">若要获得最佳结果，Excel 尝试提高在每次计算的计算顺序，直到可以无进一步优化。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-120">To obtain the best results, Excel tries to improve the calculation order on every calculation until no further optimization is possible.</span></span>
  
<span data-ttu-id="a3ee3-121">Excel 中使用单个主线程运行或执行以下：</span><span class="sxs-lookup"><span data-stu-id="a3ee3-121">Excel uses a single main thread to run or execute the following:</span></span>
  
- <span data-ttu-id="a3ee3-122">内置命令。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-122">Built-in commands</span></span>
    
- <span data-ttu-id="a3ee3-123">XLL 命令</span><span class="sxs-lookup"><span data-stu-id="a3ee3-123">XLL commands</span></span>
    
- <span data-ttu-id="a3ee3-124">XLL 加载项管理器界面函数 （**xlAutoOpen**函数等）</span><span class="sxs-lookup"><span data-stu-id="a3ee3-124">XLL Add-in Manager interface functions (**xlAutoOpen** function, and so on)</span></span> 
    
- <span data-ttu-id="a3ee3-125">Microsoft Visual Basic for Applications (VBA) 用户定义命令 （通常称作宏）</span><span class="sxs-lookup"><span data-stu-id="a3ee3-125">Microsoft Visual Basic for Applications (VBA) user-defined commands (often referred to as macros)</span></span>
    
- <span data-ttu-id="a3ee3-126">VBA 用户定义函数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-126">VBA user-defined functions</span></span>
    
- <span data-ttu-id="a3ee3-127">内置线程不安全的工作表函数 （请参阅下一节的列表）</span><span class="sxs-lookup"><span data-stu-id="a3ee3-127">Built-in thread-unsafe worksheet functions (see the next section for a list)</span></span>
    
- <span data-ttu-id="a3ee3-128">XLM 宏工作表用户定义的命令和函数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-128">XLM macro sheet user-defined commands and functions</span></span>
    
- <span data-ttu-id="a3ee3-129">COM 加载项命令和函数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-129">COM add-in commands and functions</span></span>
    
- <span data-ttu-id="a3ee3-130">函数和条件格式表达式中的运算符</span><span class="sxs-lookup"><span data-stu-id="a3ee3-130">Functions and operators within conditional formatting expressions</span></span>
    
- <span data-ttu-id="a3ee3-131">函数和中定义的名称定义在工作表公式中使用的运算符</span><span class="sxs-lookup"><span data-stu-id="a3ee3-131">Functions and operators within defined name definitions used in worksheet formulas</span></span>
    
- <span data-ttu-id="a3ee3-132">强制使用**F9**键的公式编辑框中的表达式的计算</span><span class="sxs-lookup"><span data-stu-id="a3ee3-132">The forced evaluation of an expression in the formula-edit box using the **F9** key</span></span> 
    
<span data-ttu-id="a3ee3-133">除非 Excel 配置为使用多个线程，对主线程进行评估工作表中的所有公式，无论是否函数是否线程安全。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-133">All worksheet formulas, regardless of whether the functions are thread safe or not, are evaluated on the main thread unless Excel is configured to use more than one thread.</span></span> <span data-ttu-id="a3ee3-134">当用户指定应使用多个线程时，更多线程用于线程安全单元格。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-134">When the user specifies that more than one thread should be used, the additional threads are used for thread-safe cells.</span></span> <span data-ttu-id="a3ee3-135">请注意时意义从负载平衡的点的视图后，仍可能主线程线程安全单元格中使用。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-135">Note that the main thread may still be used for thread-safe cells when it makes sense from a load-balancing point of view.</span></span>
  
<span data-ttu-id="a3ee3-136">值得复述，Excel 不同时运行多个命令，因此不需要为写入线程安全功能，如使用线程本地内存和关键节的时采用相同的预防措施。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-136">It is worth restating that Excel does not run more than one command at once, so you do not need to employ the same precautions as when you are writing thread-safe functions, such as the use of thread-local memory and critical sections.</span></span>
  
## <a name="what-is-and-is-not-considered-thread-safe-by-excel"></a><span data-ttu-id="a3ee3-137">什么是，不被视作线程安全由 Excel</span><span class="sxs-lookup"><span data-stu-id="a3ee3-137">What is and is not considered thread safe by Excel</span></span>
<span data-ttu-id="a3ee3-138"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ee3-138"></span></span>

<span data-ttu-id="a3ee3-139">Excel 只考虑以下内容作为线程安全：</span><span class="sxs-lookup"><span data-stu-id="a3ee3-139">Excel only considers the following as thread safe:</span></span>
  
- <span data-ttu-id="a3ee3-140">在 Excel 中的所有一元和二元运算符。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-140">All unary and binary operators in Excel.</span></span>
    
- <span data-ttu-id="a3ee3-141">启动 Excel 2007 （请参阅例外列表） 中的几乎所有内置的工作表函数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-141">Almost all built-in worksheet functions starting in Excel 2007 (see exceptions list)</span></span>
    
- <span data-ttu-id="a3ee3-142">XLL 加载项的功能已显式注册为线程安全。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-142">XLL add-in functions that have been explicitly registered as thread-safe.</span></span>
    
<span data-ttu-id="a3ee3-143">不线程安全的内置工作表功能是：</span><span class="sxs-lookup"><span data-stu-id="a3ee3-143">The built-in worksheet functions that are not thread safe are:</span></span>
  
- <span data-ttu-id="a3ee3-144">**拼音**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-144">**PHONETIC**</span></span>
    
- <span data-ttu-id="a3ee3-145">**单元格**时使用的"格式"或"address"的参数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-145">**CELL** when either the "format" or "address" argument is used</span></span> 
    
- <span data-ttu-id="a3ee3-146">**间接**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-146">**INDIRECT**</span></span>
    
- <span data-ttu-id="a3ee3-147">**GETPIVOTDATA**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-147">**GETPIVOTDATA**</span></span>
    
- <span data-ttu-id="a3ee3-148">**CUBEMEMBER**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-148">**CUBEMEMBER**</span></span>
    
- <span data-ttu-id="a3ee3-149">**CUBEVALUE**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-149">**CUBEVALUE**</span></span>
    
- <span data-ttu-id="a3ee3-150">**CUBEMEMBERPROPERTY**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-150">**CUBEMEMBERPROPERTY**</span></span>
    
- <span data-ttu-id="a3ee3-151">**CUBESET**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-151">**CUBESET**</span></span>
    
- <span data-ttu-id="a3ee3-152">**CUBERANKEDMEMBER**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-152">**CUBERANKEDMEMBER**</span></span>
    
- <span data-ttu-id="a3ee3-153">**CUBEKPIMEMBER**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-153">**CUBEKPIMEMBER**</span></span>
    
- <span data-ttu-id="a3ee3-154">**CUBESETCOUNT**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-154">**CUBESETCOUNT**</span></span>
    
- <span data-ttu-id="a3ee3-155">**地址**在给定第五个参数 (sheet_name)</span><span class="sxs-lookup"><span data-stu-id="a3ee3-155">**ADDRESS** where the fifth parameter (the sheet_name) is given</span></span> 
    
- <span data-ttu-id="a3ee3-156">对数据透视表是指任何数据库函数 （**DSUM**、 **DAVERAGE**，等等）</span><span class="sxs-lookup"><span data-stu-id="a3ee3-156">Any database function (**DSUM**, **DAVERAGE**, and so on) that refers to a pivot table</span></span>
    
- <span data-ttu-id="a3ee3-157">**错误。类型**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-157">**ERROR.TYPE**</span></span>
    
- <span data-ttu-id="a3ee3-158">**超链接**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-158">**HYPERLINK**</span></span>
    
<span data-ttu-id="a3ee3-159">若要显式，以下被视为不安全：</span><span class="sxs-lookup"><span data-stu-id="a3ee3-159">To be explicit, the following are considered to be unsafe:</span></span>
  
- <span data-ttu-id="a3ee3-160">VBA 用户定义函数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-160">VBA user-defined functions</span></span>
    
- <span data-ttu-id="a3ee3-161">COM 加载项用户定义函数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-161">COM add-in user-defined functions</span></span>
    
- <span data-ttu-id="a3ee3-162">XLM 宏工作表的用户定义函数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-162">XLM macro-sheet user-defined functions</span></span>
    
- <span data-ttu-id="a3ee3-163">XLL 加载项功能未显式注册为线程安全</span><span class="sxs-lookup"><span data-stu-id="a3ee3-163">XLL add-in functions not explicitly registered as thread safe</span></span>
    
<span data-ttu-id="a3ee3-164">含义是，下面的操作和功能不是线程安全的并且如果从注册为线程安全的 XLL 函数调用失败：</span><span class="sxs-lookup"><span data-stu-id="a3ee3-164">The implications are that the following operations and functions are not thread-safe, and fail if they are called from an XLL function registered as thread safe:</span></span>
  
- <span data-ttu-id="a3ee3-165">XLM 信息函数调用，例如， **xlfGetCell** (**GET。单元格**)。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-165">Calls to XLM information functions, for example, **xlfGetCell** (**GET.CELL**).</span></span>
    
- <span data-ttu-id="a3ee3-166">呼叫到**xlfSetName** (**SET.NAME**) 定义或删除 XLL 内部名称。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-166">Calls to **xlfSetName** (**SET.NAME**) to define or delete XLL-internal names.</span></span>
    
- <span data-ttu-id="a3ee3-167">对使用**xlUDF**线程不安全用户定义函数的调用。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-167">Calls to thread-unsafe user-defined functions using **xlUDF**.</span></span>
    
- <span data-ttu-id="a3ee3-168">对表达式包含线程不安全的函数或包含已定义的名称，其定义包含线程不安全的函数调用[xlfEvaluate](xlfevaluate.md)函数。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-168">Calls to the [xlfEvaluate](xlfevaluate.md) function for expressions that contain thread-unsafe functions or that contain defined names whose definitions contain thread-unsafe functions.</span></span> 
    
- <span data-ttu-id="a3ee3-169">若要清除中断条件对[xlAbort](xlabort.md)函数调用。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-169">Calls to the [xlAbort](xlabort.md) function to clear a break condition.</span></span> 
    
- <span data-ttu-id="a3ee3-170">调用[xlCoerce](xlcoerce.md)函数以获取未计算的单元格引用的值。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-170">Calls to the [xlCoerce](xlcoerce.md) function to get the value of an uncalculated cell reference.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a3ee3-171">不允许 XLL 工作表函数调用 C API 命令，如**xlcSave**，无论是否他们已注册为线程安全或不。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-171">XLL worksheet functions are not permitted to call C API commands, for example, **xlcSave**, regardless of whether they have been registered as thread safe or not.</span></span> 
  
<span data-ttu-id="a3ee3-172">假定 XLL 函数声明为线程安全无法调用 XLM 信息函数或引用未计算的单元格，Excel 不允许注册为宏工作表的等效项以还注册为线程安全的 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-172">Given that XLL functions declared as thread safe cannot call XLM information functions or reference uncalculated cells, Excel does not permit XLL functions that are registered as macro sheet equivalents to also be registered as thread safe.</span></span> <span data-ttu-id="a3ee3-173">因此尝试获取使用**xlCoerce**未计算的单元格引用的值失败并出现**xlretUncalced**错误。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-173">Therefore attempting to get the value of an uncalculated cell reference using **xlCoerce** fails with an **xlretUncalced** error.</span></span> <span data-ttu-id="a3ee3-174">调用 XLM 信息函数操作失败， **xlretFailed**错误。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-174">Calling an XLM information function fails with an **xlretFailed** error.</span></span> <span data-ttu-id="a3ee3-175">以前失败的列出的其他点，并在 Excel C API 中引入的错误代码： **xlretNotThreadSafe**。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-175">The other points listed previously fail with an error code introduced in the Excel C API: **xlretNotThreadSafe**.</span></span> 
  
<span data-ttu-id="a3ee3-176">C 仅 API 的回调函数是所有线程安全：</span><span class="sxs-lookup"><span data-stu-id="a3ee3-176">The C API-only call-back functions are all thread safe:</span></span>
  
- <span data-ttu-id="a3ee3-177">**xlCoerce**（虽然强制未计算的单元格的引用失败除外）</span><span class="sxs-lookup"><span data-stu-id="a3ee3-177">**xlCoerce** (except although coercion of uncalculated cell references fails)</span></span> 
    
- <span data-ttu-id="a3ee3-178">**xlFree**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-178">**xlFree**</span></span>
    
- <span data-ttu-id="a3ee3-179">**xlStack**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-179">**xlStack**</span></span>
    
- <span data-ttu-id="a3ee3-180">**xlSheetId**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-180">**xlSheetId**</span></span>
    
- <span data-ttu-id="a3ee3-181">**xlSheetNm**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-181">**xlSheetNm**</span></span>
    
- <span data-ttu-id="a3ee3-182">**xlAbort**（使用以清除中断条件时除外）</span><span class="sxs-lookup"><span data-stu-id="a3ee3-182">**xlAbort** (except when used to clear a break condition)</span></span> 
    
- <span data-ttu-id="a3ee3-183">**xlGetInst**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-183">**xlGetInst**</span></span>
    
- <span data-ttu-id="a3ee3-184">**xlGetHwnd**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-184">**xlGetHwnd**</span></span>
    
- <span data-ttu-id="a3ee3-185">**xlGetBinaryName**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-185">**xlGetBinaryName**</span></span>
    
- <span data-ttu-id="a3ee3-186">**xlDefineBinaryName**</span><span class="sxs-lookup"><span data-stu-id="a3ee3-186">**xlDefineBinaryName**</span></span>
    
<span data-ttu-id="a3ee3-187">一个例外情况是**xlset，则**函数，它是，在任何情况下，命令等效项，因此无法从调用任何工作表函数。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-187">The one exception is the **xlSet** function, which is, in any case, a command-equivalent and so cannot be called from any worksheet function.</span></span> 
  
<span data-ttu-id="a3ee3-188">可以使用 Excel 注册 XLL 工作表函数，为线程安全。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-188">An XLL worksheet function can be registered with Excel as thread safe.</span></span> <span data-ttu-id="a3ee3-189">这会告诉 Excel，可以安全地调用该函数并同时在多个线程，但您必须确保这是真正这种情况。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-189">This tells Excel that the function can be called safely and simultaneously on multiple threads, although you must make sure this is really the case.</span></span> <span data-ttu-id="a3ee3-190">如果不安全地那么行为就注册为线程安全的函数，您可能可以更改 Excel。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-190">You can possibly destabilize Excel if a function registered as thread safe then behaves unsafely.</span></span>
  
## <a name="registering-xll-functions-as-thread-safe"></a><span data-ttu-id="a3ee3-191">注册为线程安全的 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="a3ee3-191">Registering XLL functions as thread safe</span></span>
<span data-ttu-id="a3ee3-192"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ee3-192"></span></span>

<span data-ttu-id="a3ee3-193">开发人员编写线程安全功能时必须遵循的规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="a3ee3-193">The rules that a developer must obey when writing thread-safe functions are as follows:</span></span>
  
- <span data-ttu-id="a3ee3-194">不要调用其他可能无法线程安全的 Dll 中的资源。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-194">Do not call resources in other DLLs that may not be thread safe.</span></span>
    
- <span data-ttu-id="a3ee3-195">不执行任何线程不安全的 C API 或 COM.通过调用</span><span class="sxs-lookup"><span data-stu-id="a3ee3-195">Do not make any thread-unsafe calls via the C API or COM.</span></span>
    
- <span data-ttu-id="a3ee3-196">保护无法由使用关键节的多个线程同时使用的资源。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-196">Protect resources that could be used simultaneously by more than one thread using critical sections.</span></span>
    
- <span data-ttu-id="a3ee3-197">线程本地内存用于线程特定存储，并替换线程本地变量的函数中的静态变量。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-197">Use thread-local memory for thread-specific storage, and replace static variables within functions with thread-local variables.</span></span>
    
<span data-ttu-id="a3ee3-198">Excel 施加其他限制： 线程安全函数无法注册宏工作表的等效项，为，因此无法调用 XLM 信息函数或获取未重新计算的单元格的值。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-198">Excel imposes an additional restriction: thread-safe functions cannot be registered as macro-sheet equivalents, and therefore cannot call XLM information functions or get the values of un-recalculated cells.</span></span>
  
## <a name="memory-contention"></a><span data-ttu-id="a3ee3-199">内存争用</span><span class="sxs-lookup"><span data-stu-id="a3ee3-199">Memory contention</span></span>
<span data-ttu-id="a3ee3-200"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ee3-200"></span></span>

<span data-ttu-id="a3ee3-201">多线程的系统必须考虑两个基本问题：</span><span class="sxs-lookup"><span data-stu-id="a3ee3-201">Multithreaded systems must address two fundamental issues:</span></span>
  
- <span data-ttu-id="a3ee3-202">如何保护必须从，读取或写入，由多个线程的内存。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-202">How to protect memory that must be read from, or written to, by more than one thread.</span></span>
    
- <span data-ttu-id="a3ee3-203">如何创建和访问的内存，并且该镜像相关联，因此专用于，正在执行的线程。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-203">How to create and access memory that is associated with, and so private to, the executing thread.</span></span>
    
<span data-ttu-id="a3ee3-204">Windows 操作系统和 Windows 软件开发工具包 (SDK) 这两种提供工具： 关键节和线程本地存储 (TLS) API 分别。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-204">The Windows operating system and Windows Software Development Kit (SDK) provide tools for both of these: critical sections and the thread-local storage (TLS) API respectively.</span></span> <span data-ttu-id="a3ee3-205">有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-205">For more information, see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
<span data-ttu-id="a3ee3-206">例如，两个工作表函数 （或两个同时运行的相同的功能实例） 需要访问或修改全局变量在 DLL 项目时，可能出现的第一个问题。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-206">The first issue can arise, for example, when two worksheet functions (or two simultaneously running instances of the same function) need to access or modify a global variable in a DLL project.</span></span> <span data-ttu-id="a3ee3-207">请记住，可能的类对象的全局可访问实例中隐藏这样一个全局变量。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-207">Remember that such a global variable might be hidden in a globally accessible instance of a class object.</span></span>
  
<span data-ttu-id="a3ee3-208">例如，当工作表函数声明静态变量或函数正文代码中的对象时，可能出现第二个问题。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-208">The second issue can arise, for example, when a worksheet function declares a static variable or object within the function body code.</span></span> <span data-ttu-id="a3ee3-209">C/c + + 编译器仅创建所有线程都使用的一个副本。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-209">The C/C++ compiler only creates a single copy that all threads use.</span></span> <span data-ttu-id="a3ee3-210">这意味着该函数的一个实例无法更改此值时可能的值其以前设置假定在不同线程上的另一个。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-210">This means one instance of the function could change the value, while another on a different thread might be assuming the value is what it previously set.</span></span>
  
## <a name="example-applications-of-mtr"></a><span data-ttu-id="a3ee3-211">示例应用程序的 MTR</span><span class="sxs-lookup"><span data-stu-id="a3ee3-211">Example applications of MTR</span></span>
<span data-ttu-id="a3ee3-212"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ee3-212"></span></span>

<span data-ttu-id="a3ee3-213">导出工作表函数任何 XLL 可以利用多线程重新计算 (MTR) 在 Excel 中，前提是这些函数不需要执行线程不安全的操作。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-213">Any XLL that exports worksheet functions can take advantage of multithreaded recalculation (MTR) in Excel provided that those functions do not need to perform thread-unsafe actions.</span></span> <span data-ttu-id="a3ee3-214">这使 Excel 重新计算的依赖于它们尽可能快地工作簿，因此需要任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-214">This enables Excel to recalculate workbooks that depend on them as quickly as possible and is therefore desirable whatever the application.</span></span>
  
<span data-ttu-id="a3ee3-215">具体而言，MTR 上的工作簿调用用户定义的函数 (Udf) 自己呼叫外部进程以获取所需的结果的重新计算时间有重大影响。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-215">Specifically, MTR has an enormous impact on the recalculation time of workbooks that call user-defined functions (UDFs) that themselves call external processes to obtain the desired result.</span></span> <span data-ttu-id="a3ee3-216">特别考虑调用可同时处理多个请求的远程服务器的 UDF 和包含多次调用该函数的工作簿。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-216">In particular, consider a UDF that calls a remote server that can process many requests simultaneously and a workbook containing many calls to that function.</span></span> <span data-ttu-id="a3ee3-217">如果重新计算工作簿是单线程，每个调用 UDF，并因此到远程服务器，必须完成下一个才能进行。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-217">If recalculation of the workbook is single-threaded, each call to the UDF, and so to the remote server, must complete before the next one can be made.</span></span> <span data-ttu-id="a3ee3-218">这浪费同时处理多个呼叫服务器的能力。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-218">This wastes the server's ability to process many calls at once.</span></span> <span data-ttu-id="a3ee3-219">如果重新计算工作簿的是多线程，Excel 可以同时或快速连续进行多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-219">If recalculation of the workbook is multithreaded, Excel can make multiple calls at the same time or in rapid succession.</span></span>
  
<span data-ttu-id="a3ee3-220">如果 Excel 配置为使用相同的线程数作为服务器 — 调用它 N — 和拓扑结构的工作簿的相关性树允许这样的总重新计算时间可以降低为达到 1/N 的单线程的计算时间。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-220">If Excel is configured to use the same number of threads as the server—call it N—and the topology of the dependency tree of the workbook permits it, the total recalculation time could be reduced to something approaching 1/N of the single-threaded calculation time.</span></span> <span data-ttu-id="a3ee3-221">这可能是 true 甚至其中 （在其运行工作簿） 的客户端计算机仅具有一个处理器，尤其是其中进行呼叫的服务器所需的时间是相对于服务器处理呼叫的时间小型时。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-221">This may be true even where the client computer (on which the workbook is running) only has one processor, especially where the time taken to make the call to the server is small relative to the time it takes the server to process the call.</span></span> 
  
<span data-ttu-id="a3ee3-222">没有操作系统的每个其他线程的开销。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-222">There is operating system overhead for each additional thread.</span></span> <span data-ttu-id="a3ee3-223">因此一些实验可能需要的给定的工作簿和给定的服务器和客户端计算机以查找最佳应告知 Excel 要使用的线程数。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-223">Therefore some experimentation might be required for a given workbook and a given server and client computer to find the optimum number of threads Excel should be told to use.</span></span> 
  
<span data-ttu-id="a3ee3-224">例如，假设运行 Excel 和包含 1,000 单元格的工作簿的单处理器计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-224">For example, consider a single-processor computer that is running Excel and a workbook that contains 1,000 cells.</span></span> <span data-ttu-id="a3ee3-225">它调用 UDF，后者又调用一个或多个远程服务器。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-225">It calls a UDF, which in turn calls one or more remote servers.</span></span> <span data-ttu-id="a3ee3-226">假定的 1,000 单元格执行不依赖于每个其他，因此不需要等待一次调用，以调用下一步之前完成的 Excel。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-226">Assume that the 1,000 cells do not depend upon each other, so that Excel does not have to wait for one call to complete before calling the next.</span></span> <span data-ttu-id="a3ee3-227">（此限制某些宽松。 可能不会影响此示例）如果服务器可同时处理 100 个请求，Excel 配置为使用 100 个线程执行时间可以降低到降至 1/100th 的因为只有一个线程使用。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-227">(Some relaxation of this constraint is possible without affecting this example.) If the servers can process 100 requests simultaneously, and Excel is configured to use 100 threads, the execution time can be reduced to as little as 1/100th of that where only one thread is used.</span></span> <span data-ttu-id="a3ee3-228">与 Excel 分配对每个线程和管理 100 个线程的操作系统的调用开销即关联意味着，实际上，减少不将这非常重要。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-228">The overhead that is associated with Excel allocating calls to each thread and the operating system managing 100 threads means that, in practice, the reduction will not be quite this great.</span></span> <span data-ttu-id="a3ee3-229">另外，还有隐式假设此处的服务器可进行扩展，并要求它同时处理 100 个任务不会影响单个任务的完成时间显著。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-229">There is also an implicit assumption here that the server scales well, and asking it to process 100 tasks concurrently will not affect individual task completion times significantly.</span></span>
  
<span data-ttu-id="a3ee3-230">Monte-carlo 方法，以及可以拆分为较小的子任务可以分配到服务器的其他数值密集型任务的一个实践的应用程序在其中这种技术可以具有重要的好处。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-230">One practical application in which this technique can have an important benefit is that of Monte-Carlo methods, as well as other numerically intensive tasks that can be split into smaller sub-tasks that can be farmed out to servers.</span></span>
  
## <a name="excel-services-considerations"></a><span data-ttu-id="a3ee3-231">Excel Services 注意事项</span><span class="sxs-lookup"><span data-stu-id="a3ee3-231">Excel Services considerations</span></span>
<span data-ttu-id="a3ee3-232"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ee3-232"></span></span>

<span data-ttu-id="a3ee3-233">Excel Services 支持加载、 计算，并呈现的服务器上的 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-233">Excel Services supports the loading, calculating, and rendering of Excel spreadsheets on a server.</span></span> <span data-ttu-id="a3ee3-234">用户可以然后访问和使用标准的浏览器工具与电子表格交互。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-234">Users can then access and interact with the spreadsheets by using standard browser tools.</span></span>
  
<span data-ttu-id="a3ee3-235">Excel Services Udf 创建使用 Microsoft.NET Framework 托管代码和可用但.NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-235">Excel Services UDFs are created using Microsoft .NET Framework managed code and made available though a .NET assembly.</span></span> <span data-ttu-id="a3ee3-236">Excel Services 不支持 xll。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-236">XLLs are not supported by Excel Services.</span></span> <span data-ttu-id="a3ee3-237">托管的代码服务器 UDF 资源调入可以访问其功能，XLL，以便用户可以与客户端加载工作簿中具有相同的功能与服务器加载工作簿。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-237">A managed code server UDF resource can call into an XLL to access its functionality, so that the user can have the same functionality with a server-loaded workbook as with a client-loaded workbook.</span></span>
  
<span data-ttu-id="a3ee3-238">若要使 XLL 函数可使用此方法，它们必须因此包装在.NET 程序集中的参数和返回值将从转换的本机数据类型为.NET Framework 托管数据类型，并调用 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-238">To make an XLL's functions available in this way, they must therefore be wrapped in a .NET assembly that converts arguments and return values from the native data types to the .NET Framework managed data types, and that calls the XLL functions.</span></span> <span data-ttu-id="a3ee3-239">.NET 包装将导出正在访问每个 XLL 函数的一台的服务器 UDF。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-239">The .NET wrapper would export one server UDF for each XLL function being accessed.</span></span> <span data-ttu-id="a3ee3-240">额外的要求是必须线程安全运行这种方式调用任何 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-240">An additional requirement is that any XLL functions called in this way must be thread safe.</span></span> <span data-ttu-id="a3ee3-241">XLL 函数未注册的方式与 Excel 客户端的因为服务器和.NET 包装将没有任何办法来强制实施它们线程安全。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-241">Because the XLL functions are not registered in the way that they are with client Excel, the server and the .NET wrapper have no way of enforcing that they are thread safe.</span></span> <span data-ttu-id="a3ee3-242">它是 XLL 开发人员以确保此的责任。</span><span class="sxs-lookup"><span data-stu-id="a3ee3-242">It is the responsibility of the XLL developer to ensure this.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3ee3-243">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3ee3-243">See also</span></span>

- [<span data-ttu-id="a3ee3-244">Excel 重新计算</span><span class="sxs-lookup"><span data-stu-id="a3ee3-244">Excel Recalculation</span></span>](excel-recalculation.md)  
- [<span data-ttu-id="a3ee3-245">在 Excel 中进行内存管理</span><span class="sxs-lookup"><span data-stu-id="a3ee3-245">Memory Management in Excel</span></span>](memory-management-in-excel.md) 
- [<span data-ttu-id="a3ee3-246">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="a3ee3-246">Accessing XLL Code in Excel</span></span>](accessing-xll-code-in-excel.md)  
- [<span data-ttu-id="a3ee3-247">Excel Programming Concepts</span><span class="sxs-lookup"><span data-stu-id="a3ee3-247">Excel Programming Concepts</span></span>](excel-programming-concepts.md)  
- [<span data-ttu-id="a3ee3-248">Excel XLL SDK API Function Reference</span><span class="sxs-lookup"><span data-stu-id="a3ee3-248">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)

