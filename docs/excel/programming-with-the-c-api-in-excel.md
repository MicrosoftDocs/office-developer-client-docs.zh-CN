---
title: 在 Excel 中使用 C API 进行编程
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- c api [excel 2007],programming interfaces [Excel 2007],C API [Excel 2007], when to use,C API [Excel 2007], relation to XLM,Excel programming interfaces
localization_priority: Normal
ms.assetid: 142bc0ce-7d16-4b69-9799-ce6558da2def
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 459e57d41ef7497c535e51944bbaf24daee84167
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773808"
---
# <a name="programming-with-the-c-api-in-excel"></a>在 Excel 中使用 C API 进行编程

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
可以使用 Microsoft Excel 2013 XLL 软件开发工具包和 C API 为 Excel 2013 创建高性能工作表函数。升级到 Excel 2013 C API 反映了对于第三方或内部功能的性能对其至关重要的用户的持续支持。
  
## <a name="excel-programming-interfaces"></a>Excel 编程接口

Excel 提供了多个用于开发交互应用程序的选项。早期版本中按以下顺序添加了 Excel 编程接口：
  
- **XLM 宏语言：** 用于 Excel 扩展和 C API 基础的第一种用户可访问语言。尽管在 Excel 2010 中仍受支持，XLM 早就被 Visual Basic for Applications (VBA) 所取代。 
    
- **C API 和 XLL：** DLL 与 Excel 集成。这些 DLL 提供了用于添加高性能工作表功能最直接、最快速的接口，尽管与更新技术相比要更复杂。 
    
- **VBA：** 与 Excel 工作簿对象关联的 Visual Basic 代码对象。VBA 允许对用户定义的函数和命令进行事件捕获、自定义和添加。VBA 是最常用且最易于使用的扩展性选项。 
    
- **COM：** 基于 Windows 的应用程序的互操作性标准，Excel 通过此标准公开其事件和对象。VBA 使用 COM 与 Excel 交互。Excel 导出 COM 类型库，可帮助你创建可在外部控制 Excel 的 C++ COM 代码资源和应用程序。 
    
- **Microsoft .NET Framework：** 设计为用于分布式环境的快速应用程序开发的多语言托管代码环境。基于 .NET Framework 的代码主编程语言是 C#，尽管很多语言都可以编译为 Microsoft 中间语言 (MSIL)。Excel 2013 可以访问 .NET Framework 程序集中包含的代码资源。 
    
## <a name="when-to-use-the-c-api"></a>何时使用 C API

编写 XLL 和使用 C API 的首要原因是创建高性能的工作表函数。尽管 XLL 函数通常称为用户定义函数，但要编写 XLL 需要投入大量时间对其进行了解并获得相关技能，使得该技术对大多数用户都不实用。尽管如此，通过应用高性能函数，且在 Excel 2013 中可以为强大的服务器资源编写多线程接口，使之成为 Excel 扩展性非常重要的一部分。 
  
Excel 2007 中引入的 C API 修订主要涉及与高性能计算相关的方面，而不是用户界面等功能。
  
### <a name="writing-high-performance-user-defined-worksheet-functions"></a>编写用户定义的高性能工作表函数

如果需要通过创建 XLL 加载项来创建高性能工作表，Excel C API 是理想选择。C API 为你提供对工作表数据最直接的访问。XLL 为 Excel 提供对 DLL 资源最直接的访问。通过增加新数据类型，最重要的是，通过支持在群集服务器上运行用户定义的函数，XLL 的性能在 Excel 2013 中得到进一步增强。
  
使用 XLL 有一定的成本：C API 没有 VBA、COM 或 .NET Framework 的更高级别的快速开发功能。内存管理为较低级别，因此对开发人员的职责要求更高。通过 COM 公开的很多 Excel 功能通过 VBA 和 .NET Framework 发布，不会向 C API 公开。
  
### <a name="accessing-multithreaded-servers-by-using-xll-worksheet-functions"></a>使用 XLL 工作表函数访问多线程服务器

多线程重新计算 (MTR) 在 Excel 2007 中引入，使您可以创建线程安全的 XLL 工作表函数。您可以使用这些函数访问多线程服务器。后面几节更详细地介绍如何动态提高用户观察到的性能。对于有时需要使用大量处理能力的 Excel 用户，使用 MTR 和强大计算服务器的 XLL 组合可提供性能最高的解决方案。
  
### <a name="customizing-the-excel-user-interface"></a>自定义 Excel 用户界面

对于 Excel 的很多版本，C API 还不是自定义用户界面的最佳选择。VBA 对 Excel 对象和事件具有优先访问权。Excel 2007 中引入的用户界面在外观和基础技术方面都与之前版本相差很大。您可以使用托管代码资源更好地自定义此界面。
  
### <a name="creating-applications-that-can-be-accessed-on-the-internet"></a>创建可在 Internet 上访问的应用程序

随 2007 Microsoft Office 系统引入的 Excel Services 通过标准 Web 浏览器工具，为用户提供了访问工作簿和 Excel 功能的最佳方式。这些技术与 .NET Framework 开发语言和资源一起，成为未来对用户进行 Excel 部署的一个重要部分。
  
### <a name="controlling-excel-from-external-applications"></a>从外部应用程序控制 Excel

Excel 通过 COM 界面公开其对象、方法和事件。因此，您可以使用 COM 创建独立应用程序，这些应用程序可以启动并控制 Excel 会话或者控制现有的 Excel 会话。您可以在多种开发语言（包括 C++ 和 VBA）中访问 COM 公开的 Excel 界面。与此类似，C# 和 .NET Framework 也提供 Excel 界面以启用对 Excel 的远程访问和控制。
  
## <a name="asynchronous-calling-of-excel"></a>异步调用 Excel

仅当将控制权移交给 XLL 时，Excel 才允许 XLL 调用 C API。Excel 调用的工作表函数可以使用 C API 回调到 Excel。Excel 调用的 XLL 命令可以调用 C API。当 VBA 本身被 Excel 调用时调用的 DLL 和 XLL 函数与功能可以调用 C API。例如，您无法设置对 XLL 的计时 Windows 回调并从其调用 C API，并且您无法从您的 XLL 创建的后台线程调用 C API。不建议从 DLL 或 XLL 使用 COM 异步调用 Excel。
  
因为在有些应用程序中您可能希望 Excel 对事件做出异步响应，因此这存在很大限制。例如，您可能希望 Excel 在 Internet 上检索数据并重新计算数据何时变更。或者您可能希望后台线程执行计算并让 Excel 重新计算其何时完成。
  
您可以通过让 Excel 积极轮询变更实现此操作，但这样做效率很低且会受限制，因为 Excel 会频繁中断常规活动。您可以使用 C API 或 VBA 设置重复的计时命令，尽管这并非理想的解决方案。
  
理想情况下，您可能需要一个更有效的外部过程来检查数据变更，并使该外部过程触发 Excel 以检索更新并执行重新计算。您可以通过一个使用 COM 与 Excel 进行交互的应用程序来实现此操作。COM 不会受到与 C API 相同的限制，即仅当 Excel 向其明确传递控制权时才能发出调用。只要 Excel 处于就绪状态，COM 应用程序就能调用 Excel 方法，尽管当显示对话框、拉下菜单或执行宏时这些方法调用可能会被忽略。
  
## <a name="c-api-and-its-relation-to-xlm"></a>C API 及其与 XLM 的关系

Excel 宏 (XLM) 语言是 Excel 中提供的第一个用户可访问的编程环境。它使用户能够在与常规工作表类似的特殊宏表上创建自定义命令和函数。XLM 宏表在 Excel 2013 中仍受支持。除了无法在工作表上输入的以下项目外，还可以在宏表上使用所有常见的工作表函数，例如 **SUM** 和 **LOG**： 
  
- 工作区信息函数，例如 **GET.CELL** 和 **GET.WORKBOOK**。
    
- 启用常规用户操作自动化的命令等效函数，如 **DEFINE.NAME** 和 **PASTE**。
    
- 与加载项相关的函数，如 **REGISTER**。
    
- 命令等效事件陷阱，如 **ON.ENRTY** 和 **ON.TIME**。
    
- 宏函数特定的操作，如 **ARGUMENT** 和 **VOLATILE**。
    
- 流控制操作，如 **GOTO** 和 **RETURN**。
    
Excel 版本 3 中存在 C API 的限制版本。但是，在 Excel 版本 4 中，XLM 语言映射到了 C API。此后，DLL 已经能够调用所有工作表函数、宏表信息函数和命令，并且能够设置事件陷阱。DLL 无法从 C API 中调用 XLM 流控制函数。这些宏表函数和命令记录在帮助文件 XLMacr8.hlp（以前名为 Macrofun.hlp）中。要获取此帮助文件，请转到 [Microsoft 下载中心](http://download.microsoft.com)并搜索“XLMacr8.hlp”。 
  
> [!NOTE]
> Windows Vista 和 Windows 7 不会直接支持 .hlp 文件，但可以从 Microsoft 下载[适用于 Windows Vista 的 Windows 帮助程序 (WinHlp32.exe)](http://go.microsoft.com/fwlink/?LinkID=82148) 或[适用于 Windows 7 的 Windows 帮助程序 (WinHlp32.exe)](http://www.microsoft.com/download/en/details.aspx?id=91)，并将其从中打开。 
  
DLL 使用回调函数 **Excel4**、**Excel4v**、**Excel12** 和 **Excel12v**（后两个在 Excel 2007 中引入）调用这些函数和命令的 C API 等效项。与每个函数和命令对应的枚举常量在头文件中定义，并作为一个参数传递到这些回调。例如，**GET.CELL** 由 **xlfGetCell** 表示、**REGISTER** 由 **xlfRegister** 表示、**DEFINE.NAME** 由 **xlcDefineName** 表示。
  
除提供工作表函数和宏表函数与命令外，C API 还提供只能从 DLL 中使用这些回调进行调用的函数和命令枚举。例如，**xlGetName** 使 DLL 能够查明自己的完整路径和文件名，在 Excel 中注册函数和命令时需要此信息。 
  
在 Excel 版本 5 中引入 Visual Basic for Applications (VBA) 表，在版本 8 (Excel 97) 中引入 Visual Basic Editor (VBE) 后，用户自定义 Excel 最简单的方式就是使用 VBA，而非 XLM。因此，Excel 更高版本中引入的很多新功能均通过 VBA 提供，但不通过 XLM 或 C API 提供。例如，多个命令、事件陷阱和增强对话框功能均通过 VBA 提供，但不通过 XLM 或 C API 提供。
  
有关详细信息，请参阅[适用于 Excel 的 C API 中的新增功能](what-s-new-in-the-c-api-for-excel.md)。
  
## <a name="see-also"></a>另请参阅



[适用于 Excel 的 C API 中的新增功能](what-s-new-in-the-c-api-for-excel.md)
  
[C API 回调函数 Excel4、Excel12](c-api-callback-functions-excel4-excel12.md)


[Excel XLL SDK 入门](getting-started-with-the-excel-xll-sdk.md)

