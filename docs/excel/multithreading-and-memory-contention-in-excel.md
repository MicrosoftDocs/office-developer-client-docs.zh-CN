---
title: Excel 中的多线程和内存争用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- excel 中的多线程, excel 中的内存争用, 函数 [excel 2007], 线程安全, 线程安全函数 [excel 2007], 线程-本地内存 [excel 2007]
localization_priority: Normal
ms.assetid: 86e1e842-f433-4ea9-8b13-ad2515fc50d8
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a385728450fc6519d7f5211c186a9d74e623bf7b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301636"
---
# <a name="multithreading-and-memory-contention-in-excel"></a>Excel 中的多线程和内存争用

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
早于 excel 2007 的 Microsoft Excel 版本在所有工作表计算中使用一个线程。 但是, 从 excel 2007 开始, 可以将 excel 配置为使用1到1024并发线程来计算工作表。 在多处理器或多核计算机上, 默认线程数等于处理器或内核数。 因此, 只有包含线程安全的函数的线程安全单元格或单元格可以分配给并发线程, 这取决于需要在引用单元格之后计算的常见重新计算逻辑。
  
## <a name="thread-safe-functions"></a>线程安全函数

在 Excel 2007 中启动的大多数内置工作表函数都是线程安全的。 您还可以将 XLL 函数编写并注册为线程安全。 Excel 使用一个线程 (它的主线程) 调用所有命令、线程不安全函数、 **xlAuto**函数 (除了[xlAutoFree](xlautofree-xlautofree12.md)和**xlAutoFree12**) 以及 COM 和 Visual Basic for Applications (VBA) 函数。
  
当 XLL 函数返回具有**xlbitDLLFree**集的**XLOPER**或**XLOPER12**时, Excel 将使用对其进行函数调用的线程, 以调用**xlAutoFree**或**xlAutoFree12**。 对**xlAutoFree**或**xlAutoFree12**的调用是在该线程上的下一个函数调用之前进行的。 
  
对于 XLL 开发人员, 创建线程安全函数有一些好处:
  
- 它们使 Excel 可以充分利用多处理器或多核计算机。
    
- 他们打开远程服务器的可能性远远高于使用单个线程完成的效率。
    
假设您有一个已配置为使用的单处理器计算机, 例如*N*个线程。 假设正在运行的电子表格会对 XLL 函数进行大量调用, 进而发送对数据的请求或对远程服务器或服务器群集执行的计算。 根据依赖关系树的拓扑, Excel 几乎可以同时调用函数 N 次。 如果服务器或服务器的速度足够快或平行, 则电子表格的重新计算时间可能会降低为 1/N 的系数。 
  
编写线程安全函数的关键问题是正确处理资源的争用。 这通常意味着内存争用, 并且可以分为两个问题:
  
- 如何创建您已知将仅由此线程使用的内存。
    
- 如何确保多个线程安全地访问共享内存。
    
首先要注意的一点是, XLL 中的内存是所有线程都可访问的, 并且只能由当前正在执行的线程访问。
  
 **所有线程都可访问**
  
- 在函数体外部声明的变量、结构和类实例。
    
- 在函数体中声明的静态变量。
    
在这两种情况下, 将在为此 dll 实例创建的 dll 内存块中留出内存。 如果另一个应用程序实例加载 DLL, 它将获取该内存的自己的副本, 以便不会对此 dll 实例之外的这些资源进行争用。
  
 **只能由当前线程访问**
  
- 函数代码 (包括函数参数) 中的自动变量。
    
在这种情况下, 堆栈上为函数调用的每个实例留出内存。
  
> [!NOTE]
> 动态分配内存的作用域取决于指向它的指针的作用域: 如果指针可由所有线程访问, 则内存也是如此。 如果指针是函数中的自动变量, 则分配给该线程的内存实际上是私有的。 
  
## <a name="memory-accessible-by-only-one-thread-thread-local-memory"></a>仅有一个线程可访问的内存: 线程本地内存

假定函数主体中的静态变量可由所有线程访问, 但使用它们的函数显然不是线程安全的。 一个线程上的函数的一个实例可以更改值, 而另一个线程上的另一个实例假设它是完全不同的内容。 
  
在函数中声明静态变量的原因有两个:
  
1. 静态数据将从一个调用保留到下一个调用。
    
2. 函数可安全返回指向静态数据的指针。
    
在第一种原因的情况下, 您可能希望具有对函数的所有调用的持续和意义的数据: 可能是在每次调用函数时递增的简单计数器, 或者是在前夕上收集使用率和性能数据的结构ry 调用。 问题是如何保护共享数据或数据结构。 最好是通过在下一节中介绍的关键部分来完成此操作。
  
如果数据仅供此线程使用, 则原因可能是原因1的情况, 并且是原因2的总大小写, 问题是如何创建持续存在但只能从此线程访问的内存。 一种解决方案是使用线程本地存储 (TLS) API。
  
例如, 请考虑一个返回指向**XLOPER**的指针的函数。
  
```cs
LPXLOPER12 WINAPI mtr_unsafe_example(LPXLOPER12 pxArg)
{
    static XLOPER12 xRetVal; // memory shared by all threads!!!
// code sets xRetVal to a function of pxArg ...
    return &xRetVal;
}
```

此函数不是线程安全的, 因为一个线程可以返回静态**XLOPER12** , 而另一个线程会将其覆盖。 发生这种情况的可能性更大, 但如果需要将**XLOPER12**传递给**xlAutoFree12**。 一种解决方案是分配一个**XLOPER12**, 返回指向它的指针, 并实现**xlAutoFree12** , 以便释放**XLOPER12**内存本身。 在 Excel 中的[内存管理](memory-management-in-excel.md)中显示的许多示例函数中使用此方法。
  
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

此方法更易于实现, 而不是下一节中介绍的方法, 它依赖于 TLS API, 但有一些缺点。 首先, Excel 必须调用**xlAutoFree**/ **xlAutoFree12** , 无论返回的是哪种类型的**XLOPER**/ **XLOPER12**。 其次, 返回**XLOPER**/ **XLOPER12**s 时出现问题, 即对 C API 回调函数的调用的返回值。 **XLOPER**/ **XLOPER12**可能指向需要由 Excel 释放的内存, 但**XLOPER**/ **XLOPER12**本身必须按其分配的相同方式进行释放。 如果将此类**XLOPER**/ **XLOPER12**用作 XLL 工作表函数的返回值, 则没有简单的方法来通知**xlAutoFree**/ **xlAutoFree12**是否需要以适当的方式释放这两个指针。 (同时设置**xlbitXLFree**和**xlbitDLLFree**不能解决问题, 因为在 Excel 中对**XLOPER/XLOPER12s**的处理未定义, 并且可能会从版本更改为版本。为了解决此问题, XLL 可以制作所有 Excel 分配的**XLOPER/XLOPER12s**的深层副本, 并将其返回到工作表中。 
  
避免这些限制的解决方案是填充和返回一个线程本地**XLOPER/XLOPER12**, 这是一种需要该**xlAutoFree/xlAutoFree12**不会释放**XLOPER/XLOPER12**指针本身的方法。 
  
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

下一个问题是如何设置和检索线程本地内存, 换句话说, 如何在上一示例中实现函数**get_thread_local_xloper12** 。 这是使用线程本地存储 (TLS) API 完成的。 第一步是使用**TlsAlloc**获取 TLS 索引, 它最终必须使用**TlsFree**发布。 这两个最佳实现都是通过**DllMain**实现的。
  
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

获取索引后, 下一步是为每个线程分配内存块。 [Windows 开发文档](https://msdn.microsoft.com/library/ms682583%28VS.85%29.aspx)建议在每次使用**DLL_THREAD_ATTACH**事件调用**DllMain**回调函数, 并在每个**DLL_THREAD_DETACH**上释放内存时执行此操作。 但是, 遵循此建议将导致 DLL 对不用于重新计算的线程执行不必要的工作。 
  
相反, 最好使用 "首次使用时分配" 策略。 首先, 需要定义要为每个线程分配的结构。 对于前面返回**XLOPERs**或**XLOPER12s**的示例, 以下 suffices, 但您可以创建满足您的需求的任何结构。
  
```cs
struct TLS_data
{
    XLOPER xloper_shared_ret_val;
    XLOPER12 xloper12_shared_ret_val;
// Add other required thread-local data here...
};
```

下面的函数获取指向线程本地实例的指针, 如果这是第一个调用, 则分配一个指针。
  
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

现在, 您可以了解如何获取线程本地**XLOPER/XLOPER12**内存: 首先, 您会收到指向线程的**TLS_data**实例的指针, 然后您将返回指向包含在其中的**XLOPER/XLOPER12**的指针, 如下所示。 
  
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

在运行 Excel 时, 可以将**mtr_safe_example_1**和**mtr_safe_example_2**函数注册为线程安全工作表函数。 但是, 不能在一个 XLL 中混合使用这两种方法。 XLL 只能导出**xlAutoFree**和**xlAutoFree12**的一种实现, 并且每个内存策略都需要不同的方法。 对于**mtr_safe_example_1**, 传递给**xlAutoFree/xlAutoFree12**的指针必须与它所指向的任何数据一起释放。 使用**mtr_safe_example_2**时, 只应释放指向的数据。
  
Windows 还提供了一个函数**GetCurrentThreadId**, 它返回当前线程的唯一系统范围的 ID。 这为开发人员提供了另一种使代码线程安全的方法, 或使其具有特定的行为线程。
  
## <a name="memory-accessible-only-by-more-than-one-thread-critical-sections"></a>仅可由多个线程访问的内存: 临界节

应使用关键部分保护可由多个线程访问的读/写内存。 对于要保护的每个内存块, 您都需要一个已命名的临界区。 您可以在调用**xlAutoOpen**函数期间对这些函数进行初始化, 并在调用**xlAutoClose**函数期间将其释放并将其设置为 null。 然后, 您需要在对**EnterCriticalSection**和**LeaveCriticalSection**的一对受保护的块中包含每个访问权限。 任何时候都只允许一个线程进入临界区。 下面是一个初始化、uninitialization 和使用名为**g_csSharedTable**的节的示例。
  
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

另一种方法是, 保护内存块的安全方法是创建一个类, 其中包含自己的**CRITICAL_SECTION** , 其构造函数、析构函数和访问器方法负责使用它。 此方法增加了以下优势: 保护在**xlAutoOpen**运行之前可以初始化的对象, 或在调用**xlAutoClose**后继续运行的对象, 但在创建过多的关键部分和操作系统时应谨慎。这将创建的开销。 
  
当您的代码需要同时访问多个受保护的内存块时, 您需要仔细考虑关键节的输入和退出顺序。 例如, 以下两个函数可能会产生死锁。
  
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

如果一个线程中的第一个函数进入**g_csSharedTableA** , 而另一个线程上的第二个线程进入**g_csSharedTableB**, 则这两个线程都挂起。 正确的方法是按一致的顺序输入并按相反顺序退出, 如下所示。
  
```cs
    EnterCriticalSection(&g_csSharedTableA);
    EnterCriticalSection(&g_csSharedTableB);
    // code that accesses both blocks
    LeaveCriticalSection(&g_csSharedTableB);
    LeaveCriticalSection(&g_csSharedTableA);
```

在可能的情况下, 最好从线程协作操作点来隔离对不同块的访问, 如下所示。
  
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

如果有大量争用共享资源 (例如频繁的短时间访问请求), 则应考虑使用临界区的旋转能力。 这是一项技术, 可使资源等待更少的占用处理器的资源。 若要执行此操作, 您可以在初始化节或**SetCriticalSectionSpinCount**时使用任一**InitializeCriticalSectionAndSpinCount** , 以设置在等待资源变为前线程循环的次数可用. 等待操作成本较高, 因此如果在同时释放资源, 将会避免这种情况。 在单处理器系统上, 将有效地忽略自旋计数, 但仍可以指定它, 而不会造成任何损害。 内存堆管理器使用的数值调节计数为4000。 有关使用关键部分的详细信息, 请参阅 Windows SDK 文档。 
  
## <a name="see-also"></a>另请参阅



[Excel 中的内存管理](memory-management-in-excel.md)
  
[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

