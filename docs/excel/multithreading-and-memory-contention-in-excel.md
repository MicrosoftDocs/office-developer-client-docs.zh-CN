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
# <a name="multithreading-and-memory-contention-in-excel"></a>线程中的多线程和内存Excel

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
2007 Microsoft Excel 2007 Excel版本将单个线程用于所有工作表计算。 但是，从 2007 Excel，Excel配置为使用 1 到 1024 个并发线程进行工作表计算。 在多处理器或多核计算机上，线程的默认数量等于处理器或内核数。 因此，线程安全单元格或仅包含线程安全函数的单元格可被分配至并发线程，但需按照需要在引用单元格之后计算的通常重新计算逻辑。
  
## <a name="thread-safe-functions"></a>Thread-Safe 函数

从 2007 年 2 Excel，大多数内置工作表函数都是线程安全的。 还可以编写 XLL 函数并注册为线程安全函数。 Excel使用一个线程 (其主线程) 来调用所有命令、非线程安全函数 **、xlAuto** 函数 [ (（xlAutoFree](xlautofree-xlautofree12.md)和 **xlAutoFree12**) 除外）以及 COM 和 Visual Basic for Applications (VBA) 函数。
  
当 XLL 函数返回设置了 **xlbitDLLFree** 的 **XLOPER** 或 **XLOPER12** 时，Excel 将使用函数调用所基于的同一线程调用 **xlAutoFree** 或 **xlAutoFree12。** 在线程上的下一个函数调用之前，调用 **xlAutoFree** 或 **xlAutoFree12。** 
  
对于 XLL 开发人员，创建线程安全函数有一些好处：
  
- 它们Excel充分利用多处理器或多核计算机。
    
- 它们比使用单个线程可以更高效地使用远程服务器的可能性大很多。
    
假设您有一台已配置为使用（例如  *，N*  个线程）的单处理器计算机。 假定电子表格正在运行，该电子表格对 XLL 函数进行大量调用，而 XLL 函数又向远程服务器或服务器群集发送数据请求或计算请求。 根据依赖关系树的拓扑，Excel几乎同时调用函数 N 次。 如果一个或多个服务器速度足够快或并行，电子表格的重新计算时间可以缩短 1/N 的一个因子。 
  
编写线程安全函数的关键问题是正确处理资源的争用。 这通常意味着内存争用，它可以分为两个问题：
  
- 如何创建你知道仅此线程使用的内存。
    
- 如何确保多个线程安全地访问共享内存。
    
首先要注意的一点就是 XLL 中的哪些内存可供所有线程访问，以及当前执行的线程只能访问哪些内存。
  
 **所有线程均可访问**
  
- 在函数正文之外声明的变量、结构和类实例。
    
- 在函数的正文中声明的静态变量。
    
在这两种情况下，内存将留出在为此 DLL 实例创建的 DLL 的内存块中。 如果另一个应用程序实例加载 DLL，它将获取该内存的其自己的副本，以便不从 DLL 的此实例之外争用这些资源。
  
 **仅当前线程可访问**
  
- 函数代码中的自动变量 (包括函数参数) 。
    
在这种情况下，会为函数调用的每个实例在堆栈上留出内存。
  
> [!NOTE]
> 动态分配的内存作用域取决于指向它的指针范围：如果指针可由所有线程访问，则内存也是。 如果指针是函数中的自动变量，则分配的内存实际上对于该线程是私有的。 
  
## <a name="memory-accessible-by-only-one-thread-thread-local-memory"></a>仅一个线程可访问的内存：Thread-Local内存

鉴于所有线程均可访问函数正文中的静态变量，使用它们的函数明显不是线程安全的。 一个线程上的函数的一个实例可能会更改值，而另一个线程上的另一个实例假定该值完全不同。 
  
声明函数中的静态变量有两个原因：
  
1. 静态数据从一个调用持续到下一个调用。
    
2. 指向静态数据的指针可通过 函数安全地返回。
    
在出于第一个原因的情况下，你可能希望具有对函数的所有调用具有持久性和含义的数据：可能是每次在任何线程上调用函数时递增的简单计数器，或者是收集每次调用的使用率和性能数据的结构。 问题是如何保护共享数据或数据结构。 如下一节所述，最好使用关键部分完成此操作。
  
如果数据仅供此线程使用（可能是由于原因 1 的情况，并且原因 2 始终如此，则问题是如何创建保留但只能从此线程访问的内存。 一个解决方案是使用线程本地存储 (TLS) API。
  
例如，考虑一个返回指向 **XLOPER 的指针的函数**。
  
```cs
LPXLOPER12 WINAPI mtr_unsafe_example(LPXLOPER12 pxArg)
{
    static XLOPER12 xRetVal; // memory shared by all threads!!!
// code sets xRetVal to a function of pxArg ...
    return &xRetVal;
}
```

此函数不是线程安全的，因为一个线程可以返回静态 **XLOPER12，** 而另一个线程会覆盖它。 如果需要将 **XLOPER12** 传递到 **xlAutoFree12，** 则发生此情况的可能性仍然更大。 一个解决方案是分配 **一个 XLOPER12，** 返回指向它的指针，并实现 **xlAutoFree12，** 以便 **释放 XLOPER12** 内存本身。 此方法在 Memory Management in [Excel 中显示的许多示例函数中Excel。](memory-management-in-excel.md)
  
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

此方法的实现比下一节中介绍的方法更简单，该方法依赖于 TLS API，但它有一些缺点。 首先，Excel必须调用 **xlAutoFree** /  **xlAutoFree12，** 无论返回 **的 XLOPER** /  **XLOPER12 的类型是什么**。 其次，返回 /  **XLOPER XLOPER12** 时出现问题，这是对 C API 回调函数的调用的返回值。 **XLOPER** /  **XLOPER12** 可能指向需要由 Excel 释放的内存，但 **XLOPER** /  **XLOPER12** 本身必须按分配的方式释放。 如果将此类 **XLOPER XLOPER12** 用作 XLL 工作表函数的返回值，则没有简单的方法通知 /  **xlAutoFree** /  **xlAutoFree12** 需要以适当的方式释放这两个指针。  (同时设置 **xlbitXLFree** 和 **xlbitDLLFree** 无法解决问题，因为 Excel 中同时使用这两个集的 **XLOPER/XLOPER12** 的处理未定义，并且可能会随版本更改。) 若要解决此问题，XLL 可以制作它返回到工作表的所有 Excel 分配的 **XLOPER/XLOPER12** 的深层副本。 
  
避免这些限制的解决方案是填充和返回线程本地 **XLOPER/XLOPER12，** 该方法需要 **xlAutoFree/xlAutoFree12** 不释放 **XLOPER/XLOPER12** 指针本身。 
  
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

下一个问题是如何设置和检索线程本地内存， **也就是说** ，如何在上一示例中get_thread_local_xloper12函数。 这是通过使用线程本地存储 (TLS) API 完成。 第一步是使用 **TlsAlloc** 获取 TLS 索引，该索引最终必须使用 **TlsFree 发布**。 两者最好通过 **DllMain 实现**。
  
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

获取索引后，下一步是为每个线程分配内存块。 开发 [Windows文档](https://msdn.microsoft.com/library/ms682583%28VS.85%29.aspx)建议每次使用 **DLL_THREAD_ATTACH** 事件调用 **DllMain** 回调函数时执行此操作，并释放每个 **DLL_THREAD_DETACH。** 但是，遵循此建议将导致 DLL 对不用于重新计算的线程执行不必要的工作。 
  
相反，最好使用"首次使用时分配"策略。 首先，需要定义要为每个线程分配的结构。 对于返回 **XLOPERs** 或 **XLOPER12s** 的上一个示例，满足以下条件，但您可以创建满足您需求的任何结构。
  
```cs
struct TLS_data
{
    XLOPER xloper_shared_ret_val;
    XLOPER12 xloper12_shared_ret_val;
// Add other required thread-local data here...
};
```

以下函数获取指向线程本地实例的指针，如果这是第一个调用，则分配一个。
  
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

现在，你可以看到如何获取线程本地 **XLOPER/XLOPER12** 内存：首先，获取指向 **线程的 TLS_data** 实例的指针，然后返回一个指向其中包含的 **XLOPER/XLOPER12** 的指针，如下所示。 
  
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

在 **mtr_safe_example_1 mtr_safe_example_2** 时，可以将函数和函数注册为线程安全Excel。 但是，您不能在一个 XLL 中混合使用这两种方法。 你的 XLL 只能导出 **xlAutoFree** 和 **xlAutoFree12** 的一个实现，并且每个内存策略都需要不同的方法。 使用 **mtr_safe_example_1** 时，必须释放传递给 **xlAutoFree/xlAutoFree12** 的指针以及它指向的任何数据。 使用 **mtr_safe_example_2**，应仅释放指向的数据。
  
Windows还提供 **GetCurrentThreadId** 函数，该函数返回当前线程的唯一系统范围 ID。 这为开发人员提供了另一种使代码线程安全的方法，或使其行为线程特定。
  
## <a name="memory-accessible-only-by-more-than-one-thread-critical-sections"></a>仅可由多个线程访问的内存：关键部分

你应保护可以使用关键部分由多个线程访问的读/写内存。 您需要为要保护的每个内存块指定一个关键节。 您可以在调用 **xlAutoOpen** 函数期间初始化它们，然后释放它们，在调用 **xlAutoClose** 函数期间将它们设置为 null。 然后，你需要包含对 **EnterCriticalSection** 和 **LeaveCriticalSection** 的一对调用中受保护的块的每个访问权限。 任何时间仅允许一个线程进入关键部分。 下面是初始化、取消初始化和使用名为 g_csSharedTable **的示例**。
  
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

保护内存块的另一种可能更安全的方法是创建一个包含其自己的 **CRITICAL_SECTION** 且其构造函数、析构函数和访问器方法负责其使用的类。 此方法还具有保护对象的优势，这些对象可能在 **运行 xlAutoOpen** 之前初始化，或在调用 **xlAutoClose** 后保持有效，但应谨慎创建太多关键节以及这将造成的操作系统开销。 
  
当你的代码需要同时访问多个受保护的内存块时，你需要仔细考虑进入和退出关键部分的顺序。 例如，以下两个函数可以创建死锁。
  
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

如果一个线程上的第一个函数 **g_csSharedTableA** 另一个线程上的第二个函数进入g_csSharedTableB，则两 **个** 线程挂起。 正确的方法是按一致的顺序输入并按相反的顺序退出，如下所示。
  
```cs
    EnterCriticalSection(&g_csSharedTableA);
    EnterCriticalSection(&g_csSharedTableB);
    // code that accesses both blocks
    LeaveCriticalSection(&g_csSharedTableB);
    LeaveCriticalSection(&g_csSharedTableA);
```

如果可能，最好从线程合作的角度隔离对不同块的访问，如下所示。
  
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

如果共享资源存在大量争用，例如频繁出现短期访问请求，则应考虑使用关键节的旋转功能。 这是一种技术，可使等待资源的处理器消耗更少。 为此，可以在初始化节时使用 **InitializeCriticalSectionAndSpinCount，** 或在初始化后使用 **SetCriticalSectionSpinCount，** 以设置线程在等待资源可用之前循环次数。 等待操作成本很高，因此，如果同时释放资源，旋转将避免出现此情况。 在单个处理器系统中，调节计数实际上被忽略，但你仍然可以指定它而不做任何损害。 内存堆管理器使用旋转计数 4000。 有关使用关键部分的信息，请参阅 Windows SDK 文档。 
  
## <a name="see-also"></a>另请参阅



[Excel 中的内存管理](memory-management-in-excel.md)
  
[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

