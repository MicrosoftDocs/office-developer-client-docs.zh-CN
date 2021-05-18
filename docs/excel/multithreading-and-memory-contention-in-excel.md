---
title: 线程中的多线程和内存Excel
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- excel 中的多线程处理，Excel 中的内存争用，函数 [Excel 2007]，线程安全，线程安全函数 [Excel 2007]，线程本地内存 [Excel 2007]
localization_priority: Normal
ms.assetid: 86e1e842-f433-4ea9-8b13-ad2515fc50d8
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a385728450fc6519d7f5211c186a9d74e623bf7b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301636"
---
# <a name="multithreading-and-memory-contention-in-excel"></a><span data-ttu-id="88e17-104">线程中的多线程和内存Excel</span><span class="sxs-lookup"><span data-stu-id="88e17-104">Multithreading and Memory Contention in Excel</span></span>

 <span data-ttu-id="88e17-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="88e17-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="88e17-106">2007 Microsoft Excel 2007 Excel版本将单个线程用于所有工作表计算。</span><span class="sxs-lookup"><span data-stu-id="88e17-106">Versions of Microsoft Excel earlier than Excel 2007 use a single thread for all worksheet calculations.</span></span> <span data-ttu-id="88e17-107">但是，从 2007 Excel，Excel配置为使用 1 到 1024 个并发线程进行工作表计算。</span><span class="sxs-lookup"><span data-stu-id="88e17-107">However, starting in Excel 2007, Excel can be configured to use from 1 to 1024 concurrent threads for worksheet calculation.</span></span> <span data-ttu-id="88e17-108">在多处理器或多核计算机上，线程的默认数量等于处理器或内核数。</span><span class="sxs-lookup"><span data-stu-id="88e17-108">On a multi-processor or multi-core computer, the default number of threads is equal to the number of processors or cores.</span></span> <span data-ttu-id="88e17-109">因此，线程安全单元格或仅包含线程安全函数的单元格可被分配至并发线程，但需按照需要在引用单元格之后计算的通常重新计算逻辑。</span><span class="sxs-lookup"><span data-stu-id="88e17-109">Therefore, thread-safe cells, or cells that only contain functions that are thread safe, can be allotted to concurrent threads, subject to the usual recalculation logic of needing to be calculated after their precedents.</span></span>
  
## <a name="thread-safe-functions"></a><span data-ttu-id="88e17-110">Thread-Safe 函数</span><span class="sxs-lookup"><span data-stu-id="88e17-110">Thread-Safe Functions</span></span>

<span data-ttu-id="88e17-111">从 2007 年 2 Excel，大多数内置工作表函数都是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="88e17-111">Most of the built-in worksheet functions starting in Excel 2007 are thread safe.</span></span> <span data-ttu-id="88e17-112">还可以编写 XLL 函数并注册为线程安全函数。</span><span class="sxs-lookup"><span data-stu-id="88e17-112">You can also write and register XLL functions as being thread safe.</span></span> <span data-ttu-id="88e17-113">Excel使用一个线程 (其主线程) 来调用所有命令、非线程安全函数 **、xlAuto** 函数 [ (（xlAutoFree](xlautofree-xlautofree12.md)和 **xlAutoFree12**) 除外）以及 COM 和 Visual Basic for Applications (VBA) 函数。</span><span class="sxs-lookup"><span data-stu-id="88e17-113">Excel uses one thread (its main thread) to call all commands, thread-unsafe functions, **xlAuto** functions (except [xlAutoFree](xlautofree-xlautofree12.md) and **xlAutoFree12**), and COM and Visual Basic for Applications (VBA) functions.</span></span>
  
<span data-ttu-id="88e17-114">当 XLL 函数返回设置了 **xlbitDLLFree** 的 **XLOPER** 或 **XLOPER12** 时，Excel 将使用函数调用所基于的同一线程调用 **xlAutoFree** 或 **xlAutoFree12。**</span><span class="sxs-lookup"><span data-stu-id="88e17-114">Where an XLL function returns an **XLOPER** or **XLOPER12** with **xlbitDLLFree** set, Excel uses the same thread on which the function call was made to call **xlAutoFree** or **xlAutoFree12**.</span></span> <span data-ttu-id="88e17-115">在线程上的下一个函数调用之前，调用 **xlAutoFree** 或 **xlAutoFree12。**</span><span class="sxs-lookup"><span data-stu-id="88e17-115">The call to **xlAutoFree** or **xlAutoFree12** is made before the next function call on that thread.</span></span> 
  
<span data-ttu-id="88e17-116">对于 XLL 开发人员，创建线程安全函数有一些好处：</span><span class="sxs-lookup"><span data-stu-id="88e17-116">For XLL developers, there are benefits for creating thread-safe functions:</span></span>
  
- <span data-ttu-id="88e17-117">它们Excel充分利用多处理器或多核计算机。</span><span class="sxs-lookup"><span data-stu-id="88e17-117">They allow Excel to make the most of a multi-processor or multi-core computer.</span></span>
    
- <span data-ttu-id="88e17-118">它们比使用单个线程可以更高效地使用远程服务器的可能性大很多。</span><span class="sxs-lookup"><span data-stu-id="88e17-118">They open up the possibility of using remote servers much more efficiently than can be done using a single thread.</span></span>
    
<span data-ttu-id="88e17-119">假设您有一台已配置为使用（例如  *，N*  个线程）的单处理器计算机。</span><span class="sxs-lookup"><span data-stu-id="88e17-119">Suppose that you have a single-processor computer that has been configured to use, say,  *N*  threads.</span></span> <span data-ttu-id="88e17-120">假定电子表格正在运行，该电子表格对 XLL 函数进行大量调用，而 XLL 函数又向远程服务器或服务器群集发送数据请求或计算请求。</span><span class="sxs-lookup"><span data-stu-id="88e17-120">Suppose that a spreadsheet is running that makes a large number of calls to an XLL function that in turn sends a request for data or for a calculation to be performed to a remote server or cluster of servers.</span></span> <span data-ttu-id="88e17-121">根据依赖关系树的拓扑，Excel几乎同时调用函数 N 次。</span><span class="sxs-lookup"><span data-stu-id="88e17-121">Subject to the topology of the dependency tree, Excel could call the function N times almost simultaneously.</span></span> <span data-ttu-id="88e17-122">如果一个或多个服务器速度足够快或并行，电子表格的重新计算时间可以缩短 1/N 的一个因子。</span><span class="sxs-lookup"><span data-stu-id="88e17-122">Provided that the server or servers are sufficiently fast or parallel, the recalculation time of the spreadsheet could be reduced by as much as a factor of 1/N.</span></span> 
  
<span data-ttu-id="88e17-123">编写线程安全函数的关键问题是正确处理资源的争用。</span><span class="sxs-lookup"><span data-stu-id="88e17-123">The key issue in writing thread-safe functions is handling contention for resources correctly.</span></span> <span data-ttu-id="88e17-124">这通常意味着内存争用，它可以分为两个问题：</span><span class="sxs-lookup"><span data-stu-id="88e17-124">This usually means memory contention, and it can be broken down into two issues:</span></span>
  
- <span data-ttu-id="88e17-125">如何创建你知道仅此线程使用的内存。</span><span class="sxs-lookup"><span data-stu-id="88e17-125">How to create memory that you know will only be used by this thread.</span></span>
    
- <span data-ttu-id="88e17-126">如何确保多个线程安全地访问共享内存。</span><span class="sxs-lookup"><span data-stu-id="88e17-126">How to ensure that shared memory is accessed by multiple threads safely.</span></span>
    
<span data-ttu-id="88e17-127">首先要注意的一点就是 XLL 中的哪些内存可供所有线程访问，以及当前执行的线程只能访问哪些内存。</span><span class="sxs-lookup"><span data-stu-id="88e17-127">The first thing to be aware of is what memory in an XLL is accessible by all threads, and what is only accessible by the currently executing thread.</span></span>
  
 <span data-ttu-id="88e17-128">**所有线程均可访问**</span><span class="sxs-lookup"><span data-stu-id="88e17-128">**Accessible by all threads**</span></span>
  
- <span data-ttu-id="88e17-129">在函数正文之外声明的变量、结构和类实例。</span><span class="sxs-lookup"><span data-stu-id="88e17-129">Variables, structures, and class instances declared outside the body of a function.</span></span>
    
- <span data-ttu-id="88e17-130">在函数的正文中声明的静态变量。</span><span class="sxs-lookup"><span data-stu-id="88e17-130">Static variables declared within the body of a function.</span></span>
    
<span data-ttu-id="88e17-131">在这两种情况下，内存将留出在为此 DLL 实例创建的 DLL 的内存块中。</span><span class="sxs-lookup"><span data-stu-id="88e17-131">In these two cases, memory is set aside in the DLL's memory block created for this instance of the DLL.</span></span> <span data-ttu-id="88e17-132">如果另一个应用程序实例加载 DLL，它将获取该内存的其自己的副本，以便不从 DLL 的此实例之外争用这些资源。</span><span class="sxs-lookup"><span data-stu-id="88e17-132">If another application instance loads the DLL, it gets its own copy of that memory so that there is no contention for these resources from outside this instance of the DLL.</span></span>
  
 <span data-ttu-id="88e17-133">**仅当前线程可访问**</span><span class="sxs-lookup"><span data-stu-id="88e17-133">**Accessible only by the current thread**</span></span>
  
- <span data-ttu-id="88e17-134">函数代码中的自动变量 (包括函数参数) 。</span><span class="sxs-lookup"><span data-stu-id="88e17-134">Automatic variables within function code (including function arguments).</span></span>
    
<span data-ttu-id="88e17-135">在这种情况下，会为函数调用的每个实例在堆栈上留出内存。</span><span class="sxs-lookup"><span data-stu-id="88e17-135">In this case, memory is set aside on the stack for each instance of the function call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88e17-136">动态分配的内存作用域取决于指向它的指针范围：如果指针可由所有线程访问，则内存也是。</span><span class="sxs-lookup"><span data-stu-id="88e17-136">The scope of dynamically allocated memory depends on the scope of the pointer that points to it: if the pointer is accessible by all threads, the memory is also.</span></span> <span data-ttu-id="88e17-137">如果指针是函数中的自动变量，则分配的内存实际上对于该线程是私有的。</span><span class="sxs-lookup"><span data-stu-id="88e17-137">If the pointer is an automatic variable in a function, the allocated memory is effectively private to that thread.</span></span> 
  
## <a name="memory-accessible-by-only-one-thread-thread-local-memory"></a><span data-ttu-id="88e17-138">仅一个线程可访问的内存：Thread-Local内存</span><span class="sxs-lookup"><span data-stu-id="88e17-138">Memory Accessible by Only One Thread: Thread-Local Memory</span></span>

<span data-ttu-id="88e17-139">鉴于所有线程均可访问函数正文中的静态变量，使用它们的函数明显不是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="88e17-139">Given that static variables within the body of a function are accessible by all threads, functions that use them are clearly not thread safe.</span></span> <span data-ttu-id="88e17-140">一个线程上的函数的一个实例可能会更改值，而另一个线程上的另一个实例假定该值完全不同。</span><span class="sxs-lookup"><span data-stu-id="88e17-140">One instance of the function on one thread could be changing the value while another instance on another thread is assuming it is something completely different.</span></span> 
  
<span data-ttu-id="88e17-141">声明函数中的静态变量有两个原因：</span><span class="sxs-lookup"><span data-stu-id="88e17-141">There are two reasons for declaring static variables within a function:</span></span>
  
1. <span data-ttu-id="88e17-142">静态数据从一个调用持续到下一个调用。</span><span class="sxs-lookup"><span data-stu-id="88e17-142">Static data persist from one call to the next.</span></span>
    
2. <span data-ttu-id="88e17-143">指向静态数据的指针可通过 函数安全地返回。</span><span class="sxs-lookup"><span data-stu-id="88e17-143">A pointer to static data can safely be returned by the function.</span></span>
    
<span data-ttu-id="88e17-144">在出于第一个原因的情况下，你可能希望具有对函数的所有调用具有持久性和含义的数据：可能是每次在任何线程上调用函数时递增的简单计数器，或者是收集每次调用的使用率和性能数据的结构。</span><span class="sxs-lookup"><span data-stu-id="88e17-144">In the case of first reason, you might want to have data that persists and has meaning for all calls to the function: perhaps a simple counter that is incremented every time the function is called on any thread, or a structure that collects usage and performance data on every call.</span></span> <span data-ttu-id="88e17-145">问题是如何保护共享数据或数据结构。</span><span class="sxs-lookup"><span data-stu-id="88e17-145">The question is how to protect the shared data or data structure.</span></span> <span data-ttu-id="88e17-146">如下一节所述，最好使用关键部分完成此操作。</span><span class="sxs-lookup"><span data-stu-id="88e17-146">This is best done by using critical section as the next section explains.</span></span>
  
<span data-ttu-id="88e17-147">如果数据仅供此线程使用（可能是由于原因 1 的情况，并且原因 2 始终如此，则问题是如何创建保留但只能从此线程访问的内存。</span><span class="sxs-lookup"><span data-stu-id="88e17-147">If the data is intended only for use by this thread, which could be the case for reason 1 and is always the case for reason 2, the question is how to create memory that persists but is only accessible from this thread.</span></span> <span data-ttu-id="88e17-148">一个解决方案是使用线程本地存储 (TLS) API。</span><span class="sxs-lookup"><span data-stu-id="88e17-148">One solution is to use the thread-local storage (TLS) API.</span></span>
  
<span data-ttu-id="88e17-149">例如，考虑一个返回指向 **XLOPER 的指针的函数**。</span><span class="sxs-lookup"><span data-stu-id="88e17-149">For example, consider a function that returns a pointer to an **XLOPER**.</span></span>
  
```cs
LPXLOPER12 WINAPI mtr_unsafe_example(LPXLOPER12 pxArg)
{
    static XLOPER12 xRetVal; // memory shared by all threads!!!
// code sets xRetVal to a function of pxArg ...
    return &xRetVal;
}
```

<span data-ttu-id="88e17-150">此函数不是线程安全的，因为一个线程可以返回静态 **XLOPER12，** 而另一个线程会覆盖它。</span><span class="sxs-lookup"><span data-stu-id="88e17-150">This function is not thread safe because one thread can return the static **XLOPER12** while another is overwriting it.</span></span> <span data-ttu-id="88e17-151">如果需要将 **XLOPER12** 传递到 **xlAutoFree12，** 则发生此情况的可能性仍然更大。</span><span class="sxs-lookup"><span data-stu-id="88e17-151">The likelihood of this happening is greater still if the **XLOPER12** needs to be passed to **xlAutoFree12**.</span></span> <span data-ttu-id="88e17-152">一个解决方案是分配 **一个 XLOPER12，** 返回指向它的指针，并实现 **xlAutoFree12，** 以便 **释放 XLOPER12** 内存本身。</span><span class="sxs-lookup"><span data-stu-id="88e17-152">One solution is to allocate an **XLOPER12**, return a pointer to it, and implement **xlAutoFree12** so that the **XLOPER12** memory itself is freed.</span></span> <span data-ttu-id="88e17-153">此方法在 Memory Management in [Excel 中显示的许多示例函数中Excel。](memory-management-in-excel.md)</span><span class="sxs-lookup"><span data-stu-id="88e17-153">This approach is used in many of the example functions shown in [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
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

<span data-ttu-id="88e17-154">此方法的实现比下一节中介绍的方法更简单，该方法依赖于 TLS API，但它有一些缺点。</span><span class="sxs-lookup"><span data-stu-id="88e17-154">This approach is simpler to implement than the approach outlined in the next section, which relies on the TLS API, but it has some disadvantages.</span></span> <span data-ttu-id="88e17-155">首先，Excel必须调用 **xlAutoFree** /  **xlAutoFree12，** 无论返回 **的 XLOPER** /  **XLOPER12 的类型是什么**。</span><span class="sxs-lookup"><span data-stu-id="88e17-155">First, Excel must call **xlAutoFree**/ **xlAutoFree12** whatever the type of the returned **XLOPER**/ **XLOPER12**.</span></span> <span data-ttu-id="88e17-156">其次，返回 /  **XLOPER XLOPER12** 时出现问题，这是对 C API 回调函数的调用的返回值。</span><span class="sxs-lookup"><span data-stu-id="88e17-156">Second, there is a problem when returning **XLOPER**/ **XLOPER12** s that are the return value of a call to a C API callback function.</span></span> <span data-ttu-id="88e17-157">**XLOPER** /  **XLOPER12** 可能指向需要由 Excel 释放的内存，但 **XLOPER** /  **XLOPER12** 本身必须按分配的方式释放。</span><span class="sxs-lookup"><span data-stu-id="88e17-157">The **XLOPER**/ **XLOPER12** may point to memory that needs to be freed by Excel, but the **XLOPER**/ **XLOPER12** itself must be freed in the same way it was allocated.</span></span> <span data-ttu-id="88e17-158">如果将此类 **XLOPER XLOPER12** 用作 XLL 工作表函数的返回值，则没有简单的方法通知 /  **xlAutoFree** /  **xlAutoFree12** 需要以适当的方式释放这两个指针。</span><span class="sxs-lookup"><span data-stu-id="88e17-158">If such an **XLOPER**/ **XLOPER12** is to be used as the return value of an XLL worksheet function, there is no easy way to inform **xlAutoFree**/ **xlAutoFree12** of the need to free both pointers in the appropriate way.</span></span> <span data-ttu-id="88e17-159"> (同时设置 **xlbitXLFree** 和 **xlbitDLLFree** 无法解决问题，因为 Excel 中同时使用这两个集的 **XLOPER/XLOPER12** 的处理未定义，并且可能会随版本更改。) 若要解决此问题，XLL 可以制作它返回到工作表的所有 Excel 分配的 **XLOPER/XLOPER12** 的深层副本。</span><span class="sxs-lookup"><span data-stu-id="88e17-159">(Setting both the **xlbitXLFree** and **xlbitDLLFree** does not solve the problem, as the treatment of **XLOPER/XLOPER12s** in Excel with both set is undefined and might change from version to version.) To work around this problem, the XLL can make deep copies of all Excel-allocated **XLOPER/XLOPER12s** that it returns to the worksheet.</span></span> 
  
<span data-ttu-id="88e17-160">避免这些限制的解决方案是填充和返回线程本地 **XLOPER/XLOPER12，** 该方法需要 **xlAutoFree/xlAutoFree12** 不释放 **XLOPER/XLOPER12** 指针本身。</span><span class="sxs-lookup"><span data-stu-id="88e17-160">A solution that avoids these limitations is to populate and return a thread-local **XLOPER/XLOPER12**, an approach that necessitates that **xlAutoFree/xlAutoFree12** does not free the **XLOPER/XLOPER12** pointer itself.</span></span> 
  
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

<span data-ttu-id="88e17-161">下一个问题是如何设置和检索线程本地内存， **也就是说** ，如何在上一示例中get_thread_local_xloper12函数。</span><span class="sxs-lookup"><span data-stu-id="88e17-161">The next question is how to set up and retrieve the thread-local memory, in other words, how to implement the function **get_thread_local_xloper12** in the previous example.</span></span> <span data-ttu-id="88e17-162">这是通过使用线程本地存储 (TLS) API 完成。</span><span class="sxs-lookup"><span data-stu-id="88e17-162">This is done using the Thread Local Storage (TLS) API.</span></span> <span data-ttu-id="88e17-163">第一步是使用 **TlsAlloc** 获取 TLS 索引，该索引最终必须使用 **TlsFree 发布**。</span><span class="sxs-lookup"><span data-stu-id="88e17-163">The first step is to obtain a TLS index by using **TlsAlloc**, which must ultimately be released using **TlsFree**.</span></span> <span data-ttu-id="88e17-164">两者最好通过 **DllMain 实现**。</span><span class="sxs-lookup"><span data-stu-id="88e17-164">Both are best accomplished from **DllMain**.</span></span>
  
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

<span data-ttu-id="88e17-165">获取索引后，下一步是为每个线程分配内存块。</span><span class="sxs-lookup"><span data-stu-id="88e17-165">After you obtain the index, the next step is to allocate a block of memory for each thread.</span></span> <span data-ttu-id="88e17-166">开发 [Windows文档](https://msdn.microsoft.com/library/ms682583%28VS.85%29.aspx)建议每次使用 **DLL_THREAD_ATTACH** 事件调用 **DllMain** 回调函数时执行此操作，并释放每个 **DLL_THREAD_DETACH。**</span><span class="sxs-lookup"><span data-stu-id="88e17-166">The [Windows Development Documentation](https://msdn.microsoft.com/library/ms682583%28VS.85%29.aspx) recommends doing this every time the **DllMain** callback function is called with a **DLL_THREAD_ATTACH** event, and freeing the memory on every **DLL_THREAD_DETACH**.</span></span> <span data-ttu-id="88e17-167">但是，遵循此建议将导致 DLL 对不用于重新计算的线程执行不必要的工作。</span><span class="sxs-lookup"><span data-stu-id="88e17-167">However, following this advice would cause your DLL to do unnecessary work for threads not used for recalculation.</span></span> 
  
<span data-ttu-id="88e17-168">相反，最好使用"首次使用时分配"策略。</span><span class="sxs-lookup"><span data-stu-id="88e17-168">Instead, it is better to use an allocate-on-first-use strategy.</span></span> <span data-ttu-id="88e17-169">首先，需要定义要为每个线程分配的结构。</span><span class="sxs-lookup"><span data-stu-id="88e17-169">First, you need to define a structure that you want to allocate for each thread.</span></span> <span data-ttu-id="88e17-170">对于返回 **XLOPERs** 或 **XLOPER12s** 的上一个示例，满足以下条件，但您可以创建满足您需求的任何结构。</span><span class="sxs-lookup"><span data-stu-id="88e17-170">For the previous examples that return **XLOPERs** or **XLOPER12s**, the following suffices, but you can create any structure that satisfies your needs.</span></span>
  
```cs
struct TLS_data
{
    XLOPER xloper_shared_ret_val;
    XLOPER12 xloper12_shared_ret_val;
// Add other required thread-local data here...
};
```

<span data-ttu-id="88e17-171">以下函数获取指向线程本地实例的指针，如果这是第一个调用，则分配一个。</span><span class="sxs-lookup"><span data-stu-id="88e17-171">The following function gets a pointer to the thread-local instance, or allocates one if this is the first call.</span></span>
  
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

<span data-ttu-id="88e17-172">现在，你可以看到如何获取线程本地 **XLOPER/XLOPER12** 内存：首先，获取指向 **线程的 TLS_data** 实例的指针，然后返回一个指向其中包含的 **XLOPER/XLOPER12** 的指针，如下所示。</span><span class="sxs-lookup"><span data-stu-id="88e17-172">Now you can see how the thread-local **XLOPER/XLOPER12** memory is obtained: first, you get a pointer to the thread's instance of **TLS_data**, and then you return a pointer to the **XLOPER/XLOPER12** contained within it, as follows.</span></span> 
  
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

<span data-ttu-id="88e17-173">在 **mtr_safe_example_1 mtr_safe_example_2** 时，可以将函数和函数注册为线程安全Excel。</span><span class="sxs-lookup"><span data-stu-id="88e17-173">The **mtr_safe_example_1** and **mtr_safe_example_2** functions can be registered as thread-safe worksheet functions when you are running Excel.</span></span> <span data-ttu-id="88e17-174">但是，您不能在一个 XLL 中混合使用这两种方法。</span><span class="sxs-lookup"><span data-stu-id="88e17-174">However, you cannot mix the two approaches in one XLL.</span></span> <span data-ttu-id="88e17-175">你的 XLL 只能导出 **xlAutoFree** 和 **xlAutoFree12** 的一个实现，并且每个内存策略都需要不同的方法。</span><span class="sxs-lookup"><span data-stu-id="88e17-175">Your XLL can only export one implementation of **xlAutoFree** and **xlAutoFree12**, and each memory strategy requires a different approach.</span></span> <span data-ttu-id="88e17-176">使用 **mtr_safe_example_1** 时，必须释放传递给 **xlAutoFree/xlAutoFree12** 的指针以及它指向的任何数据。</span><span class="sxs-lookup"><span data-stu-id="88e17-176">With **mtr_safe_example_1**, the pointer passed to **xlAutoFree/xlAutoFree12** must be freed along with any data it points to.</span></span> <span data-ttu-id="88e17-177">使用 **mtr_safe_example_2**，应仅释放指向的数据。</span><span class="sxs-lookup"><span data-stu-id="88e17-177">With **mtr_safe_example_2**, only the pointed-to data should be freed.</span></span>
  
<span data-ttu-id="88e17-178">Windows还提供 **GetCurrentThreadId** 函数，该函数返回当前线程的唯一系统范围 ID。</span><span class="sxs-lookup"><span data-stu-id="88e17-178">Windows also provides a function **GetCurrentThreadId**, which returns the current thread's unique system-wide ID.</span></span> <span data-ttu-id="88e17-179">这为开发人员提供了另一种使代码线程安全的方法，或使其行为线程特定。</span><span class="sxs-lookup"><span data-stu-id="88e17-179">This provides the developer with another way to make code thread safe, or to make its behavior thread specific.</span></span>
  
## <a name="memory-accessible-only-by-more-than-one-thread-critical-sections"></a><span data-ttu-id="88e17-180">仅可由多个线程访问的内存：关键部分</span><span class="sxs-lookup"><span data-stu-id="88e17-180">Memory Accessible Only by More than One Thread: Critical Sections</span></span>

<span data-ttu-id="88e17-181">你应保护可以使用关键部分由多个线程访问的读/写内存。</span><span class="sxs-lookup"><span data-stu-id="88e17-181">You should protect read/write memory that can be accessed by more than one thread using critical sections.</span></span> <span data-ttu-id="88e17-182">您需要为要保护的每个内存块指定一个关键节。</span><span class="sxs-lookup"><span data-stu-id="88e17-182">You need a named critical section for each block of memory you want to protect.</span></span> <span data-ttu-id="88e17-183">您可以在调用 **xlAutoOpen** 函数期间初始化它们，然后释放它们，在调用 **xlAutoClose** 函数期间将它们设置为 null。</span><span class="sxs-lookup"><span data-stu-id="88e17-183">You can initialize these during the call to the **xlAutoOpen** function, and release them and set them to null during the call to the **xlAutoClose** function.</span></span> <span data-ttu-id="88e17-184">然后，你需要包含对 **EnterCriticalSection** 和 **LeaveCriticalSection** 的一对调用中受保护的块的每个访问权限。</span><span class="sxs-lookup"><span data-stu-id="88e17-184">You then need to contain each access to the protected block within a pair of calls to **EnterCriticalSection** and **LeaveCriticalSection**.</span></span> <span data-ttu-id="88e17-185">任何时间仅允许一个线程进入关键部分。</span><span class="sxs-lookup"><span data-stu-id="88e17-185">Only one thread is permitted into the critical section at any time.</span></span> <span data-ttu-id="88e17-186">下面是初始化、取消初始化和使用名为 g_csSharedTable **的示例**。</span><span class="sxs-lookup"><span data-stu-id="88e17-186">Here is an example of the initialization, uninitialization, and use of a section called **g_csSharedTable**.</span></span>
  
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

<span data-ttu-id="88e17-187">保护内存块的另一种可能更安全的方法是创建一个包含其自己的 **CRITICAL_SECTION** 且其构造函数、析构函数和访问器方法负责其使用的类。</span><span class="sxs-lookup"><span data-stu-id="88e17-187">Another, perhaps safer way of protecting a block of memory is to create a class that contains its own **CRITICAL_SECTION** and whose constructor, destructor, and accessor methods take care of its use.</span></span> <span data-ttu-id="88e17-188">此方法还具有保护对象的优势，这些对象可能在 **运行 xlAutoOpen** 之前初始化，或在调用 **xlAutoClose** 后保持有效，但应谨慎创建太多关键节以及这将造成的操作系统开销。</span><span class="sxs-lookup"><span data-stu-id="88e17-188">This approach has the added advantage of protecting objects that may be initialized before **xlAutoOpen** is run, or survive after **xlAutoClose** is called, but you should be careful about creating too many critical sections and the operating system overhead that this would create.</span></span> 
  
<span data-ttu-id="88e17-189">当你的代码需要同时访问多个受保护的内存块时，你需要仔细考虑进入和退出关键部分的顺序。</span><span class="sxs-lookup"><span data-stu-id="88e17-189">When you have code that needs access to more than one block of protected memory at the same time, you need to consider very carefully the order in which the critical sections are entered and exited.</span></span> <span data-ttu-id="88e17-190">例如，以下两个函数可以创建死锁。</span><span class="sxs-lookup"><span data-stu-id="88e17-190">For example, the following two functions could create a deadlock.</span></span>
  
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

<span data-ttu-id="88e17-191">如果一个线程上的第一个函数 **g_csSharedTableA** 另一个线程上的第二个函数进入g_csSharedTableB，则两 **个** 线程挂起。</span><span class="sxs-lookup"><span data-stu-id="88e17-191">If the first function on one thread enters **g_csSharedTableA** while the second on another thread enters **g_csSharedTableB**, both threads hang.</span></span> <span data-ttu-id="88e17-192">正确的方法是按一致的顺序输入并按相反的顺序退出，如下所示。</span><span class="sxs-lookup"><span data-stu-id="88e17-192">The correct approach is to enter in a consistent order and exit in the reverse order, as follows.</span></span>
  
```cs
    EnterCriticalSection(&g_csSharedTableA);
    EnterCriticalSection(&g_csSharedTableB);
    // code that accesses both blocks
    LeaveCriticalSection(&g_csSharedTableB);
    LeaveCriticalSection(&g_csSharedTableA);
```

<span data-ttu-id="88e17-193">如果可能，最好从线程合作的角度隔离对不同块的访问，如下所示。</span><span class="sxs-lookup"><span data-stu-id="88e17-193">Where possible, it is better from a thread co-operation point of view to isolate access to distinct blocks, as shown here.</span></span>
  
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

<span data-ttu-id="88e17-194">如果共享资源存在大量争用，例如频繁出现短期访问请求，则应考虑使用关键节的旋转功能。</span><span class="sxs-lookup"><span data-stu-id="88e17-194">Where there is a lot of contention for a shared resource, such as frequent short-duration access requests, you should consider using the critical section's ability to spin.</span></span> <span data-ttu-id="88e17-195">这是一种技术，可使等待资源的处理器消耗更少。</span><span class="sxs-lookup"><span data-stu-id="88e17-195">This is a technique that makes waiting for the resource less processor-intensive.</span></span> <span data-ttu-id="88e17-196">为此，可以在初始化节时使用 **InitializeCriticalSectionAndSpinCount，** 或在初始化后使用 **SetCriticalSectionSpinCount，** 以设置线程在等待资源可用之前循环次数。</span><span class="sxs-lookup"><span data-stu-id="88e17-196">To do this, you can use either **InitializeCriticalSectionAndSpinCount** when initializing the section or **SetCriticalSectionSpinCount** once initialized, to set the number of times the thread loops before waiting for resources to become available.</span></span> <span data-ttu-id="88e17-197">等待操作成本很高，因此，如果同时释放资源，旋转将避免出现此情况。</span><span class="sxs-lookup"><span data-stu-id="88e17-197">The wait operation is expensive, so spinning avoids this if the resource is freed in the meantime.</span></span> <span data-ttu-id="88e17-198">在单个处理器系统中，调节计数实际上被忽略，但你仍然可以指定它而不做任何损害。</span><span class="sxs-lookup"><span data-stu-id="88e17-198">On a single processor system, the spin count is effectively ignored, but you can still specify it without doing any harm.</span></span> <span data-ttu-id="88e17-199">内存堆管理器使用旋转计数 4000。</span><span class="sxs-lookup"><span data-stu-id="88e17-199">The memory heap manager uses a spin count of 4000.</span></span> <span data-ttu-id="88e17-200">有关使用关键部分的信息，请参阅 Windows SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="88e17-200">For more information about the use of critical sections, see the Windows SDK documentation.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="88e17-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88e17-201">See also</span></span>



[<span data-ttu-id="88e17-202">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="88e17-202">Memory Management in Excel</span></span>](memory-management-in-excel.md)
  
[<span data-ttu-id="88e17-203">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="88e17-203">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="88e17-204">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="88e17-204">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

