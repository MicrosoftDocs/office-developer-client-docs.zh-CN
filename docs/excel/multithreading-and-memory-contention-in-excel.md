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
# <a name="multithreading-and-memory-contention-in-excel"></a>Excel 中的多线程处理和内存争用

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
早版本的 Microsoft Excel 比在 Excel 2007 使用单个线程的所有工作表计算。 但是，从 Excel 2007 开始，Excel 可以配置用于介于 1 到 1024年并发线程工作表计算。 多处理器或多核计算机上, 默认的线程数等于内核处理器的数量。 因此，线程安全单元格或仅包含线程安全的函数的单元格都可以分配给并发线程，受到需要计算其引用单元格后的常用重新计算逻辑。
  
## <a name="thread-safe-functions"></a>线程安全功能

线程安全了大部分启动 Excel 2007 中内置的工作表函数。 您还可以编写并注册为正在线程安全的 XLL 函数。 Excel 使用一个线程 （其主线程） 呼叫所有命令、 线程不安全的功能、 **xlAuto**函数 （除了[xlAutoFree](xlautofree-xlautofree12.md)和**xlAutoFree12**） 和 COM 和 Visual Basic for Applications (VBA) 函数。
  
其中 XLL 函数返回**XLOPER**或**XLOPER12** **xlbitDLLFree**设置，Excel 将使用相同的线程进行函数调用来调用**xlAutoFree**或**xlAutoFree12**。 调用**xlAutoFree**或**xlAutoFree12**由该线程上的下一个函数调用之前。 
  
对于 XLL 开发人员，有以下好处创建线程安全功能：
  
- 它们允许 Excel 充分利用多处理器或多核计算机。
    
- 他们打开比可以进行更有效地使用远程服务器的可能性使用单个线程。
    
假设您有已配置为使用，请说， *N*线程的单处理器计算机。 假设电子表格正在运行，使大量对 XLL 函数的调用，以打开发送请求数据或计算执行到远程服务器或服务器群集。 受到相关性树的拓扑，Excel 无法几乎同时调用的函数 N 时间。 假设或多个服务器都充分 fast 或并行，可减少电子表格的重新计算时间为 1/从一个因子得多 
  
编写线程安全函数中的关键问题正确处理争夺资源。 这通常意味着内存争用，它可以分为两个问题：
  
- 仅将此线程使用如何创建您知道的内存。
    
- 如何确保共享的内存安全地访问由多个线程。
    
首先要注意的是 XLL 哪些内存访问所有线程，且新增仅可访问当前执行的线程。
  
 **访问所有线程**
  
- 变量、 结构和类实例外函数的主体的声明。
    
- 函数的正文内声明的静态变量。
    
在这两种情况，内存设置留出中创建的此实例的 DLL 的 DLL 的内存块。 如果另一个应用程序实例加载 DLL，它获取其自己的内存副本，以便不会从外部 DLL 此实例，这些资源争用。
  
 **只能由当前线程访问**
  
- （包括函数参数） 的函数代码中的自动变量。
    
在这种情况下，在每个实例函数调用堆栈留出设置内存。
  
> [!NOTE]
> 动态分配的内存范围取决于指向它的指针的范围： 如果将指针是可访问所有线程，也是内存。 指针是自动变量函数中的，如果是有效地专用于该线程分配的内存。 
  
## <a name="memory-accessible-by-only-one-thread-thread-local-memory"></a>只能由一个线程可访问的内存： 线程本地内存

静态变量的函数的正文内都可以访问所有线程，使用它们的函数不清楚地线程安全。 一个线程上函数实例无法值更改时另一个线程上的另一个实例假定它为完全不同。 
  
有两个声明函数中的静态变量原因：
  
1. 静态数据保留从到下一个呼叫。
    
2. 安全地可以由函数返回对静态数据的指针。
    
对于第一个原因，您可能希望具有仍然存在，并且有意义的函数的所有呼叫的数据： 或许就会增加每次上任何线程，调用该函数的简单的计数器或收集前夕的使用情况和性能数据结构ry 呼叫。 此问题是如何保护数据结构的共享的数据。 最佳这是下一节介绍使用关键部分。
  
如果数据旨在通过此线程，其原因 1 的情况，始终是原因 2 这种情况，仅用于问题是如何创建仍然存在但才可以访问从此线程的内存。 一个解决方案是使用的线程本地存储区 (TLS) API。
  
例如，请考虑将指针返回到**XLOPER**函数。
  
```cs
LPXLOPER12 WINAPI mtr_unsafe_example(LPXLOPER12 pxArg)
{
    static XLOPER12 xRetVal; // memory shared by all threads!!!
// code sets xRetVal to a function of pxArg ...
    return &xRetVal;
}
```

此函数不是线程安全，因为一个线程可以返回静态**XLOPER12** ，而另一个覆盖它。 更高版本仍然如果**XLOPER12**需要传递给**xlAutoFree12**出现这种情况的可能性。 一种解决方案是分配**XLOPER12**、，返回一个指针和实现**xlAutoFree12** ，以便释放**XLOPER12**内存本身。 在[Excel 中进行内存管理](memory-management-in-excel.md)中所示的示例功能的许多情况下使用此方法。
  
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

简单比依赖 TLS API，下一节所述的方法实现此方法，但它有一些缺点。 首先，Excel 必须调用**xlAutoFree**/ **xlAutoFree12**任何类型的返回**XLOPER**/ **XLOPER12**。 其次，没有问题时返回**XLOPER**/ **XLOPER12**s 的调用的 C API 回调函数的返回值。 **XLOPER**/ **XLOPER12**可能会导致内存需要释放的 Excel，但**XLOPER**/ **XLOPER12**本身，必须释放被分配方式相同。 如果此类**XLOPER**/ **XLOPER12**是要用作 XLL 工作表函数的返回值，没有简单方法，告知**xlAutoFree**/ **xlAutoFree12**的需要两个指针忙以相应的方式。 （设置**xlbitXLFree**和**xlbitDLLFree**未解决此问题，请在两个设置**XLOPER/XLOPER12s**在 Excel 中的处理未和可能更改版本之间的差异。）若要解决此问题，XLL 可以进行深入的所有 Excel 分配**XLOPER/XLOPER12s**它返回到工作表的副本。 
  
避免了这些限制的解决方案是填充并返回线程本地**XLOPER/XLOPER12**，需要**xlAutoFree/xlAutoFree12**该方法不会释放**XLOPER/XLOPER12**指针本身。 
  
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

下一个问题是如何设置和检索的线程本地内存，换句话说，如何实现函数**get_thread_local_xloper12**在上面的示例。 这是使用线程本地存储 (TLS) API。 第一步是使用**TlsAlloc**，最终必须通过使用**TlsFree**释放其获取 TLS 索引。 这两最佳完成从**DllMain**。
  
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

获取索引后下, 一步是内存的为每个线程分配块。 [Windows 开发文档](http://msdn.microsoft.com/en-us/library/ms682583%28VS.85%29.aspx)建议这样做，每次**DllMain**回调函数调用与**DLL_THREAD_ATTACH**事件，以及在每个**DLL_THREAD_DETACH**内存。 但是，关注此建议将导致 DLL 执行不必要的工作线程在不用于重新计算。 
  
相反，则最好使用分配上第一个使用策略。 首先，您需要定义要为每个线程分配结构。 返回**XLOPERs**或**XLOPER12s**的上一个示例，以下足够了，但您可以创建任何结构符合您的需求。
  
```cs
struct TLS_data
{
    XLOPER xloper_shared_ret_val;
    XLOPER12 xloper12_shared_ret_val;
// Add other required thread-local data here...
};
```

下面的函数获取一个指针指向线程本地实例，或如果这是首次调用分配一个。
  
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

现在您可以查看如何获取线程本地**XLOPER/XLOPER12**内存： 首先，指针进入**TLS_data**的线程的实例，然后将您返回到**XLOPER/XLOPER12** ，如下所示，其中包含一个指针。 
  
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

运行 Excel 时，可以将**mtr_safe_example_1**和**mtr_safe_example_2**函数注册为线程安全工作表函数。 但是，不能混合一个 XLL 中的两种方法。 您 XLL 只能导出一个实现**xlAutoFree**和**xlAutoFree12**，并且每个内存策略需要不同的方法。 与**mtr_safe_example_1**，以及它指向的任何数据，必须释放传递给**xlAutoFree/xlAutoFree12**的指针。 与**mtr_safe_example_2**，应释放仅指向的数据。
  
Windows 还提供了一个函数**GetCurrentThreadId**，它返回当前线程的唯一系统范围 id。 这将为开发人员提供使代码线程安全的或者使其行为线程特定的另一种方法。
  
## <a name="memory-accessible-only-by-more-than-one-thread-critical-sections"></a>只能由多个线程可访问的内存： 关键节

您应该保护可以通过使用关键节的多个线程的读/写内存。 对于每个要保护的内存块中需要命名的关键部分。 您可以初始化在**xlAutoOpen**函数中，调用过程和释放其期间对**xlAutoClose**函数的调用将它们设置为 null。 然后，您需要包含对受保护的块内调用**EnterCriticalSection**和**LeaveCriticalSection**的一对每个访问。 只有一个线程允许到关键部分中，在任何时间。 下面是部分的初始化、 非初始化，并使用调用**g_csSharedTable**的一个示例。
  
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

保护内存块的另一个、 也许更安全的方式是创建一个类，其中包含自己**CRITICAL_SECTION**其构造函数、 析构函数，并使用解决访问器方法。 此方法的优点添加了保护之前**xlAutoOpen**运行或排除后调用**xlAutoClose**时，可能初始化的对象，但您应注意有关创建太多的关键部分和操作系统这将创建的开销。 
  
同时需要访问受保护的内存的多个块的代码后，您需要非常仔细考虑的关键部分进行输入和退出的顺序。 例如，以下两个功能还可以创建死锁。
  
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

如果一个线程上的第一个函数输入**g_csSharedTableA**当另一个线程上的第二个进入**g_csSharedTableB**时，这两个线程挂起。 正确的方法是一致的顺序进入和退出的相反顺序，如下所示。
  
```cs
    EnterCriticalSection(&g_csSharedTableA);
    EnterCriticalSection(&g_csSharedTableB);
    // code that accesses both blocks
    LeaveCriticalSection(&g_csSharedTableB);
    LeaveCriticalSection(&g_csSharedTableA);
```

在可能的情况下，最好是从线程共同操作角度隔离访问不同块，如下所示。
  
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

其中没有大量争用共享资源，如常用 short 持续时间访问请求，您应考虑使用关键部分中的功能旋转。 这是一种使较少的处理器密集型等待资源的技术。 若要执行此操作，您可以使用任一**InitializeCriticalSectionAndSpinCount**初始化节或**SetCriticalSectionSpinCount**一旦初始化，若要设置的次数之前等待资源成为循环线程时可用。 等待操作很高，，因此旋转可避免这，如果同时会释放资源。 在单个处理器系统上，实际上会忽略调节计数，但不进行任何损害，仍可以所指定。 内存堆管理器使用 4000 调节计数。 有关如何使用的关键部分的详细信息，请参阅 Windows SDK 文档。 
  
## <a name="see-also"></a>另请参阅



[Excel 中的内存管理](memory-management-in-excel.md)
  
[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

