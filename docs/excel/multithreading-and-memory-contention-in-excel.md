---
title: Excel 中的多线程处理和内存争用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- 多线程中的 excel、 Excel、 函数 [Excel 2007]、 线程安全、 线程安全的内存争用函数 [Excel 2007]，线程本地内存 [Excel 2007]
localization_priority: Normal
ms.assetid: 86e1e842-f433-4ea9-8b13-ad2515fc50d8
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fb0eddfff2f34307143bb896fd451de357f2b639
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773809"
---
# <a name="multithreading-and-memory-contention-in-excel"></a><span data-ttu-id="bdcde-104">Excel 中的多线程处理和内存争用</span><span class="sxs-lookup"><span data-stu-id="bdcde-104">Multithreading and Memory Contention in Excel</span></span>

 <span data-ttu-id="bdcde-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bdcde-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="bdcde-106">早版本的 Microsoft Excel 比在 Excel 2007 使用单个线程的所有工作表计算。</span><span class="sxs-lookup"><span data-stu-id="bdcde-106">Versions of Microsoft Excel earlier than Excel 2007 use a single thread for all worksheet calculations.</span></span> <span data-ttu-id="bdcde-107">但是，从 Excel 2007 开始，Excel 可以配置用于介于 1 到 1024年并发线程工作表计算。</span><span class="sxs-lookup"><span data-stu-id="bdcde-107">However, starting in Excel 2007, Excel can be configured to use from 1 to 1024 concurrent threads for worksheet calculation.</span></span> <span data-ttu-id="bdcde-108">多处理器或多核计算机上, 默认的线程数等于内核处理器的数量。</span><span class="sxs-lookup"><span data-stu-id="bdcde-108">On a multi-processor or multi-core computer, the default number of threads is equal to the number of processors or cores.</span></span> <span data-ttu-id="bdcde-109">因此，线程安全单元格或仅包含线程安全的函数的单元格都可以分配给并发线程，受到需要计算其引用单元格后的常用重新计算逻辑。</span><span class="sxs-lookup"><span data-stu-id="bdcde-109">Therefore, thread-safe cells, or cells that only contain functions that are thread safe, can be allotted to concurrent threads, subject to the usual recalculation logic of needing to be calculated after their precedents.</span></span>
  
## <a name="thread-safe-functions"></a><span data-ttu-id="bdcde-110">线程安全功能</span><span class="sxs-lookup"><span data-stu-id="bdcde-110">Thread-Safe Functions</span></span>

<span data-ttu-id="bdcde-111">线程安全了大部分启动 Excel 2007 中内置的工作表函数。</span><span class="sxs-lookup"><span data-stu-id="bdcde-111">Most of the built-in worksheet functions starting in Excel 2007 are thread safe.</span></span> <span data-ttu-id="bdcde-112">您还可以编写并注册为正在线程安全的 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="bdcde-112">You can also write and register XLL functions as being thread safe.</span></span> <span data-ttu-id="bdcde-113">Excel 使用一个线程 （其主线程） 呼叫所有命令、 线程不安全的功能、 **xlAuto**函数 （除了[xlAutoFree](xlautofree-xlautofree12.md)和**xlAutoFree12**） 和 COM 和 Visual Basic for Applications (VBA) 函数。</span><span class="sxs-lookup"><span data-stu-id="bdcde-113">Excel uses one thread (its main thread) to call all commands, thread-unsafe functions, **xlAuto** functions (except [xlAutoFree](xlautofree-xlautofree12.md) and **xlAutoFree12**), and COM and Visual Basic for Applications (VBA) functions.</span></span>
  
<span data-ttu-id="bdcde-114">其中 XLL 函数返回**XLOPER**或**XLOPER12** **xlbitDLLFree**设置，Excel 将使用相同的线程进行函数调用来调用**xlAutoFree**或**xlAutoFree12**。</span><span class="sxs-lookup"><span data-stu-id="bdcde-114">Where an XLL function returns an **XLOPER** or **XLOPER12** with **xlbitDLLFree** set, Excel uses the same thread on which the function call was made to call **xlAutoFree** or **xlAutoFree12**.</span></span> <span data-ttu-id="bdcde-115">调用**xlAutoFree**或**xlAutoFree12**由该线程上的下一个函数调用之前。</span><span class="sxs-lookup"><span data-stu-id="bdcde-115">The call to **xlAutoFree** or **xlAutoFree12** is made before the next function call on that thread.</span></span> 
  
<span data-ttu-id="bdcde-116">对于 XLL 开发人员，有以下好处创建线程安全功能：</span><span class="sxs-lookup"><span data-stu-id="bdcde-116">For XLL developers, there are benefits for creating thread-safe functions:</span></span>
  
- <span data-ttu-id="bdcde-117">它们允许 Excel 充分利用多处理器或多核计算机。</span><span class="sxs-lookup"><span data-stu-id="bdcde-117">They allow Excel to make the most of a multi-processor or multi-core computer.</span></span>
    
- <span data-ttu-id="bdcde-118">他们打开比可以进行更有效地使用远程服务器的可能性使用单个线程。</span><span class="sxs-lookup"><span data-stu-id="bdcde-118">They open up the possibility of using remote servers much more efficiently than can be done using a single thread.</span></span>
    
<span data-ttu-id="bdcde-119">假设您有已配置为使用，请说， *N*线程的单处理器计算机。</span><span class="sxs-lookup"><span data-stu-id="bdcde-119">Suppose that you have a single-processor computer that has been configured to use, say,  *N*  threads.</span></span> <span data-ttu-id="bdcde-120">假设电子表格正在运行，使大量对 XLL 函数的调用，以打开发送请求数据或计算执行到远程服务器或服务器群集。</span><span class="sxs-lookup"><span data-stu-id="bdcde-120">Suppose that a spreadsheet is running that makes a large number of calls to an XLL function that in turn sends a request for data or for a calculation to be performed to a remote server or cluster of servers.</span></span> <span data-ttu-id="bdcde-121">受到相关性树的拓扑，Excel 无法几乎同时调用的函数 N 时间。</span><span class="sxs-lookup"><span data-stu-id="bdcde-121">Subject to the topology of the dependency tree, Excel could call the function N times almost simultaneously.</span></span> <span data-ttu-id="bdcde-122">假设或多个服务器都充分 fast 或并行，可减少电子表格的重新计算时间为 1/从一个因子得多</span><span class="sxs-lookup"><span data-stu-id="bdcde-122">Provided that the server or servers are sufficiently fast or parallel, the recalculation time of the spreadsheet could be reduced by as much as a factor of 1/N.</span></span> 
  
<span data-ttu-id="bdcde-123">编写线程安全函数中的关键问题正确处理争夺资源。</span><span class="sxs-lookup"><span data-stu-id="bdcde-123">The key issue in writing thread-safe functions is handling contention for resources correctly.</span></span> <span data-ttu-id="bdcde-124">这通常意味着内存争用，它可以分为两个问题：</span><span class="sxs-lookup"><span data-stu-id="bdcde-124">This usually means memory contention, and it can be broken down into two issues:</span></span>
  
- <span data-ttu-id="bdcde-125">仅将此线程使用如何创建您知道的内存。</span><span class="sxs-lookup"><span data-stu-id="bdcde-125">How to create memory that you know will only be used by this thread.</span></span>
    
- <span data-ttu-id="bdcde-126">如何确保共享的内存安全地访问由多个线程。</span><span class="sxs-lookup"><span data-stu-id="bdcde-126">How to ensure that shared memory is accessed by multiple threads safely.</span></span>
    
<span data-ttu-id="bdcde-127">首先要注意的是 XLL 哪些内存访问所有线程，且新增仅可访问当前执行的线程。</span><span class="sxs-lookup"><span data-stu-id="bdcde-127">The first thing to be aware of is what memory in an XLL is accessible by all threads, and what is only accessible by the currently executing thread.</span></span>
  
 <span data-ttu-id="bdcde-128">**访问所有线程**</span><span class="sxs-lookup"><span data-stu-id="bdcde-128">**Accessible by all threads**</span></span>
  
- <span data-ttu-id="bdcde-129">变量、 结构和类实例外函数的主体的声明。</span><span class="sxs-lookup"><span data-stu-id="bdcde-129">Variables, structures, and class instances declared outside the body of a function.</span></span>
    
- <span data-ttu-id="bdcde-130">函数的正文内声明的静态变量。</span><span class="sxs-lookup"><span data-stu-id="bdcde-130">Static variables declared within the body of a function.</span></span>
    
<span data-ttu-id="bdcde-131">在这两种情况，内存设置留出中创建的此实例的 DLL 的 DLL 的内存块。</span><span class="sxs-lookup"><span data-stu-id="bdcde-131">In these two cases, memory is set aside in the DLL's memory block created for this instance of the DLL.</span></span> <span data-ttu-id="bdcde-132">如果另一个应用程序实例加载 DLL，它获取其自己的内存副本，以便不会从外部 DLL 此实例，这些资源争用。</span><span class="sxs-lookup"><span data-stu-id="bdcde-132">If another application instance loads the DLL, it gets its own copy of that memory so that there is no contention for these resources from outside this instance of the DLL.</span></span>
  
 <span data-ttu-id="bdcde-133">**只能由当前线程访问**</span><span class="sxs-lookup"><span data-stu-id="bdcde-133">**Accessible only by the current thread**</span></span>
  
- <span data-ttu-id="bdcde-134">（包括函数参数） 的函数代码中的自动变量。</span><span class="sxs-lookup"><span data-stu-id="bdcde-134">Automatic variables within function code (including function arguments).</span></span>
    
<span data-ttu-id="bdcde-135">在这种情况下，在每个实例函数调用堆栈留出设置内存。</span><span class="sxs-lookup"><span data-stu-id="bdcde-135">In this case, memory is set aside on the stack for each instance of the function call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bdcde-136">动态分配的内存范围取决于指向它的指针的范围： 如果将指针是可访问所有线程，也是内存。</span><span class="sxs-lookup"><span data-stu-id="bdcde-136">The scope of dynamically allocated memory depends on the scope of the pointer that points to it: if the pointer is accessible by all threads, the memory is also.</span></span> <span data-ttu-id="bdcde-137">指针是自动变量函数中的，如果是有效地专用于该线程分配的内存。</span><span class="sxs-lookup"><span data-stu-id="bdcde-137">If the pointer is an automatic variable in a function, the allocated memory is effectively private to that thread.</span></span> 
  
## <a name="memory-accessible-by-only-one-thread-thread-local-memory"></a><span data-ttu-id="bdcde-138">只能由一个线程可访问的内存： 线程本地内存</span><span class="sxs-lookup"><span data-stu-id="bdcde-138">Memory Accessible by Only One Thread: Thread-Local Memory</span></span>

<span data-ttu-id="bdcde-139">静态变量的函数的正文内都可以访问所有线程，使用它们的函数不清楚地线程安全。</span><span class="sxs-lookup"><span data-stu-id="bdcde-139">Given that static variables within the body of a function are accessible by all threads, functions that use them are clearly not thread safe.</span></span> <span data-ttu-id="bdcde-140">一个线程上函数实例无法值更改时另一个线程上的另一个实例假定它为完全不同。</span><span class="sxs-lookup"><span data-stu-id="bdcde-140">One instance of the function on one thread could be changing the value while another instance on another thread is assuming it is something completely different.</span></span> 
  
<span data-ttu-id="bdcde-141">有两个声明函数中的静态变量原因：</span><span class="sxs-lookup"><span data-stu-id="bdcde-141">There are two reasons for declaring static variables within a function:</span></span>
  
1. <span data-ttu-id="bdcde-142">静态数据保留从到下一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="bdcde-142">Static data persist from one call to the next.</span></span>
    
2. <span data-ttu-id="bdcde-143">安全地可以由函数返回对静态数据的指针。</span><span class="sxs-lookup"><span data-stu-id="bdcde-143">A pointer to static data can safely be returned by the function.</span></span>
    
<span data-ttu-id="bdcde-144">对于第一个原因，您可能希望具有仍然存在，并且有意义的函数的所有呼叫的数据： 或许就会增加每次上任何线程，调用该函数的简单的计数器或收集前夕的使用情况和性能数据结构ry 呼叫。</span><span class="sxs-lookup"><span data-stu-id="bdcde-144">In the case of first reason, you might want to have data that persists and has meaning for all calls to the function: perhaps a simple counter that is incremented every time the function is called on any thread, or a structure that collects usage and performance data on every call.</span></span> <span data-ttu-id="bdcde-145">此问题是如何保护数据结构的共享的数据。</span><span class="sxs-lookup"><span data-stu-id="bdcde-145">The question is how to protect the shared data or data structure.</span></span> <span data-ttu-id="bdcde-146">最佳这是下一节介绍使用关键部分。</span><span class="sxs-lookup"><span data-stu-id="bdcde-146">This is best done by using critical section as the next section explains.</span></span>
  
<span data-ttu-id="bdcde-147">如果数据旨在通过此线程，其原因 1 的情况，始终是原因 2 这种情况，仅用于问题是如何创建仍然存在但才可以访问从此线程的内存。</span><span class="sxs-lookup"><span data-stu-id="bdcde-147">If the data is intended only for use by this thread, which could be the case for reason 1 and is always the case for reason 2, the question is how to create memory that persists but is only accessible from this thread.</span></span> <span data-ttu-id="bdcde-148">一个解决方案是使用的线程本地存储区 (TLS) API。</span><span class="sxs-lookup"><span data-stu-id="bdcde-148">One solution is to use the thread-local storage (TLS) API.</span></span>
  
<span data-ttu-id="bdcde-149">例如，请考虑将指针返回到**XLOPER**函数。</span><span class="sxs-lookup"><span data-stu-id="bdcde-149">For example, consider a function that returns a pointer to an **XLOPER**.</span></span>
  
```cs
LPXLOPER12 WINAPI mtr_unsafe_example(LPXLOPER12 pxArg)
{
    static XLOPER12 xRetVal; // memory shared by all threads!!!
// code sets xRetVal to a function of pxArg ...
    return &xRetVal;
}
```

<span data-ttu-id="bdcde-150">此函数不是线程安全，因为一个线程可以返回静态**XLOPER12** ，而另一个覆盖它。</span><span class="sxs-lookup"><span data-stu-id="bdcde-150">This function is not thread safe because one thread can return the static **XLOPER12** while another is overwriting it.</span></span> <span data-ttu-id="bdcde-151">更高版本仍然如果**XLOPER12**需要传递给**xlAutoFree12**出现这种情况的可能性。</span><span class="sxs-lookup"><span data-stu-id="bdcde-151">The likelihood of this happening is greater still if the **XLOPER12** needs to be passed to **xlAutoFree12**.</span></span> <span data-ttu-id="bdcde-152">一种解决方案是分配**XLOPER12**、，返回一个指针和实现**xlAutoFree12** ，以便释放**XLOPER12**内存本身。</span><span class="sxs-lookup"><span data-stu-id="bdcde-152">One solution is to allocate an **XLOPER12**, return a pointer to it, and implement **xlAutoFree12** so that the **XLOPER12** memory itself is freed.</span></span> <span data-ttu-id="bdcde-153">在[Excel 中进行内存管理](memory-management-in-excel.md)中所示的示例功能的许多情况下使用此方法。</span><span class="sxs-lookup"><span data-stu-id="bdcde-153">This approach is used in many of the example functions shown in [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
```cs
LPXLOPER12 WINAPI mtr_safe_example_1(LPXLOPER12 pxArg)
{
// pxRetVal must be freed later by xlAutoFree12
    LPXLOPER12 pxRetVal = new XLOPER12;
// code sets pxRetVal to a function of pxArg ...
    pxRetVal->xltype |= xlbitDLLFree; // Needed for all types
    return pxRetVal; // xlAutoFree12 must free this
}
```

<span data-ttu-id="bdcde-154">简单比依赖 TLS API，下一节所述的方法实现此方法，但它有一些缺点。</span><span class="sxs-lookup"><span data-stu-id="bdcde-154">This approach is simpler to implement than the approach outlined in the next section, which relies on the TLS API, but it has some disadvantages.</span></span> <span data-ttu-id="bdcde-155">首先，Excel 必须调用**xlAutoFree**/ **xlAutoFree12**任何类型的返回**XLOPER**/ **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="bdcde-155">First, Excel must call **xlAutoFree**/ **xlAutoFree12** whatever the type of the returned **XLOPER**/ **XLOPER12**.</span></span> <span data-ttu-id="bdcde-156">其次，没有问题时返回**XLOPER**/ **XLOPER12**s 的调用的 C API 回调函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="bdcde-156">Second, there is a problem when returning **XLOPER**/ **XLOPER12**s that are the return value of a call to a C API callback function.</span></span> <span data-ttu-id="bdcde-157">**XLOPER**/ **XLOPER12**可能会导致内存需要释放的 Excel，但**XLOPER**/ **XLOPER12**本身，必须释放被分配方式相同。</span><span class="sxs-lookup"><span data-stu-id="bdcde-157">The **XLOPER**/ **XLOPER12** may point to memory that needs to be freed by Excel, but the **XLOPER**/ **XLOPER12** itself must be freed in the same way it was allocated.</span></span> <span data-ttu-id="bdcde-158">如果此类**XLOPER**/ **XLOPER12**是要用作 XLL 工作表函数的返回值，没有简单方法，告知**xlAutoFree**/ **xlAutoFree12**的需要两个指针忙以相应的方式。</span><span class="sxs-lookup"><span data-stu-id="bdcde-158">If such an **XLOPER**/ **XLOPER12** is to be used as the return value of an XLL worksheet function, there is no easy way to inform **xlAutoFree**/ **xlAutoFree12** of the need to free both pointers in the appropriate way.</span></span> <span data-ttu-id="bdcde-159">（设置**xlbitXLFree**和**xlbitDLLFree**未解决此问题，请在两个设置**XLOPER/XLOPER12s**在 Excel 中的处理未和可能更改版本之间的差异。）若要解决此问题，XLL 可以进行深入的所有 Excel 分配**XLOPER/XLOPER12s**它返回到工作表的副本。</span><span class="sxs-lookup"><span data-stu-id="bdcde-159">(Setting both the **xlbitXLFree** and **xlbitDLLFree** does not solve the problem, as the treatment of **XLOPER/XLOPER12s** in Excel with both set is undefined and might change from version to version.) To work around this problem, the XLL can make deep copies of all Excel-allocated **XLOPER/XLOPER12s** that it returns to the worksheet.</span></span> 
  
<span data-ttu-id="bdcde-160">避免了这些限制的解决方案是填充并返回线程本地**XLOPER/XLOPER12**，需要**xlAutoFree/xlAutoFree12**该方法不会释放**XLOPER/XLOPER12**指针本身。</span><span class="sxs-lookup"><span data-stu-id="bdcde-160">A solution that avoids these limitations is to populate and return a thread-local **XLOPER/XLOPER12**, an approach that necessitates that **xlAutoFree/xlAutoFree12** does not free the **XLOPER/XLOPER12** pointer itself.</span></span> 
  
```cs
LPXLOPER12 get_thread_local_xloper12(void);
LPXLOPER12 WINAPI mtr_safe_example_2(LPXLOPER12 pxArg)
{
    LPXLOPER12 pxRetVal = get_thread_local_xloper12();
// Code sets pxRetVal to a function of pxArg setting xlbitDLLFree or
// xlbitXLFree as required.
    return pxRetVal; // xlAutoFree12 must not free this pointer!
}

```

<span data-ttu-id="bdcde-161">下一个问题是如何设置和检索的线程本地内存，换句话说，如何实现函数**get_thread_local_xloper12**在上面的示例。</span><span class="sxs-lookup"><span data-stu-id="bdcde-161">The next question is how to set up and retrieve the thread-local memory, in other words, how to implement the function **get_thread_local_xloper12** in the previous example.</span></span> <span data-ttu-id="bdcde-162">这是使用线程本地存储 (TLS) API。</span><span class="sxs-lookup"><span data-stu-id="bdcde-162">This is done using the Thread Local Storage (TLS) API.</span></span> <span data-ttu-id="bdcde-163">第一步是使用**TlsAlloc**，最终必须通过使用**TlsFree**释放其获取 TLS 索引。</span><span class="sxs-lookup"><span data-stu-id="bdcde-163">The first step is to obtain a TLS index by using **TlsAlloc**, which must ultimately be released using **TlsFree**.</span></span> <span data-ttu-id="bdcde-164">这两最佳完成从**DllMain**。</span><span class="sxs-lookup"><span data-stu-id="bdcde-164">Both are best accomplished from **DllMain**.</span></span>
  
```cs
// This implementation just calls a function to set up
// thread-local storage.
BOOL TLS_Action(DWORD Reason); // Could be in another module
BOOL WINAPI DllMain(HINSTANCE hDll, DWORD Reason, void *Reserved)
{
    return TLS_Action(Reason);
}
DWORD TlsIndex; // Module scope only if all TLS access in this module
BOOL TLS_Action(DWORD DllMainCallReason)
{
    switch (DllMainCallReason)
    {
    case DLL_PROCESS_ATTACH: // The DLL is being loaded.
        if((TlsIndex = TlsAlloc()) == TLS_OUT_OF_INDEXES)
            return FALSE;
        break;
    case DLL_PROCESS_DETACH: // The DLL is being unloaded.
        TlsFree(TlsIndex); // Release the TLS index.
        break;
    }
    return TRUE;
}
```

<span data-ttu-id="bdcde-165">获取索引后下, 一步是内存的为每个线程分配块。</span><span class="sxs-lookup"><span data-stu-id="bdcde-165">After you obtain the index, the next step is to allocate a block of memory for each thread.</span></span> <span data-ttu-id="bdcde-166">[Windows 开发文档](http://msdn.microsoft.com/en-us/library/ms682583%28VS.85%29.aspx)建议这样做，每次**DllMain**回调函数调用与**DLL_THREAD_ATTACH**事件，以及在每个**DLL_THREAD_DETACH**内存。</span><span class="sxs-lookup"><span data-stu-id="bdcde-166">The [Windows Development Documentation](http://msdn.microsoft.com/en-us/library/ms682583%28VS.85%29.aspx) recommends doing this every time the **DllMain** callback function is called with a **DLL_THREAD_ATTACH** event, and freeing the memory on every **DLL_THREAD_DETACH**.</span></span> <span data-ttu-id="bdcde-167">但是，关注此建议将导致 DLL 执行不必要的工作线程在不用于重新计算。</span><span class="sxs-lookup"><span data-stu-id="bdcde-167">However, following this advice would cause your DLL to do unnecessary work for threads not used for recalculation.</span></span> 
  
<span data-ttu-id="bdcde-168">相反，则最好使用分配上第一个使用策略。</span><span class="sxs-lookup"><span data-stu-id="bdcde-168">Instead, it is better to use an allocate-on-first-use strategy.</span></span> <span data-ttu-id="bdcde-169">首先，您需要定义要为每个线程分配结构。</span><span class="sxs-lookup"><span data-stu-id="bdcde-169">First, you need to define a structure that you want to allocate for each thread.</span></span> <span data-ttu-id="bdcde-170">返回**XLOPERs**或**XLOPER12s**的上一个示例，以下足够了，但您可以创建任何结构符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="bdcde-170">For the previous examples that return **XLOPERs** or **XLOPER12s**, the following suffices, but you can create any structure that satisfies your needs.</span></span>
  
```cs
struct TLS_data
{
    XLOPER xloper_shared_ret_val;
    XLOPER12 xloper12_shared_ret_val;
// Add other required thread-local data here...
};
```

<span data-ttu-id="bdcde-171">下面的函数获取一个指针指向线程本地实例，或如果这是首次调用分配一个。</span><span class="sxs-lookup"><span data-stu-id="bdcde-171">The following function gets a pointer to the thread-local instance, or allocates one if this is the first call.</span></span>
  
```cs
TLS_data *get_TLS_data(void)
{
// Get a pointer to this thread's static memory.
    void *pTLS = TlsGetValue(TlsIndex);
    if(!pTLS) // No TLS memory for this thread yet
    {
        if((pTLS = calloc(1, sizeof(TLS_data))) == NULL)
        // Display some error message (omitted).
            return NULL;
        TlsSetValue(TlsIndex, pTLS); // Associate with this thread
    }
    return (TLS_data *)pTLS;
}
```

<span data-ttu-id="bdcde-172">现在您可以查看如何获取线程本地**XLOPER/XLOPER12**内存： 首先，指针进入**TLS_data**的线程的实例，然后将您返回到**XLOPER/XLOPER12** ，如下所示，其中包含一个指针。</span><span class="sxs-lookup"><span data-stu-id="bdcde-172">Now you can see how the thread-local **XLOPER/XLOPER12** memory is obtained: first, you get a pointer to the thread's instance of **TLS_data**, and then you return a pointer to the **XLOPER/XLOPER12** contained within it, as follows.</span></span> 
  
```cs
LPXLOPER get_thread_local_xloper(void)
{
    TLS_data *pTLS = get_TLS_data();
    if(pTLS)
        return &(pTLS->xloper_shared_ret_val);
    return NULL;
}
LPXLOPER12 get_thread_local_xloper12(void)
{
    TLS_data *pTLS = get_TLS_data();
    if(pTLS)
        return &(pTLS->xloper12_shared_ret_val);
    return NULL;
}

```

<span data-ttu-id="bdcde-173">运行 Excel 时，可以将**mtr_safe_example_1**和**mtr_safe_example_2**函数注册为线程安全工作表函数。</span><span class="sxs-lookup"><span data-stu-id="bdcde-173">The **mtr_safe_example_1** and **mtr_safe_example_2** functions can be registered as thread-safe worksheet functions when you are running Excel.</span></span> <span data-ttu-id="bdcde-174">但是，不能混合一个 XLL 中的两种方法。</span><span class="sxs-lookup"><span data-stu-id="bdcde-174">However, you cannot mix the two approaches in one XLL.</span></span> <span data-ttu-id="bdcde-175">您 XLL 只能导出一个实现**xlAutoFree**和**xlAutoFree12**，并且每个内存策略需要不同的方法。</span><span class="sxs-lookup"><span data-stu-id="bdcde-175">Your XLL can only export one implementation of **xlAutoFree** and **xlAutoFree12**, and each memory strategy requires a different approach.</span></span> <span data-ttu-id="bdcde-176">与**mtr_safe_example_1**，以及它指向的任何数据，必须释放传递给**xlAutoFree/xlAutoFree12**的指针。</span><span class="sxs-lookup"><span data-stu-id="bdcde-176">With **mtr_safe_example_1**, the pointer passed to **xlAutoFree/xlAutoFree12** must be freed along with any data it points to.</span></span> <span data-ttu-id="bdcde-177">与**mtr_safe_example_2**，应释放仅指向的数据。</span><span class="sxs-lookup"><span data-stu-id="bdcde-177">With **mtr_safe_example_2**, only the pointed-to data should be freed.</span></span>
  
<span data-ttu-id="bdcde-178">Windows 还提供了一个函数**GetCurrentThreadId**，它返回当前线程的唯一系统范围 id。</span><span class="sxs-lookup"><span data-stu-id="bdcde-178">Windows also provides a function **GetCurrentThreadId**, which returns the current thread's unique system-wide ID.</span></span> <span data-ttu-id="bdcde-179">这将为开发人员提供使代码线程安全的或者使其行为线程特定的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="bdcde-179">This provides the developer with another way to make code thread safe, or to make its behavior thread specific.</span></span>
  
## <a name="memory-accessible-only-by-more-than-one-thread-critical-sections"></a><span data-ttu-id="bdcde-180">只能由多个线程可访问的内存： 关键节</span><span class="sxs-lookup"><span data-stu-id="bdcde-180">Memory Accessible Only by More than One Thread: Critical Sections</span></span>

<span data-ttu-id="bdcde-181">您应该保护可以通过使用关键节的多个线程的读/写内存。</span><span class="sxs-lookup"><span data-stu-id="bdcde-181">You should protect read/write memory that can be accessed by more than one thread using critical sections.</span></span> <span data-ttu-id="bdcde-182">对于每个要保护的内存块中需要命名的关键部分。</span><span class="sxs-lookup"><span data-stu-id="bdcde-182">You need a named critical section for each block of memory you want to protect.</span></span> <span data-ttu-id="bdcde-183">您可以初始化在**xlAutoOpen**函数中，调用过程和释放其期间对**xlAutoClose**函数的调用将它们设置为 null。</span><span class="sxs-lookup"><span data-stu-id="bdcde-183">You can initialize these during the call to the **xlAutoOpen** function, and release them and set them to null during the call to the **xlAutoClose** function.</span></span> <span data-ttu-id="bdcde-184">然后，您需要包含对受保护的块内调用**EnterCriticalSection**和**LeaveCriticalSection**的一对每个访问。</span><span class="sxs-lookup"><span data-stu-id="bdcde-184">You then need to contain each access to the protected block within a pair of calls to **EnterCriticalSection** and **LeaveCriticalSection**.</span></span> <span data-ttu-id="bdcde-185">只有一个线程允许到关键部分中，在任何时间。</span><span class="sxs-lookup"><span data-stu-id="bdcde-185">Only one thread is permitted into the critical section at any time.</span></span> <span data-ttu-id="bdcde-186">下面是部分的初始化、 非初始化，并使用调用**g_csSharedTable**的一个示例。</span><span class="sxs-lookup"><span data-stu-id="bdcde-186">Here is an example of the initialization, uninitialization, and use of a section called **g_csSharedTable**.</span></span>
  
```cs
CRITICAL_SECTION g_csSharedTable; // global scope (if required)
bool xll_initialised = false; // Only module scope needed
int WINAPI xlAutoOpen(void)
{
    if(xll_initialised)
        return 1;
// Other initialisation omitted
    InitializeCriticalSection(&g_csSharedTable);
    xll_initialised = true;
    return 1;
}
int WINAPI xlAutoClose(void)
{
    if(!xll_initialised)
        return 1;
// Other cleaning up omitted.
    DeleteCriticalSection(&g_csSharedTable);
    xll_initialised = false;
    return 1;
}
#define SHARED_TABLE_SIZE 1000 /* Some value consistent with the table */
bool read_shared_table_element(unsigned int index, double &d)
{
    if(index >= SHARED_TABLE_SIZE) return false;
    EnterCriticalSection(&g_csSharedTable);
    d = shared_table[index];
    LeaveCriticalSection(&g_csSharedTable);
    return true;
}
bool set_shared_table_element(unsigned int index, double d)
{
    if(index >= SHARED_TABLE_SIZE) return false;
    EnterCriticalSection(&g_csSharedTable);
    shared_table[index] = d;
    LeaveCriticalSection(&g_csSharedTable);
    return true;
}
```

<span data-ttu-id="bdcde-187">保护内存块的另一个、 也许更安全的方式是创建一个类，其中包含自己**CRITICAL_SECTION**其构造函数、 析构函数，并使用解决访问器方法。</span><span class="sxs-lookup"><span data-stu-id="bdcde-187">Another, perhaps safer way of protecting a block of memory is to create a class that contains its own **CRITICAL_SECTION** and whose constructor, destructor, and accessor methods take care of its use.</span></span> <span data-ttu-id="bdcde-188">此方法的优点添加了保护之前**xlAutoOpen**运行或排除后调用**xlAutoClose**时，可能初始化的对象，但您应注意有关创建太多的关键部分和操作系统这将创建的开销。</span><span class="sxs-lookup"><span data-stu-id="bdcde-188">This approach has the added advantage of protecting objects that may be initialized before **xlAutoOpen** is run, or survive after **xlAutoClose** is called, but you should be careful about creating too many critical sections and the operating system overhead that this would create.</span></span> 
  
<span data-ttu-id="bdcde-189">同时需要访问受保护的内存的多个块的代码后，您需要非常仔细考虑的关键部分进行输入和退出的顺序。</span><span class="sxs-lookup"><span data-stu-id="bdcde-189">When you have code that needs access to more than one block of protected memory at the same time, you need to consider very carefully the order in which the critical sections are entered and exited.</span></span> <span data-ttu-id="bdcde-190">例如，以下两个功能还可以创建死锁。</span><span class="sxs-lookup"><span data-stu-id="bdcde-190">For example, the following two functions could create a deadlock.</span></span>
  
```cs
// WARNING: Do not copy this code. These two functions
// can produce a deadlock and are provided for
// example and illustration only.
bool copy_shared_table_element_A_to_B(unsigned int index)
{
    if(index >= SHARED_TABLE_SIZE) return false;
    EnterCriticalSection(&g_csSharedTableA);
    EnterCriticalSection(&g_csSharedTableB);
    shared_table_B[index] = shared_table_A[index];
// Critical sections should be exited in the order
// they were entered, NOT as shown here in this
// deliberately wrong illustration.
    LeaveCriticalSection(&g_csSharedTableA);
    LeaveCriticalSection(&g_csSharedTableB);
    return true;
}
bool copy_shared_table_element_B_to_A(unsigned int index)
{
    if(index >= SHARED_TABLE_SIZE) return false;
    EnterCriticalSection(&g_csSharedTableB);
    EnterCriticalSection(&g_csSharedTableA);
    shared_table_A[index] = shared_table_B[index];
    LeaveCriticalSection(&g_csSharedTableA);
    LeaveCriticalSection(&g_csSharedTableB);
    return true;
}
```

<span data-ttu-id="bdcde-191">如果一个线程上的第一个函数输入**g_csSharedTableA**当另一个线程上的第二个进入**g_csSharedTableB**时，这两个线程挂起。</span><span class="sxs-lookup"><span data-stu-id="bdcde-191">If the first function on one thread enters **g_csSharedTableA** while the second on another thread enters **g_csSharedTableB**, both threads hang.</span></span> <span data-ttu-id="bdcde-192">正确的方法是一致的顺序进入和退出的相反顺序，如下所示。</span><span class="sxs-lookup"><span data-stu-id="bdcde-192">The correct approach is to enter in a consistent order and exit in the reverse order, as follows.</span></span>
  
```cs
    EnterCriticalSection(&g_csSharedTableA);
    EnterCriticalSection(&g_csSharedTableB);
    // code that accesses both blocks
    LeaveCriticalSection(&g_csSharedTableB);
    LeaveCriticalSection(&g_csSharedTableA);
```

<span data-ttu-id="bdcde-193">在可能的情况下，最好是从线程共同操作角度隔离访问不同块，如下所示。</span><span class="sxs-lookup"><span data-stu-id="bdcde-193">Where possible, it is better from a thread co-operation point of view to isolate access to distinct blocks, as shown here.</span></span>
  
```cs
bool copy_shared_table_element_A_to_B(unsigned int index)
{
    if(index >= SHARED_TABLE_SIZE) return false;
    EnterCriticalSection(&g_csSharedTableA);
    double d = shared_table_A[index];
    LeaveCriticalSection(&g_csSharedTableA);
    EnterCriticalSection(&g_csSharedTableB);
    shared_table_B[index] = d;
    LeaveCriticalSection(&g_csSharedTableB);
    return true;
}
```

<span data-ttu-id="bdcde-194">其中没有大量争用共享资源，如常用 short 持续时间访问请求，您应考虑使用关键部分中的功能旋转。</span><span class="sxs-lookup"><span data-stu-id="bdcde-194">Where there is a lot of contention for a shared resource, such as frequent short-duration access requests, you should consider using the critical section's ability to spin.</span></span> <span data-ttu-id="bdcde-195">这是一种使较少的处理器密集型等待资源的技术。</span><span class="sxs-lookup"><span data-stu-id="bdcde-195">This is a technique that makes waiting for the resource less processor-intensive.</span></span> <span data-ttu-id="bdcde-196">若要执行此操作，您可以使用任一**InitializeCriticalSectionAndSpinCount**初始化节或**SetCriticalSectionSpinCount**一旦初始化，若要设置的次数之前等待资源成为循环线程时可用。</span><span class="sxs-lookup"><span data-stu-id="bdcde-196">To do this, you can use either **InitializeCriticalSectionAndSpinCount** when initializing the section or **SetCriticalSectionSpinCount** once initialized, to set the number of times the thread loops before waiting for resources to become available.</span></span> <span data-ttu-id="bdcde-197">等待操作很高，，因此旋转可避免这，如果同时会释放资源。</span><span class="sxs-lookup"><span data-stu-id="bdcde-197">The wait operation is expensive, so spinning avoids this if the resource is freed in the meantime.</span></span> <span data-ttu-id="bdcde-198">在单个处理器系统上，实际上会忽略调节计数，但不进行任何损害，仍可以所指定。</span><span class="sxs-lookup"><span data-stu-id="bdcde-198">On a single processor system, the spin count is effectively ignored, but you can still specify it without doing any harm.</span></span> <span data-ttu-id="bdcde-199">内存堆管理器使用 4000 调节计数。</span><span class="sxs-lookup"><span data-stu-id="bdcde-199">The memory heap manager uses a spin count of 4000.</span></span> <span data-ttu-id="bdcde-200">有关如何使用的关键部分的详细信息，请参阅 Windows SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="bdcde-200">For more information about the use of critical sections, see the Windows SDK documentation.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bdcde-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdcde-201">See also</span></span>



[<span data-ttu-id="bdcde-202">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="bdcde-202">Memory Management in Excel</span></span>](memory-management-in-excel.md)
  
[<span data-ttu-id="bdcde-203">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="bdcde-203">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="bdcde-204">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="bdcde-204">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

