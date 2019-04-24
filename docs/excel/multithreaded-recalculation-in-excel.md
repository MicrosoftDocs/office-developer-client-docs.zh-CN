---
title: Excel 中的多线程重新计算
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- 线程安全单元格 [Excel 2007],Excel 中的多线程,并发任务 [Excel 2007],线程安全函数 [Excel 2007],多线程重新计算 [Excel 2007],MTR [Excel 2007],XLL 函数 [Excel 2007],注册为线程安全,重新计算 [Excel 2007],多线程,内存争用 [Excel 2007],将 XLL 函数注册为线程安全 [Excel 2007],不安全函数 [Excel 2007]
ms.assetid: c6c831f1-4be1-4dcc-a0fa-c26052ec53c9
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: f0b6f3d7310cac6d141fc74652a3333f70bda8e9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310500"
---
# <a name="multithreaded-recalculation-in-excel"></a><span data-ttu-id="8a915-104">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="8a915-104">Multithreaded recalculation in Excel</span></span>

<span data-ttu-id="8a915-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8a915-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="8a915-106">Microsoft Office Excel 2007 是首版对工作表使用多线程重新计算 (MTR) 的 Excel。</span><span class="sxs-lookup"><span data-stu-id="8a915-106">Microsoft Office Excel 2007 was the first version of Excel to use multithreaded recalculation (MTR) of worksheets.</span></span> <span data-ttu-id="8a915-107">可以将 Excel 配置为，在重新计算时最多使用 1024 个并发线程，无论计算机上有多少个处理器或处理器核心。</span><span class="sxs-lookup"><span data-stu-id="8a915-107">You can configure Excel to use up to 1024 concurrent threads when recalculating, regardless of the number of processors or processor cores on the computer.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8a915-108">由于会产生与每个线程相关的操作系统开销，因此不得将 Excel 配置为使用超过所需的线程数。</span><span class="sxs-lookup"><span data-stu-id="8a915-108">There is an operating system overhead associated with each thread, so you should not configure Excel to use more threads than you need.</span></span> 
  
<span data-ttu-id="8a915-109">如果计算机有多个处理器或处理器核心，操作系统负责以最高效方式将线程分配给处理器。</span><span class="sxs-lookup"><span data-stu-id="8a915-109">If the computer has multiple processors or processor cores, the operating system takes responsibility for allocating the threads to the processors in the most efficient way.</span></span>
  
## <a name="excel-mtr-overview"></a><span data-ttu-id="8a915-110">Excel MTR 概述</span><span class="sxs-lookup"><span data-stu-id="8a915-110">Excel MTR overview</span></span>

<span data-ttu-id="8a915-111">Excel 尝试确定可同时在不同线程中重新计算的计算链部分。</span><span class="sxs-lookup"><span data-stu-id="8a915-111">Excel tries to identify parts of the calculation chain that can be recalculated concurrently on different threads.</span></span> <span data-ttu-id="8a915-112">下面这个非常简单的示例树（其中，x ← y 表示 y 仅依赖 x）就说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="8a915-112">The following very simple tree (where x ← y means y only depends on x) shows an example of this.</span></span>
  
<span data-ttu-id="8a915-113">**图 1：同时在不同线程中计算**</span><span class="sxs-lookup"><span data-stu-id="8a915-113">**Figure 1. Calculating concurrently on different threads**</span></span>

<span data-ttu-id="8a915-114">![同时在不同线程中计算](media/12b5a52b-6308-420c-b6cf-492bd1f195ce.gif "同时在不同线程中计算")</span><span class="sxs-lookup"><span data-stu-id="8a915-114">![Calculating concurrently on different threads](media/12b5a52b-6308-420c-b6cf-492bd1f195ce.gif "Calculating concurrently on different threads")</span></span>
  
<span data-ttu-id="8a915-115">在计算 A1 后，便能在一个线程中依次计算 A2 和 A3，同时在另一个线程中依次计算 B1 和 C1（假设所有单元格都是线程安全单元格）。</span><span class="sxs-lookup"><span data-stu-id="8a915-115">After A1 is calculated, A2 and then A3 can be calculated on one thread, while B1 and then C1 can be calculated on another, assuming all the cells are thread safe.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8a915-116">“线程安全单元格”一词是指只包含线程安全函数的单元格。</span><span class="sxs-lookup"><span data-stu-id="8a915-116">The term thread-safe cell means a cell that only contains thread-safe functions.</span></span> <span data-ttu-id="8a915-117">[Excel 视为线程安全和非线程安全的项](#xl2007xllsdk_threadsafe)中详细说明了什么是线程安全项和非线程安全项。</span><span class="sxs-lookup"><span data-stu-id="8a915-117">What is and is not thread-safe is detailed [What Is and Is Not Considered Thread Safe by Excel](#xl2007xllsdk_threadsafe).</span></span> 
  
<span data-ttu-id="8a915-118">大多数实际工作簿包含的依赖关系树要比上面的示例复杂得多。</span><span class="sxs-lookup"><span data-stu-id="8a915-118">Most practical workbooks contain far more complex dependency trees than this example.</span></span> <span data-ttu-id="8a915-119">此外，只有在计算完成后，才能知道单元格的重新计算时间，此时间长短不一，具体视函数参数而定。</span><span class="sxs-lookup"><span data-stu-id="8a915-119">Moreover, the recalculation time of a cell cannot be known until a calculation is done and can vary greatly depending on the functions' arguments.</span></span> <span data-ttu-id="8a915-120">为了获得最佳结果，Excel 在每次计算时都会尝试改进计算顺序，直到没有进一步优化空间为止。</span><span class="sxs-lookup"><span data-stu-id="8a915-120">To obtain the best results, Excel tries to improve the calculation order on every calculation until no further optimization is possible.</span></span>
  
<span data-ttu-id="8a915-121">Excel 使用一个主线程来运行或执行以下内容：</span><span class="sxs-lookup"><span data-stu-id="8a915-121">Excel uses a single main thread to run or execute the following:</span></span>
  
- <span data-ttu-id="8a915-122">内置命令</span><span class="sxs-lookup"><span data-stu-id="8a915-122">Built-in commands</span></span>
    
- <span data-ttu-id="8a915-123">XLL 命令</span><span class="sxs-lookup"><span data-stu-id="8a915-123">XLL commands</span></span>
    
- <span data-ttu-id="8a915-124">XLL 加载项管理器接口函数（**xlAutoOpen** 函数等）</span><span class="sxs-lookup"><span data-stu-id="8a915-124">XLL Add-in Manager interface functions (**xlAutoOpen** function, and so on)</span></span> 
    
- <span data-ttu-id="8a915-125">Microsoft Visual Basic for Applications (VBA) 用户定义命令（通常称为“宏”）</span><span class="sxs-lookup"><span data-stu-id="8a915-125">Microsoft Visual Basic for Applications (VBA) user-defined commands (often referred to as macros)</span></span>
    
- <span data-ttu-id="8a915-126">VBA 用户定义函数</span><span class="sxs-lookup"><span data-stu-id="8a915-126">VBA user-defined functions</span></span>
    
- <span data-ttu-id="8a915-127">内置非线程安全工作表函数（见下一部分中的列表）</span><span class="sxs-lookup"><span data-stu-id="8a915-127">Built-in thread-unsafe worksheet functions (see the next section for a list)</span></span>
    
- <span data-ttu-id="8a915-128">XLM 宏工作表用户定义命令和函数</span><span class="sxs-lookup"><span data-stu-id="8a915-128">XLM macro sheet user-defined commands and functions</span></span>
    
- <span data-ttu-id="8a915-129">COM 加载项命令和函数</span><span class="sxs-lookup"><span data-stu-id="8a915-129">COM add-in commands and functions</span></span>
    
- <span data-ttu-id="8a915-130">条件格式表达式中的函数和运算符</span><span class="sxs-lookup"><span data-stu-id="8a915-130">Functions and operators within conditional formatting expressions</span></span>
    
- <span data-ttu-id="8a915-131">工作表公式中使用的已定义名称定义中的函数和运算符</span><span class="sxs-lookup"><span data-stu-id="8a915-131">Functions and operators within defined name definitions used in worksheet formulas</span></span>
    
- <span data-ttu-id="8a915-132">使用 **F9** 键强制计算公式编辑框中的表达式</span><span class="sxs-lookup"><span data-stu-id="8a915-132">The forced evaluation of an expression in the formula-edit box using the **F9** key</span></span> 
    
<span data-ttu-id="8a915-133">除非 Excel 被配置为使用多线程，否则所有工作表公式（无论函数是否是线程安全函数）都是在主线程中进行计算。</span><span class="sxs-lookup"><span data-stu-id="8a915-133">All worksheet formulas, regardless of whether the functions are thread safe or not, are evaluated on the main thread unless Excel is configured to use more than one thread.</span></span> <span data-ttu-id="8a915-134">如果用户指定应使用多线程，其他线程用于线程安全单元格。</span><span class="sxs-lookup"><span data-stu-id="8a915-134">When the user specifies that more than one thread should be used, the additional threads are used for thread-safe cells.</span></span> <span data-ttu-id="8a915-135">请注意，如果从负载均衡角度来看是有意义的，主线程仍用于线程安全单元格。</span><span class="sxs-lookup"><span data-stu-id="8a915-135">Note that the main thread may still be used for thread-safe cells when it makes sense from a load-balancing point of view.</span></span>
  
<span data-ttu-id="8a915-136">值得重申的是，Excel 一次只运行一个命令，因此无需采用在编写线程安全函数时所采用的相同防范措施，如使用线程本地内存和关键部分。</span><span class="sxs-lookup"><span data-stu-id="8a915-136">It is worth restating that Excel does not run more than one command at once, so you do not need to employ the same precautions as when you are writing thread-safe functions, such as the use of thread-local memory and critical sections.</span></span>
  
## <a name="what-is-and-is-not-considered-thread-safe-by-excel"></a><span data-ttu-id="8a915-137">Excel 视为安全线程和非安全线程的项</span><span class="sxs-lookup"><span data-stu-id="8a915-137">What is and is not considered thread safe by Excel</span></span>
<span data-ttu-id="8a915-138"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="8a915-138"></span></span>

<span data-ttu-id="8a915-139">Excel 仅将以下项视为线程安全项：</span><span class="sxs-lookup"><span data-stu-id="8a915-139">Excel only considers the following as thread safe:</span></span>
  
- <span data-ttu-id="8a915-140">Excel 中的所有一元运算符和二元运算符。</span><span class="sxs-lookup"><span data-stu-id="8a915-140">All unary and binary operators in Excel.</span></span>
    
- <span data-ttu-id="8a915-141">自 Excel 2007 起引入的几乎所有内置工作表函数（见例外列表）</span><span class="sxs-lookup"><span data-stu-id="8a915-141">Almost all built-in worksheet functions starting in Excel 2007 (see exceptions list)</span></span>
    
- <span data-ttu-id="8a915-142">已显式注册为线程安全的 XLL 加载项函数。</span><span class="sxs-lookup"><span data-stu-id="8a915-142">XLL add-in functions that have been explicitly registered as thread-safe.</span></span>
    
<span data-ttu-id="8a915-143">内置非线程安全工作表函数包括：</span><span class="sxs-lookup"><span data-stu-id="8a915-143">The built-in worksheet functions that are not thread safe are:</span></span>
  
- <span data-ttu-id="8a915-144">**PHONETIC**</span><span class="sxs-lookup"><span data-stu-id="8a915-144">**PHONETIC**</span></span>
    
- <span data-ttu-id="8a915-145">**CELL**（如果使用的是“format”或“address”参数）</span><span class="sxs-lookup"><span data-stu-id="8a915-145">**CELL** when either the "format" or "address" argument is used</span></span> 
    
- <span data-ttu-id="8a915-146">**INDIRECT**</span><span class="sxs-lookup"><span data-stu-id="8a915-146">**INDIRECT**</span></span>
    
- <span data-ttu-id="8a915-147">**GETPIVOTDATA**</span><span class="sxs-lookup"><span data-stu-id="8a915-147">**GETPIVOTDATA**</span></span>
    
- <span data-ttu-id="8a915-148">**CUBEMEMBER**</span><span class="sxs-lookup"><span data-stu-id="8a915-148">**CUBEMEMBER**</span></span>
    
- <span data-ttu-id="8a915-149">**CUBEVALUE**</span><span class="sxs-lookup"><span data-stu-id="8a915-149">**CUBEVALUE**</span></span>
    
- <span data-ttu-id="8a915-150">**CUBEMEMBERPROPERTY**</span><span class="sxs-lookup"><span data-stu-id="8a915-150">**CUBEMEMBERPROPERTY**</span></span>
    
- <span data-ttu-id="8a915-151">**CUBESET**</span><span class="sxs-lookup"><span data-stu-id="8a915-151">**CUBESET**</span></span>
    
- <span data-ttu-id="8a915-152">**CUBERANKEDMEMBER**</span><span class="sxs-lookup"><span data-stu-id="8a915-152">**CUBERANKEDMEMBER**</span></span>
    
- <span data-ttu-id="8a915-153">**CUBEKPIMEMBER**</span><span class="sxs-lookup"><span data-stu-id="8a915-153">**CUBEKPIMEMBER**</span></span>
    
- <span data-ttu-id="8a915-154">**CUBESETCOUNT**</span><span class="sxs-lookup"><span data-stu-id="8a915-154">**CUBESETCOUNT**</span></span>
    
- <span data-ttu-id="8a915-155">**ADDRESS**（其中第五个参数 (sheet_name) 已给定）</span><span class="sxs-lookup"><span data-stu-id="8a915-155">**ADDRESS** where the fifth parameter (the sheet_name) is given</span></span> 
    
- <span data-ttu-id="8a915-156">任何引用数据透视表的数据库函数（**DSUM**、**DAVERAGE** 等）</span><span class="sxs-lookup"><span data-stu-id="8a915-156">Any database function (**DSUM**, **DAVERAGE**, and so on) that refers to a pivot table</span></span>
    
- <span data-ttu-id="8a915-157">**ERROR.TYPE**</span><span class="sxs-lookup"><span data-stu-id="8a915-157">**ERROR.TYPE**</span></span>
    
- <span data-ttu-id="8a915-158">**HYPERLINK**</span><span class="sxs-lookup"><span data-stu-id="8a915-158">**HYPERLINK**</span></span>
    
<span data-ttu-id="8a915-159">具体而言，以下项被视为非安全线程项：</span><span class="sxs-lookup"><span data-stu-id="8a915-159">To be explicit, the following are considered to be unsafe:</span></span>
  
- <span data-ttu-id="8a915-160">VBA 用户定义函数</span><span class="sxs-lookup"><span data-stu-id="8a915-160">VBA user-defined functions</span></span>
    
- <span data-ttu-id="8a915-161">COM 加载项用户定义函数</span><span class="sxs-lookup"><span data-stu-id="8a915-161">COM add-in user-defined functions</span></span>
    
- <span data-ttu-id="8a915-162">XLM 宏工作表用户定义函数</span><span class="sxs-lookup"><span data-stu-id="8a915-162">XLM macro-sheet user-defined functions</span></span>
    
- <span data-ttu-id="8a915-163">未显式注册为线程安全的 XLL 加载项函数</span><span class="sxs-lookup"><span data-stu-id="8a915-163">XLL add-in functions not explicitly registered as thread safe</span></span>
    
<span data-ttu-id="8a915-164">潜在影响是，以下操作和函数是非线程安全，无法从注册为线程安全的 XLL 函数中调用它们：</span><span class="sxs-lookup"><span data-stu-id="8a915-164">The implications are that the following operations and functions are not thread-safe, and fail if they are called from an XLL function registered as thread safe:</span></span>
  
- <span data-ttu-id="8a915-165">调用 XLM 信息函数，例如，**xlfGetCell** (**GET.CELL**)。</span><span class="sxs-lookup"><span data-stu-id="8a915-165">Calls to XLM information functions, for example, **xlfGetCell** (**GET.CELL**).</span></span>
    
- <span data-ttu-id="8a915-166">调用 **xlfSetName** (**SET.NAME**)，以定义或删除 XLL 内部名称。</span><span class="sxs-lookup"><span data-stu-id="8a915-166">Calls to **xlfSetName** (**SET.NAME**) to define or delete XLL-internal names.</span></span>
    
- <span data-ttu-id="8a915-167">使用 **xlUDF** 调用非线程安全的用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="8a915-167">Calls to thread-unsafe user-defined functions using **xlUDF**.</span></span>
    
- <span data-ttu-id="8a915-168">对包含非线程安全函数或包含定义内有非线程安全函数的已定义名称的表达式调用 [xlfEvaluate](xlfevaluate.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="8a915-168">Calls to the [xlfEvaluate](xlfevaluate.md) function for expressions that contain thread-unsafe functions or that contain defined names whose definitions contain thread-unsafe functions.</span></span> 
    
- <span data-ttu-id="8a915-169">调用 [xlAbort](xlabort.md) 函数，以清除中断条件。</span><span class="sxs-lookup"><span data-stu-id="8a915-169">Calls to the [xlAbort](xlabort.md) function to clear a break condition.</span></span> 
    
- <span data-ttu-id="8a915-170">调用 [xlCoerce](xlcoerce.md) 函数，以获取未计算单元格引用的值。</span><span class="sxs-lookup"><span data-stu-id="8a915-170">Calls to the [xlCoerce](xlcoerce.md) function to get the value of an uncalculated cell reference.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8a915-171">XLL 工作表函数不得调用 C API 命令（例如，**xlcSave**），无论是否已注册为线程安全。</span><span class="sxs-lookup"><span data-stu-id="8a915-171">XLL worksheet functions are not permitted to call C API commands, for example, **xlcSave**, regardless of whether they have been registered as thread safe or not.</span></span> 
  
<span data-ttu-id="8a915-172">假设声明为线程安全的 XLL 函数无法调用 XLM 信息函数或引用未计算单元格，Excel 不允许注册为宏工作表等效项的 XLL 函数也注册为线程安全。</span><span class="sxs-lookup"><span data-stu-id="8a915-172">Given that XLL functions declared as thread safe cannot call XLM information functions or reference uncalculated cells, Excel does not permit XLL functions that are registered as macro sheet equivalents to also be registered as thread safe.</span></span> <span data-ttu-id="8a915-173">因此，无法尝试使用 **xlCoerce** 获取未计算单元格引用的值，并看到 **xlretUncalced** 错误。</span><span class="sxs-lookup"><span data-stu-id="8a915-173">Therefore attempting to get the value of an uncalculated cell reference using **xlCoerce** fails with an **xlretUncalced** error.</span></span> <span data-ttu-id="8a915-174">也无法调用 XLM 信息函数，并看到 **xlretFailed** 错误。</span><span class="sxs-lookup"><span data-stu-id="8a915-174">Calling an XLM information function fails with an **xlretFailed** error.</span></span> <span data-ttu-id="8a915-175">上面列出的其他点也会失败，并看到 Excel C API 中引入的错误代码：**xlretNotThreadSafe**。</span><span class="sxs-lookup"><span data-stu-id="8a915-175">The other points listed previously fail with an error code introduced in the Excel C API: **xlretNotThreadSafe**.</span></span> 
  
<span data-ttu-id="8a915-176">所有仅限 C API 的回调函数都是线程安全函数：</span><span class="sxs-lookup"><span data-stu-id="8a915-176">The C API-only call-back functions are all thread safe:</span></span>
  
- <span data-ttu-id="8a915-177">**xlCoerce**（但例外是无法强制转换未计算单元格引用）</span><span class="sxs-lookup"><span data-stu-id="8a915-177">**xlCoerce** (except although coercion of uncalculated cell references fails)</span></span> 
    
- <span data-ttu-id="8a915-178">**xlFree**</span><span class="sxs-lookup"><span data-stu-id="8a915-178">**xlFree**</span></span>
    
- <span data-ttu-id="8a915-179">**xlStack**</span><span class="sxs-lookup"><span data-stu-id="8a915-179">**xlStack**</span></span>
    
- <span data-ttu-id="8a915-180">**xlSheetId**</span><span class="sxs-lookup"><span data-stu-id="8a915-180">**xlSheetId**</span></span>
    
- <span data-ttu-id="8a915-181">**xlSheetNm**</span><span class="sxs-lookup"><span data-stu-id="8a915-181">**xlSheetNm**</span></span>
    
- <span data-ttu-id="8a915-182">**xlAbort**（用于清除中断条件时例外）</span><span class="sxs-lookup"><span data-stu-id="8a915-182">**xlAbort** (except when used to clear a break condition)</span></span> 
    
- <span data-ttu-id="8a915-183">**xlGetInst**</span><span class="sxs-lookup"><span data-stu-id="8a915-183">**xlGetInst**</span></span>
    
- <span data-ttu-id="8a915-184">**xlGetHwnd**</span><span class="sxs-lookup"><span data-stu-id="8a915-184">**xlGetHwnd**</span></span>
    
- <span data-ttu-id="8a915-185">**xlGetBinaryName**</span><span class="sxs-lookup"><span data-stu-id="8a915-185">**xlGetBinaryName**</span></span>
    
- <span data-ttu-id="8a915-186">**xlDefineBinaryName**</span><span class="sxs-lookup"><span data-stu-id="8a915-186">**xlDefineBinaryName**</span></span>
    
<span data-ttu-id="8a915-187">有一种例外情况是 **xlSet** 函数，在任何情况下，它都是命令等效项，因此无法从任何工作表函数中进行调用。</span><span class="sxs-lookup"><span data-stu-id="8a915-187">The one exception is the **xlSet** function, which is, in any case, a command-equivalent and so cannot be called from any worksheet function.</span></span> 
  
<span data-ttu-id="8a915-188">可使用 Excel 将 XLL 工作表函数注册为线程安全。</span><span class="sxs-lookup"><span data-stu-id="8a915-188">An XLL worksheet function can be registered with Excel as thread safe.</span></span> <span data-ttu-id="8a915-189">这会指示 Excel 可以在多线程中安全地同步调用函数，尽管必须确保情况的确如此。</span><span class="sxs-lookup"><span data-stu-id="8a915-189">This tells Excel that the function can be called safely and simultaneously on multiple threads, although you must make sure this is really the case.</span></span> <span data-ttu-id="8a915-190">如果注册为线程安全的函数之后的行为不安全，可能会破坏 Excel 的稳定性。</span><span class="sxs-lookup"><span data-stu-id="8a915-190">You can possibly destabilize Excel if a function registered as thread safe then behaves unsafely.</span></span>
  
## <a name="registering-xll-functions-as-thread-safe"></a><span data-ttu-id="8a915-191">将 XLL 函数注册为线程安全</span><span class="sxs-lookup"><span data-stu-id="8a915-191">Registering XLL functions as thread safe</span></span>
<span data-ttu-id="8a915-192"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="8a915-192"></span></span>

<span data-ttu-id="8a915-193">编写线程安全函数时，开发人员必须遵守如下规则：</span><span class="sxs-lookup"><span data-stu-id="8a915-193">The rules that a developer must obey when writing thread-safe functions are as follows:</span></span>
  
- <span data-ttu-id="8a915-194">不要在可能是非线程安全的其他 DLL 中调用资源。</span><span class="sxs-lookup"><span data-stu-id="8a915-194">Do not call resources in other DLLs that may not be thread safe.</span></span>
    
- <span data-ttu-id="8a915-195">不要通过 C API 或 COM 执行任何非线程安全调用。</span><span class="sxs-lookup"><span data-stu-id="8a915-195">Do not make any thread-unsafe calls via the C API or COM.</span></span>
    
- <span data-ttu-id="8a915-196">使用关键部分来保护多线程可能同时使用的资源。</span><span class="sxs-lookup"><span data-stu-id="8a915-196">Protect resources that could be used simultaneously by more than one thread using critical sections.</span></span>
    
- <span data-ttu-id="8a915-197">对线程专用存储使用线程本地内存，并将函数中的静态变量替换为线程本地变量。</span><span class="sxs-lookup"><span data-stu-id="8a915-197">Use thread-local memory for thread-specific storage, and replace static variables within functions with thread-local variables.</span></span>
    
<span data-ttu-id="8a915-198">Excel 施加了以下额外限制：不能将线程安全函数注册为宏工作表等效项，因此既无法调用 XLM 信息函数，也无法获取未重新计算单元格的值。</span><span class="sxs-lookup"><span data-stu-id="8a915-198">Excel imposes an additional restriction: thread-safe functions cannot be registered as macro-sheet equivalents, and therefore cannot call XLM information functions or get the values of un-recalculated cells.</span></span>
  
## <a name="memory-contention"></a><span data-ttu-id="8a915-199">内存争用</span><span class="sxs-lookup"><span data-stu-id="8a915-199">Memory contention</span></span>
<span data-ttu-id="8a915-200"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="8a915-200"></span></span>

<span data-ttu-id="8a915-201">多线程系统必须解决以下两个基本问题：</span><span class="sxs-lookup"><span data-stu-id="8a915-201">Multithreaded systems must address two fundamental issues:</span></span>
  
- <span data-ttu-id="8a915-202">如何保护必须供多线程读取或写入的内存。</span><span class="sxs-lookup"><span data-stu-id="8a915-202">How to protect memory that must be read from, or written to, by more than one thread.</span></span>
    
- <span data-ttu-id="8a915-203">如何创建和访问与执行线程关联（所以也是专用）的内存。</span><span class="sxs-lookup"><span data-stu-id="8a915-203">How to create and access memory that is associated with, and so private to, the executing thread.</span></span>
    
<span data-ttu-id="8a915-204">Windows 操作系统和 Windows 软件开发工具包 (SDK) 提供了可解决这两个问题的工具：分别是关键部分和线程本地存储 (TLS) API。</span><span class="sxs-lookup"><span data-stu-id="8a915-204">The Windows operating system and Windows Software Development Kit (SDK) provide tools for both of these: critical sections and the thread-local storage (TLS) API respectively.</span></span> <span data-ttu-id="8a915-205">有关详细信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="8a915-205">For more information, see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
<span data-ttu-id="8a915-206">可能会出现第一个问题的情况包括，例如当两个工作表函数（或同一函数的两个同时运行实例）需要访问或修改 DLL 项目中的全局变量时。</span><span class="sxs-lookup"><span data-stu-id="8a915-206">The first issue can arise, for example, when two worksheet functions (or two simultaneously running instances of the same function) need to access or modify a global variable in a DLL project.</span></span> <span data-ttu-id="8a915-207">请注意，此类全局变量可能会隐藏在类对象的全局可访问实例中。</span><span class="sxs-lookup"><span data-stu-id="8a915-207">Remember that such a global variable might be hidden in a globally accessible instance of a class object.</span></span>
  
<span data-ttu-id="8a915-208">可能会出现第二个问题的情况包括，例如当工作表函数在函数体代码中声明静态变量或对象时。</span><span class="sxs-lookup"><span data-stu-id="8a915-208">The second issue can arise, for example, when a worksheet function declares a static variable or object within the function body code.</span></span> <span data-ttu-id="8a915-209">C/C++ 编译器仅创建所有线程都使用的一个副本。</span><span class="sxs-lookup"><span data-stu-id="8a915-209">The C/C++ compiler only creates a single copy that all threads use.</span></span> <span data-ttu-id="8a915-210">也就是说，函数的一个实例可能会更改值，而其他线程中的另一个实例可能会假定值是之前设置的。</span><span class="sxs-lookup"><span data-stu-id="8a915-210">This means one instance of the function could change the value, while another on a different thread might be assuming the value is what it previously set.</span></span>
  
## <a name="example-applications-of-mtr"></a><span data-ttu-id="8a915-211">MTR 应用示例</span><span class="sxs-lookup"><span data-stu-id="8a915-211">Example applications of MTR</span></span>
<span data-ttu-id="8a915-212"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="8a915-212"></span></span>

<span data-ttu-id="8a915-213">所有导出工作表函数的 XLL 都可以利用 Excel 中的多线程重新计算 (MTR)，前提是这些函数无需执行非线程安全操作。</span><span class="sxs-lookup"><span data-stu-id="8a915-213">Any XLL that exports worksheet functions can take advantage of multithreaded recalculation (MTR) in Excel provided that those functions do not need to perform thread-unsafe actions.</span></span> <span data-ttu-id="8a915-214">这样一来，Excel 能够尽快重新计算依赖它们的工作簿，因此适用于任何应用场景。</span><span class="sxs-lookup"><span data-stu-id="8a915-214">This enables Excel to recalculate workbooks that depend on them as quickly as possible and is therefore desirable whatever the application.</span></span>
  
<span data-ttu-id="8a915-215">具体而言，MTR 对调用用户定义函数 (UDF) 的工作簿的重新计算时间有重大影响，这些函数本身调用外部进程来获取理想结果。</span><span class="sxs-lookup"><span data-stu-id="8a915-215">Specifically, MTR has an enormous impact on the recalculation time of workbooks that call user-defined functions (UDFs) that themselves call external processes to obtain the desired result.</span></span> <span data-ttu-id="8a915-216">尤其是，假设 UDF 调用可同时处理多个请求的远程服务器，且工作簿包含对相应函数的多个调用。</span><span class="sxs-lookup"><span data-stu-id="8a915-216">In particular, consider a UDF that calls a remote server that can process many requests simultaneously and a workbook containing many calls to that function.</span></span> <span data-ttu-id="8a915-217">如果工作簿重新计算是单线程，那么必须先完成对 UDF 和远程服务器的每次调用，然后才能执行下一个调用。</span><span class="sxs-lookup"><span data-stu-id="8a915-217">If recalculation of the workbook is single-threaded, each call to the UDF, and so to the remote server, must complete before the next one can be made.</span></span> <span data-ttu-id="8a915-218">这就浪费了服务器一次处理多个调用的功能。</span><span class="sxs-lookup"><span data-stu-id="8a915-218">This wastes the server's ability to process many calls at once.</span></span> <span data-ttu-id="8a915-219">如果工作簿重新计算是多线程，Excel 就可以同时或快速连续地执行多个调用。</span><span class="sxs-lookup"><span data-stu-id="8a915-219">If recalculation of the workbook is multithreaded, Excel can make multiple calls at the same time or in rapid succession.</span></span>
  
<span data-ttu-id="8a915-220">如果 Excel 配置为使用与服务器相同的线程数（称之为 N），且工作簿的依赖关系树拓扑允许此配置，那么总重新计算时间可能会大约缩短为单线程计算时间的 1/N。</span><span class="sxs-lookup"><span data-stu-id="8a915-220">If Excel is configured to use the same number of threads as the server—call it N—and the topology of the dependency tree of the workbook permits it, the total recalculation time could be reduced to something approaching 1/N of the single-threaded calculation time.</span></span> <span data-ttu-id="8a915-221">即使（运行工作簿的）客户端计算机只有一个处理器，可能也是这样，尤其是当调用服务器所花费的时间相对于服务器处理调用所花费的时间较短时。</span><span class="sxs-lookup"><span data-stu-id="8a915-221">This may be true even where the client computer (on which the workbook is running) only has one processor, especially where the time taken to make the call to the server is small relative to the time it takes the server to process the call.</span></span> 
  
<span data-ttu-id="8a915-222">每个额外线程都会产生操作系统开销。</span><span class="sxs-lookup"><span data-stu-id="8a915-222">There is operating system overhead for each additional thread.</span></span> <span data-ttu-id="8a915-223">因此，可能必须对给定工作簿、给定服务器和客户端计算机进行某试验，以确定应指示 Excel 使用的最佳线程数。</span><span class="sxs-lookup"><span data-stu-id="8a915-223">Therefore some experimentation might be required for a given workbook and a given server and client computer to find the optimum number of threads Excel should be told to use.</span></span> 
  
<span data-ttu-id="8a915-224">例如，假设正在运行 Excel 的是单处理器计算机，且工作簿包含 1,000 个单元格。</span><span class="sxs-lookup"><span data-stu-id="8a915-224">For example, consider a single-processor computer that is running Excel and a workbook that contains 1,000 cells.</span></span> <span data-ttu-id="8a915-225">它会调用 UDF，进而调用一个或多个远程服务器。</span><span class="sxs-lookup"><span data-stu-id="8a915-225">It calls a UDF, which in turn calls one or more remote servers.</span></span> <span data-ttu-id="8a915-226">假定这 1,000 个单元格不相互依赖，因此 Excel 无需等到一个调用完成后再执行下一个调用。</span><span class="sxs-lookup"><span data-stu-id="8a915-226">Assume that the 1,000 cells do not depend upon each other, so that Excel does not have to wait for one call to complete before calling the next.</span></span> <span data-ttu-id="8a915-227">（此约束可以有所放宽，而不影响此示例。）如果服务器可以同时处理 100 个请求，且 Excel 配置为使用 100 个线程，那么执行时间可以缩短为仅单线程执行时间的 1/100。</span><span class="sxs-lookup"><span data-stu-id="8a915-227">(Some relaxation of this constraint is possible without affecting this example.) If the servers can process 100 requests simultaneously, and Excel is configured to use 100 threads, the execution time can be reduced to as little as 1/100th of that where only one thread is used.</span></span> <span data-ttu-id="8a915-228">与向每个线程分配调用的 Excel 和管理 100 个线程的操作系统相关的开销表明实际时间缩短不会如此明显。</span><span class="sxs-lookup"><span data-stu-id="8a915-228">The overhead that is associated with Excel allocating calls to each thread and the operating system managing 100 threads means that, in practice, the reduction will not be quite this great.</span></span> <span data-ttu-id="8a915-229">这其中还有一个隐含假定，即服务器可以很好地缩放，且让它同时处理 100 个任务不会显著影响各个任务完成时间。</span><span class="sxs-lookup"><span data-stu-id="8a915-229">There is also an implicit assumption here that the server scales well, and asking it to process 100 tasks concurrently will not affect individual task completion times significantly.</span></span>
  
<span data-ttu-id="8a915-230">这项技术可能会带来重要优势的一个实际应用是，可以将 Monte-Carlo 方法和其他数字密集型任务拆分为更小的子任务，从而能够在服务器中进行场化。</span><span class="sxs-lookup"><span data-stu-id="8a915-230">One practical application in which this technique can have an important benefit is that of Monte-Carlo methods, as well as other numerically intensive tasks that can be split into smaller sub-tasks that can be farmed out to servers.</span></span>
  
## <a name="excel-services-considerations"></a><span data-ttu-id="8a915-231">Excel Services 注意事项</span><span class="sxs-lookup"><span data-stu-id="8a915-231">Excel Services considerations</span></span>
<span data-ttu-id="8a915-232"><a name="xl2007xllsdk_threadsafe"> </a></span><span class="sxs-lookup"><span data-stu-id="8a915-232"></span></span>

<span data-ttu-id="8a915-233">Excel Services 支持在服务器上加载、计算和呈现 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="8a915-233">Excel Services supports the loading, calculating, and rendering of Excel spreadsheets on a server.</span></span> <span data-ttu-id="8a915-234">然后，用户可使用标准浏览器工具来访问电子表格并与之交互。</span><span class="sxs-lookup"><span data-stu-id="8a915-234">Users can then access and interact with the spreadsheets by using standard browser tools.</span></span>
  
<span data-ttu-id="8a915-235">Excel Services UDF 是使用 Microsoft .NET Framework 托管代码创建而成，可通过 .NET 程序集使用。</span><span class="sxs-lookup"><span data-stu-id="8a915-235">Excel Services UDFs are created using Microsoft .NET Framework managed code and made available though a .NET assembly.</span></span> <span data-ttu-id="8a915-236">Excel Services 不支持 XLL。</span><span class="sxs-lookup"><span data-stu-id="8a915-236">XLLs are not supported by Excel Services.</span></span> <span data-ttu-id="8a915-237">托管代码服务器 UDF 资源可以调用 XLL 来使用它的功能，这样用户可以在使用服务器加载的工作簿和客户端加载的工作簿时使用相同功能。</span><span class="sxs-lookup"><span data-stu-id="8a915-237">A managed code server UDF resource can call into an XLL to access its functionality, so that the user can have the same functionality with a server-loaded workbook as with a client-loaded workbook.</span></span>
  
<span data-ttu-id="8a915-238">若要让 XLL 函数以这种方式可用，必须将它们包装在 .NET 程序集中，此程序集将参数和本机数据类型中的返回值转换为 .NET Framework 托管数据类型，并调用 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="8a915-238">To make an XLL's functions available in this way, they must therefore be wrapped in a .NET assembly that converts arguments and return values from the native data types to the .NET Framework managed data types, and that calls the XLL functions.</span></span> <span data-ttu-id="8a915-239">.NET 包装器会为访问的每个 XLL 函数导出一个服务器 UDF。</span><span class="sxs-lookup"><span data-stu-id="8a915-239">The .NET wrapper would export one server UDF for each XLL function being accessed.</span></span> <span data-ttu-id="8a915-240">附加要求是，这样调用的所有 XLL 函数都必须是线程安全函数。</span><span class="sxs-lookup"><span data-stu-id="8a915-240">An additional requirement is that any XLL functions called in this way must be thread safe.</span></span> <span data-ttu-id="8a915-241">由于 XLL 函数并非像在客户端 Excel 中一样注册，因此服务器和 .NET 包装器无法强制执行它们必须是线程安全函数的要求。</span><span class="sxs-lookup"><span data-stu-id="8a915-241">Because the XLL functions are not registered in the way that they are with client Excel, the server and the .NET wrapper have no way of enforcing that they are thread safe.</span></span> <span data-ttu-id="8a915-242">XLL 开发人员有责任确保这一点。</span><span class="sxs-lookup"><span data-stu-id="8a915-242">It is the responsibility of the XLL developer to ensure this.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a915-243">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a915-243">See also</span></span>

- [<span data-ttu-id="8a915-244">Excel 重新计算</span><span class="sxs-lookup"><span data-stu-id="8a915-244">Excel Recalculation</span></span>](excel-recalculation.md)  
- [<span data-ttu-id="8a915-245">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="8a915-245">Memory Management in Excel</span></span>](memory-management-in-excel.md) 
- [<span data-ttu-id="8a915-246">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="8a915-246">Accessing XLL Code in Excel</span></span>](accessing-xll-code-in-excel.md)  
- [<span data-ttu-id="8a915-247">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="8a915-247">Excel Programming Concepts</span></span>](excel-programming-concepts.md)  
- [<span data-ttu-id="8a915-248">Excel XLL SDK API 函数引用</span><span class="sxs-lookup"><span data-stu-id="8a915-248">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)

