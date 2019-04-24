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
# <a name="multithreaded-recalculation-in-excel"></a>Excel 中的多线程重新计算

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Office Excel 2007 是首版对工作表使用多线程重新计算 (MTR) 的 Excel。 可以将 Excel 配置为，在重新计算时最多使用 1024 个并发线程，无论计算机上有多少个处理器或处理器核心。 
  
> [!NOTE]
> 由于会产生与每个线程相关的操作系统开销，因此不得将 Excel 配置为使用超过所需的线程数。 
  
如果计算机有多个处理器或处理器核心，操作系统负责以最高效方式将线程分配给处理器。
  
## <a name="excel-mtr-overview"></a>Excel MTR 概述

Excel 尝试确定可同时在不同线程中重新计算的计算链部分。 下面这个非常简单的示例树（其中，x ← y 表示 y 仅依赖 x）就说明了这一点。
  
**图 1：同时在不同线程中计算**

![同时在不同线程中计算](media/12b5a52b-6308-420c-b6cf-492bd1f195ce.gif "同时在不同线程中计算")
  
在计算 A1 后，便能在一个线程中依次计算 A2 和 A3，同时在另一个线程中依次计算 B1 和 C1（假设所有单元格都是线程安全单元格）。 
  
> [!NOTE]
> “线程安全单元格”一词是指只包含线程安全函数的单元格。 [Excel 视为线程安全和非线程安全的项](#xl2007xllsdk_threadsafe)中详细说明了什么是线程安全项和非线程安全项。 
  
大多数实际工作簿包含的依赖关系树要比上面的示例复杂得多。 此外，只有在计算完成后，才能知道单元格的重新计算时间，此时间长短不一，具体视函数参数而定。 为了获得最佳结果，Excel 在每次计算时都会尝试改进计算顺序，直到没有进一步优化空间为止。
  
Excel 使用一个主线程来运行或执行以下内容：
  
- 内置命令
    
- XLL 命令
    
- XLL 加载项管理器接口函数（**xlAutoOpen** 函数等） 
    
- Microsoft Visual Basic for Applications (VBA) 用户定义命令（通常称为“宏”）
    
- VBA 用户定义函数
    
- 内置非线程安全工作表函数（见下一部分中的列表）
    
- XLM 宏工作表用户定义命令和函数
    
- COM 加载项命令和函数
    
- 条件格式表达式中的函数和运算符
    
- 工作表公式中使用的已定义名称定义中的函数和运算符
    
- 使用 **F9** 键强制计算公式编辑框中的表达式 
    
除非 Excel 被配置为使用多线程，否则所有工作表公式（无论函数是否是线程安全函数）都是在主线程中进行计算。 如果用户指定应使用多线程，其他线程用于线程安全单元格。 请注意，如果从负载均衡角度来看是有意义的，主线程仍用于线程安全单元格。
  
值得重申的是，Excel 一次只运行一个命令，因此无需采用在编写线程安全函数时所采用的相同防范措施，如使用线程本地内存和关键部分。
  
## <a name="what-is-and-is-not-considered-thread-safe-by-excel"></a>Excel 视为安全线程和非安全线程的项
<a name="xl2007xllsdk_threadsafe"> </a>

Excel 仅将以下项视为线程安全项：
  
- Excel 中的所有一元运算符和二元运算符。
    
- 自 Excel 2007 起引入的几乎所有内置工作表函数（见例外列表）
    
- 已显式注册为线程安全的 XLL 加载项函数。
    
内置非线程安全工作表函数包括：
  
- **PHONETIC**
    
- **CELL**（如果使用的是“format”或“address”参数） 
    
- **INDIRECT**
    
- **GETPIVOTDATA**
    
- **CUBEMEMBER**
    
- **CUBEVALUE**
    
- **CUBEMEMBERPROPERTY**
    
- **CUBESET**
    
- **CUBERANKEDMEMBER**
    
- **CUBEKPIMEMBER**
    
- **CUBESETCOUNT**
    
- **ADDRESS**（其中第五个参数 (sheet_name) 已给定） 
    
- 任何引用数据透视表的数据库函数（**DSUM**、**DAVERAGE** 等）
    
- **ERROR.TYPE**
    
- **HYPERLINK**
    
具体而言，以下项被视为非安全线程项：
  
- VBA 用户定义函数
    
- COM 加载项用户定义函数
    
- XLM 宏工作表用户定义函数
    
- 未显式注册为线程安全的 XLL 加载项函数
    
潜在影响是，以下操作和函数是非线程安全，无法从注册为线程安全的 XLL 函数中调用它们：
  
- 调用 XLM 信息函数，例如，**xlfGetCell** (**GET.CELL**)。
    
- 调用 **xlfSetName** (**SET.NAME**)，以定义或删除 XLL 内部名称。
    
- 使用 **xlUDF** 调用非线程安全的用户定义函数。
    
- 对包含非线程安全函数或包含定义内有非线程安全函数的已定义名称的表达式调用 [xlfEvaluate](xlfevaluate.md) 函数。 
    
- 调用 [xlAbort](xlabort.md) 函数，以清除中断条件。 
    
- 调用 [xlCoerce](xlcoerce.md) 函数，以获取未计算单元格引用的值。 
    
> [!NOTE]
> XLL 工作表函数不得调用 C API 命令（例如，**xlcSave**），无论是否已注册为线程安全。 
  
假设声明为线程安全的 XLL 函数无法调用 XLM 信息函数或引用未计算单元格，Excel 不允许注册为宏工作表等效项的 XLL 函数也注册为线程安全。 因此，无法尝试使用 **xlCoerce** 获取未计算单元格引用的值，并看到 **xlretUncalced** 错误。 也无法调用 XLM 信息函数，并看到 **xlretFailed** 错误。 上面列出的其他点也会失败，并看到 Excel C API 中引入的错误代码：**xlretNotThreadSafe**。 
  
所有仅限 C API 的回调函数都是线程安全函数：
  
- **xlCoerce**（但例外是无法强制转换未计算单元格引用） 
    
- **xlFree**
    
- **xlStack**
    
- **xlSheetId**
    
- **xlSheetNm**
    
- **xlAbort**（用于清除中断条件时例外） 
    
- **xlGetInst**
    
- **xlGetHwnd**
    
- **xlGetBinaryName**
    
- **xlDefineBinaryName**
    
有一种例外情况是 **xlSet** 函数，在任何情况下，它都是命令等效项，因此无法从任何工作表函数中进行调用。 
  
可使用 Excel 将 XLL 工作表函数注册为线程安全。 这会指示 Excel 可以在多线程中安全地同步调用函数，尽管必须确保情况的确如此。 如果注册为线程安全的函数之后的行为不安全，可能会破坏 Excel 的稳定性。
  
## <a name="registering-xll-functions-as-thread-safe"></a>将 XLL 函数注册为线程安全
<a name="xl2007xllsdk_threadsafe"> </a>

编写线程安全函数时，开发人员必须遵守如下规则：
  
- 不要在可能是非线程安全的其他 DLL 中调用资源。
    
- 不要通过 C API 或 COM 执行任何非线程安全调用。
    
- 使用关键部分来保护多线程可能同时使用的资源。
    
- 对线程专用存储使用线程本地内存，并将函数中的静态变量替换为线程本地变量。
    
Excel 施加了以下额外限制：不能将线程安全函数注册为宏工作表等效项，因此既无法调用 XLM 信息函数，也无法获取未重新计算单元格的值。
  
## <a name="memory-contention"></a>内存争用
<a name="xl2007xllsdk_threadsafe"> </a>

多线程系统必须解决以下两个基本问题：
  
- 如何保护必须供多线程读取或写入的内存。
    
- 如何创建和访问与执行线程关联（所以也是专用）的内存。
    
Windows 操作系统和 Windows 软件开发工具包 (SDK) 提供了可解决这两个问题的工具：分别是关键部分和线程本地存储 (TLS) API。 有关详细信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。
  
可能会出现第一个问题的情况包括，例如当两个工作表函数（或同一函数的两个同时运行实例）需要访问或修改 DLL 项目中的全局变量时。 请注意，此类全局变量可能会隐藏在类对象的全局可访问实例中。
  
可能会出现第二个问题的情况包括，例如当工作表函数在函数体代码中声明静态变量或对象时。 C/C++ 编译器仅创建所有线程都使用的一个副本。 也就是说，函数的一个实例可能会更改值，而其他线程中的另一个实例可能会假定值是之前设置的。
  
## <a name="example-applications-of-mtr"></a>MTR 应用示例
<a name="xl2007xllsdk_threadsafe"> </a>

所有导出工作表函数的 XLL 都可以利用 Excel 中的多线程重新计算 (MTR)，前提是这些函数无需执行非线程安全操作。 这样一来，Excel 能够尽快重新计算依赖它们的工作簿，因此适用于任何应用场景。
  
具体而言，MTR 对调用用户定义函数 (UDF) 的工作簿的重新计算时间有重大影响，这些函数本身调用外部进程来获取理想结果。 尤其是，假设 UDF 调用可同时处理多个请求的远程服务器，且工作簿包含对相应函数的多个调用。 如果工作簿重新计算是单线程，那么必须先完成对 UDF 和远程服务器的每次调用，然后才能执行下一个调用。 这就浪费了服务器一次处理多个调用的功能。 如果工作簿重新计算是多线程，Excel 就可以同时或快速连续地执行多个调用。
  
如果 Excel 配置为使用与服务器相同的线程数（称之为 N），且工作簿的依赖关系树拓扑允许此配置，那么总重新计算时间可能会大约缩短为单线程计算时间的 1/N。 即使（运行工作簿的）客户端计算机只有一个处理器，可能也是这样，尤其是当调用服务器所花费的时间相对于服务器处理调用所花费的时间较短时。 
  
每个额外线程都会产生操作系统开销。 因此，可能必须对给定工作簿、给定服务器和客户端计算机进行某试验，以确定应指示 Excel 使用的最佳线程数。 
  
例如，假设正在运行 Excel 的是单处理器计算机，且工作簿包含 1,000 个单元格。 它会调用 UDF，进而调用一个或多个远程服务器。 假定这 1,000 个单元格不相互依赖，因此 Excel 无需等到一个调用完成后再执行下一个调用。 （此约束可以有所放宽，而不影响此示例。）如果服务器可以同时处理 100 个请求，且 Excel 配置为使用 100 个线程，那么执行时间可以缩短为仅单线程执行时间的 1/100。 与向每个线程分配调用的 Excel 和管理 100 个线程的操作系统相关的开销表明实际时间缩短不会如此明显。 这其中还有一个隐含假定，即服务器可以很好地缩放，且让它同时处理 100 个任务不会显著影响各个任务完成时间。
  
这项技术可能会带来重要优势的一个实际应用是，可以将 Monte-Carlo 方法和其他数字密集型任务拆分为更小的子任务，从而能够在服务器中进行场化。
  
## <a name="excel-services-considerations"></a>Excel Services 注意事项
<a name="xl2007xllsdk_threadsafe"> </a>

Excel Services 支持在服务器上加载、计算和呈现 Excel 电子表格。 然后，用户可使用标准浏览器工具来访问电子表格并与之交互。
  
Excel Services UDF 是使用 Microsoft .NET Framework 托管代码创建而成，可通过 .NET 程序集使用。 Excel Services 不支持 XLL。 托管代码服务器 UDF 资源可以调用 XLL 来使用它的功能，这样用户可以在使用服务器加载的工作簿和客户端加载的工作簿时使用相同功能。
  
若要让 XLL 函数以这种方式可用，必须将它们包装在 .NET 程序集中，此程序集将参数和本机数据类型中的返回值转换为 .NET Framework 托管数据类型，并调用 XLL 函数。 .NET 包装器会为访问的每个 XLL 函数导出一个服务器 UDF。 附加要求是，这样调用的所有 XLL 函数都必须是线程安全函数。 由于 XLL 函数并非像在客户端 Excel 中一样注册，因此服务器和 .NET 包装器无法强制执行它们必须是线程安全函数的要求。 XLL 开发人员有责任确保这一点。
  
## <a name="see-also"></a>另请参阅

- [Excel 重新计算](excel-recalculation.md)  
- [Excel 中的内存管理](memory-management-in-excel.md) 
- [在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)  
- [Excel 编程概念](excel-programming-concepts.md)  
- [Excel XLL SDK API 函数引用](excel-xll-sdk-api-function-reference.md)

