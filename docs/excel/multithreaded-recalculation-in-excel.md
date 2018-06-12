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
# <a name="multithreaded-recalculation-in-excel"></a>在 Excel 中的多线程重新计算

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
Microsoft Office Excel 2007 是 Excel 使用多线程重新计算 (MTR) 的工作表的第一版。 您可以配置 Excel 时要使用最多为 1024年并发线程重新计算，无论在计算机上的处理器内核处理器的数量。 
  
> [!NOTE]
> 没有与每个线程，开销关联，因此不应配置 Excel 使用更多需要线程操作系统。 
  
如果计算机有多个处理器或处理器内核，操作系统所需的最适合您的方式分配给处理器线程的责任。
  
## <a name="excel-mtr-overview"></a>Excel MTR 概述 （英文)

Excel 尝试确定可以在不同线程同时重新计算的计算链部分。 以下非常简单树 （其中 x ← y 意味着 y 仅取决于 x） 显示此示例。
  
**图 1。在不同线程上同时计算**

![在不同线程上同时计算](media/12b5a52b-6308-420c-b6cf-492bd1f195ce.gif "在不同线程上同时计算")
  
计算 A1 后，A2 然后 A3 可以计算一个线程上同时 B1 然后 C1 可以计算另一个，假定所有单元格都安全的线程。 
  
> [!NOTE]
> 术语线程安全单元格表示仅包含线程安全函数的单元格。 将详细介绍什么是而不是线程安全[新增和是不被视为线程安全由 Excel](#xl2007xllsdk_threadsafe)。 
  
大多数实际工作簿包含更复杂的依赖项树比此示例。 此外，直到计算完成和可能相差根据函数的参数，则无法知道单元格的重新计算时间。 若要获得最佳结果，Excel 尝试提高在每次计算的计算顺序，直到可以无进一步优化。
  
Excel 中使用单个主线程运行或执行以下：
  
- 内置命令。
    
- XLL 命令
    
- XLL 加载项管理器界面函数 （**xlAutoOpen**函数等） 
    
- Microsoft Visual Basic for Applications (VBA) 用户定义命令 （通常称作宏）
    
- VBA 用户定义函数
    
- 内置线程不安全的工作表函数 （请参阅下一节的列表）
    
- XLM 宏工作表用户定义的命令和函数
    
- COM 加载项命令和函数
    
- 函数和条件格式表达式中的运算符
    
- 函数和中定义的名称定义在工作表公式中使用的运算符
    
- 强制使用**F9**键的公式编辑框中的表达式的计算 
    
除非 Excel 配置为使用多个线程，对主线程进行评估工作表中的所有公式，无论是否函数是否线程安全。 当用户指定应使用多个线程时，更多线程用于线程安全单元格。 请注意时意义从负载平衡的点的视图后，仍可能主线程线程安全单元格中使用。
  
值得复述，Excel 不同时运行多个命令，因此不需要为写入线程安全功能，如使用线程本地内存和关键节的时采用相同的预防措施。
  
## <a name="what-is-and-is-not-considered-thread-safe-by-excel"></a>什么是，不被视作线程安全由 Excel
<a name="xl2007xllsdk_threadsafe"> </a>

Excel 只考虑以下内容作为线程安全：
  
- 在 Excel 中的所有一元和二元运算符。
    
- 启动 Excel 2007 （请参阅例外列表） 中的几乎所有内置的工作表函数
    
- XLL 加载项的功能已显式注册为线程安全。
    
不线程安全的内置工作表功能是：
  
- **拼音**
    
- **单元格**时使用的"格式"或"address"的参数 
    
- **间接**
    
- **GETPIVOTDATA**
    
- **CUBEMEMBER**
    
- **CUBEVALUE**
    
- **CUBEMEMBERPROPERTY**
    
- **CUBESET**
    
- **CUBERANKEDMEMBER**
    
- **CUBEKPIMEMBER**
    
- **CUBESETCOUNT**
    
- **地址**在给定第五个参数 (sheet_name) 
    
- 对数据透视表是指任何数据库函数 （**DSUM**、 **DAVERAGE**，等等）
    
- **错误。类型**
    
- **超链接**
    
若要显式，以下被视为不安全：
  
- VBA 用户定义函数
    
- COM 加载项用户定义函数
    
- XLM 宏工作表的用户定义函数
    
- XLL 加载项功能未显式注册为线程安全
    
含义是，下面的操作和功能不是线程安全的并且如果从注册为线程安全的 XLL 函数调用失败：
  
- XLM 信息函数调用，例如， **xlfGetCell** (**GET。单元格**)。
    
- 呼叫到**xlfSetName** (**SET.NAME**) 定义或删除 XLL 内部名称。
    
- 对使用**xlUDF**线程不安全用户定义函数的调用。
    
- 对表达式包含线程不安全的函数或包含已定义的名称，其定义包含线程不安全的函数调用[xlfEvaluate](xlfevaluate.md)函数。 
    
- 若要清除中断条件对[xlAbort](xlabort.md)函数调用。 
    
- 调用[xlCoerce](xlcoerce.md)函数以获取未计算的单元格引用的值。 
    
> [!NOTE]
> 不允许 XLL 工作表函数调用 C API 命令，如**xlcSave**，无论是否他们已注册为线程安全或不。 
  
假定 XLL 函数声明为线程安全无法调用 XLM 信息函数或引用未计算的单元格，Excel 不允许注册为宏工作表的等效项以还注册为线程安全的 XLL 函数。 因此尝试获取使用**xlCoerce**未计算的单元格引用的值失败并出现**xlretUncalced**错误。 调用 XLM 信息函数操作失败， **xlretFailed**错误。 以前失败的列出的其他点，并在 Excel C API 中引入的错误代码： **xlretNotThreadSafe**。 
  
C 仅 API 的回调函数是所有线程安全：
  
- **xlCoerce**（虽然强制未计算的单元格的引用失败除外） 
    
- **xlFree**
    
- **xlStack**
    
- **xlSheetId**
    
- **xlSheetNm**
    
- **xlAbort**（使用以清除中断条件时除外） 
    
- **xlGetInst**
    
- **xlGetHwnd**
    
- **xlGetBinaryName**
    
- **xlDefineBinaryName**
    
一个例外情况是**xlset，则**函数，它是，在任何情况下，命令等效项，因此无法从调用任何工作表函数。 
  
可以使用 Excel 注册 XLL 工作表函数，为线程安全。 这会告诉 Excel，可以安全地调用该函数并同时在多个线程，但您必须确保这是真正这种情况。 如果不安全地那么行为就注册为线程安全的函数，您可能可以更改 Excel。
  
## <a name="registering-xll-functions-as-thread-safe"></a>注册为线程安全的 XLL 函数
<a name="xl2007xllsdk_threadsafe"> </a>

开发人员编写线程安全功能时必须遵循的规则如下所示：
  
- 不要调用其他可能无法线程安全的 Dll 中的资源。
    
- 不执行任何线程不安全的 C API 或 COM.通过调用
    
- 保护无法由使用关键节的多个线程同时使用的资源。
    
- 线程本地内存用于线程特定存储，并替换线程本地变量的函数中的静态变量。
    
Excel 施加其他限制： 线程安全函数无法注册宏工作表的等效项，为，因此无法调用 XLM 信息函数或获取未重新计算的单元格的值。
  
## <a name="memory-contention"></a>内存争用
<a name="xl2007xllsdk_threadsafe"> </a>

多线程的系统必须考虑两个基本问题：
  
- 如何保护必须从，读取或写入，由多个线程的内存。
    
- 如何创建和访问的内存，并且该镜像相关联，因此专用于，正在执行的线程。
    
Windows 操作系统和 Windows 软件开发工具包 (SDK) 这两种提供工具： 关键节和线程本地存储 (TLS) API 分别。 有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。
  
例如，两个工作表函数 （或两个同时运行的相同的功能实例） 需要访问或修改全局变量在 DLL 项目时，可能出现的第一个问题。 请记住，可能的类对象的全局可访问实例中隐藏这样一个全局变量。
  
例如，当工作表函数声明静态变量或函数正文代码中的对象时，可能出现第二个问题。 C/c + + 编译器仅创建所有线程都使用的一个副本。 这意味着该函数的一个实例无法更改此值时可能的值其以前设置假定在不同线程上的另一个。
  
## <a name="example-applications-of-mtr"></a>示例应用程序的 MTR
<a name="xl2007xllsdk_threadsafe"> </a>

导出工作表函数任何 XLL 可以利用多线程重新计算 (MTR) 在 Excel 中，前提是这些函数不需要执行线程不安全的操作。 这使 Excel 重新计算的依赖于它们尽可能快地工作簿，因此需要任何应用程序。
  
具体而言，MTR 上的工作簿调用用户定义的函数 (Udf) 自己呼叫外部进程以获取所需的结果的重新计算时间有重大影响。 特别考虑调用可同时处理多个请求的远程服务器的 UDF 和包含多次调用该函数的工作簿。 如果重新计算工作簿是单线程，每个调用 UDF，并因此到远程服务器，必须完成下一个才能进行。 这浪费同时处理多个呼叫服务器的能力。 如果重新计算工作簿的是多线程，Excel 可以同时或快速连续进行多个呼叫。
  
如果 Excel 配置为使用相同的线程数作为服务器 — 调用它 N — 和拓扑结构的工作簿的相关性树允许这样的总重新计算时间可以降低为达到 1/N 的单线程的计算时间。 这可能是 true 甚至其中 （在其运行工作簿） 的客户端计算机仅具有一个处理器，尤其是其中进行呼叫的服务器所需的时间是相对于服务器处理呼叫的时间小型时。 
  
没有操作系统的每个其他线程的开销。 因此一些实验可能需要的给定的工作簿和给定的服务器和客户端计算机以查找最佳应告知 Excel 要使用的线程数。 
  
例如，假设运行 Excel 和包含 1,000 单元格的工作簿的单处理器计算机。 它调用 UDF，后者又调用一个或多个远程服务器。 假定的 1,000 单元格执行不依赖于每个其他，因此不需要等待一次调用，以调用下一步之前完成的 Excel。 （此限制某些宽松。 可能不会影响此示例）如果服务器可同时处理 100 个请求，Excel 配置为使用 100 个线程执行时间可以降低到降至 1/100th 的因为只有一个线程使用。 与 Excel 分配对每个线程和管理 100 个线程的操作系统的调用开销即关联意味着，实际上，减少不将这非常重要。 另外，还有隐式假设此处的服务器可进行扩展，并要求它同时处理 100 个任务不会影响单个任务的完成时间显著。
  
Monte-carlo 方法，以及可以拆分为较小的子任务可以分配到服务器的其他数值密集型任务的一个实践的应用程序在其中这种技术可以具有重要的好处。
  
## <a name="excel-services-considerations"></a>Excel Services 注意事项
<a name="xl2007xllsdk_threadsafe"> </a>

Excel Services 支持加载、 计算，并呈现的服务器上的 Excel 电子表格。 用户可以然后访问和使用标准的浏览器工具与电子表格交互。
  
Excel Services Udf 创建使用 Microsoft.NET Framework 托管代码和可用但.NET 程序集。 Excel Services 不支持 xll （英文）。 托管的代码服务器 UDF 资源调入可以访问其功能，XLL，以便用户可以与客户端加载工作簿中具有相同的功能与服务器加载工作簿。
  
若要使 XLL 函数可使用此方法，它们必须因此包装在.NET 程序集中的参数和返回值将从转换的本机数据类型为.NET Framework 托管数据类型，并调用 XLL 函数。 .NET 包装将导出正在访问每个 XLL 函数的一台的服务器 UDF。 额外的要求是必须线程安全运行这种方式调用任何 XLL 函数。 XLL 函数未注册的方式与 Excel 客户端的因为服务器和.NET 包装将没有任何办法来强制实施它们线程安全。 它是 XLL 开发人员以确保此的责任。
  
## <a name="see-also"></a>另请参阅

- [Excel 重新计算](excel-recalculation.md)  
- [在 Excel 中进行内存管理](memory-management-in-excel.md) 
- [在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)  
- [Excel Programming Concepts](excel-programming-concepts.md)  
- [Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md)

