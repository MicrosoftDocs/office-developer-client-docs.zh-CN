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
# <a name="programming-with-the-c-api-in-excel"></a><span data-ttu-id="b3135-104">在 Excel 中使用 C API 进行编程</span><span class="sxs-lookup"><span data-stu-id="b3135-104">Programming with the C API in Excel</span></span>

 <span data-ttu-id="b3135-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b3135-105">Applies to: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b3135-p101">可以使用 Microsoft Excel 2013 XLL 软件开发工具包和 C API 为 Excel 2013 创建高性能工作表函数。升级到 Excel 2013 C API 反映了对于第三方或内部功能的性能对其至关重要的用户的持续支持。</span><span class="sxs-lookup"><span data-stu-id="b3135-p101">You can use the Microsoft Excel 2013 XLL Software Development Kit and the C API to create high-performance worksheet functions for Excel 2013. The upgrades to the Excel 2013 C API reflect ongoing support for users for whom the performance of third-party or in-house functionality is critical.</span></span>
  
## <a name="excel-programming-interfaces"></a><span data-ttu-id="b3135-108">Excel 编程接口</span><span class="sxs-lookup"><span data-stu-id="b3135-108">Excel Programming Interfaces</span></span>

<span data-ttu-id="b3135-p102">Excel 提供了多个用于开发交互应用程序的选项。早期版本中按以下顺序添加了 Excel 编程接口：</span><span class="sxs-lookup"><span data-stu-id="b3135-p102">Excel provides several options for developing applications that interface with it. The Excel programming interfaces were added to earlier versions in the following order:</span></span>
  
- <span data-ttu-id="b3135-p103">**XLM 宏语言：** 用于 Excel 扩展和 C API 基础的第一种用户可访问语言。尽管在 Excel 2010 中仍受支持，XLM 早就被 Visual Basic for Applications (VBA) 所取代。</span><span class="sxs-lookup"><span data-stu-id="b3135-p103">**XLM macro language:** The first user-accessible language for the extension of Excel and the basis of the C API. Although still supported in Excel 2010, XLM has long been superseded by Visual Basic for Applications (VBA).</span></span> 
    
- <span data-ttu-id="b3135-p104">**C API 和 XLL：** DLL 与 Excel 集成。这些 DLL 提供了用于添加高性能工作表功能最直接、最快速的接口，尽管与更新技术相比要更复杂。</span><span class="sxs-lookup"><span data-stu-id="b3135-p104">**C API and XLLs:** DLLs that are integrated with Excel. These DLLs provide the most direct and fastest interface for the addition of high-performance worksheet functions, although at the cost of some complexity compared with later technologies.</span></span> 
    
- <span data-ttu-id="b3135-p105">**VBA：** 与 Excel 工作簿对象关联的 Visual Basic 代码对象。VBA 允许对用户定义的函数和命令进行事件捕获、自定义和添加。VBA 是最常用且最易于使用的扩展性选项。</span><span class="sxs-lookup"><span data-stu-id="b3135-p105">**VBA:** Visual Basic code objects that are associated with Excel workbook objects. VBA allows event trapping, customization, and the addition of user-defined functions and commands. VBA is the most commonly used and most easily available of the extensibility options.</span></span> 
    
- <span data-ttu-id="b3135-p106">**COM：** 基于 Windows 的应用程序的互操作性标准，Excel 通过此标准公开其事件和对象。VBA 使用 COM 与 Excel 交互。Excel 导出 COM 类型库，可帮助你创建可在外部控制 Excel 的 C++ COM 代码资源和应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3135-p106">**COM:** The interoperability standard for Windows-based applications, through which Excel exposes its events and objects. VBA uses COM to interact with Excel. Excel exports COM type libraries that can help you create C++ COM code resources and applications that can control Excel externally.</span></span> 
    
- <span data-ttu-id="b3135-p107">**Microsoft .NET Framework：** 设计为用于分布式环境的快速应用程序开发的多语言托管代码环境。基于 .NET Framework 的代码主编程语言是 C#，尽管很多语言都可以编译为 Microsoft 中间语言 (MSIL)。Excel 2013 可以访问 .NET Framework 程序集中包含的代码资源。</span><span class="sxs-lookup"><span data-stu-id="b3135-p107">**The Microsoft .NET Framework:** The multi-language managed code environment designed for rapid application development for distributed environments. The primary programming language for code that is based on the .NET Framework is C#, although many languages can be compiled to the Microsoft intermediate language (MSIL). Excel 2013 can access code resources contained within .NET Framework assemblies.</span></span> 
    
## <a name="when-to-use-the-c-api"></a><span data-ttu-id="b3135-124">何时使用 C API</span><span class="sxs-lookup"><span data-stu-id="b3135-124">When to Use the C API</span></span>

<span data-ttu-id="b3135-p108">编写 XLL 和使用 C API 的首要原因是创建高性能的工作表函数。尽管 XLL 函数通常称为用户定义函数，但要编写 XLL 需要投入大量时间对其进行了解并获得相关技能，使得该技术对大多数用户都不实用。尽管如此，通过应用高性能函数，且在 Excel 2013 中可以为强大的服务器资源编写多线程接口，使之成为 Excel 扩展性非常重要的一部分。</span><span class="sxs-lookup"><span data-stu-id="b3135-p108">The primary reason for writing XLLs and using the C API is to create high-performance worksheet functions. Although XLL functions are frequently referred to as user-defined functions, the investment in time to obtain the understanding and skills that are required to write XLLs make this a technology impractical for most users. Nevertheless, the applications of high-performance functions—and, in Excel 2013, the ability to write multithreaded interfaces to powerful server resources—make this a very important part of Excel extensibility.</span></span> 
  
<span data-ttu-id="b3135-128">Excel 2007 中引入的 C API 修订主要涉及与高性能计算相关的方面，而不是用户界面等功能。</span><span class="sxs-lookup"><span data-stu-id="b3135-128">The revision of the C API that was introduced in Excel 2007 is mainly concerned with the aspects relating to high-performance calculations, rather than features such as the user interface.</span></span>
  
### <a name="writing-high-performance-user-defined-worksheet-functions"></a><span data-ttu-id="b3135-129">编写用户定义的高性能工作表函数</span><span class="sxs-lookup"><span data-stu-id="b3135-129">Writing High-Performance User-Defined Worksheet Functions</span></span>

<span data-ttu-id="b3135-p109">如果需要通过创建 XLL 加载项来创建高性能工作表，Excel C API 是理想选择。C API 为你提供对工作表数据最直接的访问。XLL 为 Excel 提供对 DLL 资源最直接的访问。通过增加新数据类型，最重要的是，通过支持在群集服务器上运行用户定义的函数，XLL 的性能在 Excel 2013 中得到进一步增强。</span><span class="sxs-lookup"><span data-stu-id="b3135-p109">The Excel C API is the ideal choice when you want to create high-performance worksheet functions by creating XLL add-ins. The C API provides you with the most direct access to worksheet data. XLLs provide Excel with the most direct access to the DLL resources. The performance of XLLs is further enhanced in Excel 2013 by the addition of new data types and, most importantly, support for running user-defined functions on clustered servers.</span></span>
  
<span data-ttu-id="b3135-p110">使用 XLL 有一定的成本：C API 没有 VBA、COM 或 .NET Framework 的更高级别的快速开发功能。内存管理为较低级别，因此对开发人员的职责要求更高。通过 COM 公开的很多 Excel 功能通过 VBA 和 .NET Framework 发布，不会向 C API 公开。</span><span class="sxs-lookup"><span data-stu-id="b3135-p110">Working with XLLs comes at a cost: The C API has none of the higher-level rapid development features of VBA, COM, or the .NET Framework. Memory management is low level and, therefore, puts greater responsibility on the developer. Many Excel features that are exposed via COM, making them available through VBA and the .NET Framework, are not exposed to the C API.</span></span>
  
### <a name="accessing-multithreaded-servers-by-using-xll-worksheet-functions"></a><span data-ttu-id="b3135-136">使用 XLL 工作表函数访问多线程服务器</span><span class="sxs-lookup"><span data-stu-id="b3135-136">Accessing Multithreaded Servers by Using XLL Worksheet Functions</span></span>

<span data-ttu-id="b3135-p111">多线程重新计算 (MTR) 在 Excel 2007 中引入，使您可以创建线程安全的 XLL 工作表函数。您可以使用这些函数访问多线程服务器。后面几节更详细地介绍如何动态提高用户观察到的性能。对于有时需要使用大量处理能力的 Excel 用户，使用 MTR 和强大计算服务器的 XLL 组合可提供性能最高的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3135-p111">Multithreaded recalculation (MTR), which was introduced in Excel 2007, enables you to create thread-safe XLL worksheet functions. You can use these functions to access multithreaded servers. Later sections describe more fully how this can dramatically increase the performance observed by the user. For Excel users who sometimes need access to a lot of processing power, the combination of an XLL that uses MTR and a powerful calculation server provides the highest-performance solution.</span></span>
  
### <a name="customizing-the-excel-user-interface"></a><span data-ttu-id="b3135-141">自定义 Excel 用户界面</span><span class="sxs-lookup"><span data-stu-id="b3135-141">Customizing the Excel User Interface</span></span>

<span data-ttu-id="b3135-p112">对于 Excel 的很多版本，C API 还不是自定义用户界面的最佳选择。VBA 对 Excel 对象和事件具有优先访问权。Excel 2007 中引入的用户界面在外观和基础技术方面都与之前版本相差很大。您可以使用托管代码资源更好地自定义此界面。</span><span class="sxs-lookup"><span data-stu-id="b3135-p112">For many versions of Excel, the C API has not been the best choice for customizing the user interface. VBA has superior access to Excel objects and events. The user interface introduced in Excel 2007 is significantly different from earlier versions both in appearance and underlying technology. You can best customize this interface by using managed code resources.</span></span>
  
### <a name="creating-applications-that-can-be-accessed-on-the-internet"></a><span data-ttu-id="b3135-146">创建可在 Internet 上访问的应用程序</span><span class="sxs-lookup"><span data-stu-id="b3135-146">Creating Applications that Can Be Accessed on the Internet</span></span>

<span data-ttu-id="b3135-p113">随 2007 Microsoft Office 系统引入的 Excel Services 通过标准 Web 浏览器工具，为用户提供了访问工作簿和 Excel 功能的最佳方式。这些技术与 .NET Framework 开发语言和资源一起，成为未来对用户进行 Excel 部署的一个重要部分。</span><span class="sxs-lookup"><span data-stu-id="b3135-p113">Excel Services, introduced with the 2007 Microsoft Office system, provides the best way to give users access to workbooks and Excel functionality by using standard Web browser tools. Together with .NET Framework development languages and resources, these technologies represent an important part of Excel deployment to users in the future.</span></span>
  
### <a name="controlling-excel-from-external-applications"></a><span data-ttu-id="b3135-149">从外部应用程序控制 Excel</span><span class="sxs-lookup"><span data-stu-id="b3135-149">Controlling Excel from External Applications</span></span>

<span data-ttu-id="b3135-p114">Excel 通过 COM 界面公开其对象、方法和事件。因此，您可以使用 COM 创建独立应用程序，这些应用程序可以启动并控制 Excel 会话或者控制现有的 Excel 会话。您可以在多种开发语言（包括 C++ 和 VBA）中访问 COM 公开的 Excel 界面。与此类似，C# 和 .NET Framework 也提供 Excel 界面以启用对 Excel 的远程访问和控制。</span><span class="sxs-lookup"><span data-stu-id="b3135-p114">Excel exposes its objects, methods, and events through the COM interface. You can, therefore, use COM to create stand-alone applications that can start and control an Excel session or control an existing Excel session. You can access the COM-exposed Excel interface within several development languages, including C++ and VBA. C# and the .NET Framework similarly provide an interface to Excel that enables remote access to and control of Excel.</span></span>
  
## <a name="asynchronous-calling-of-excel"></a><span data-ttu-id="b3135-154">异步调用 Excel</span><span class="sxs-lookup"><span data-stu-id="b3135-154">Asynchronous Calling of Excel</span></span>

<span data-ttu-id="b3135-p115">仅当将控制权移交给 XLL 时，Excel 才允许 XLL 调用 C API。Excel 调用的工作表函数可以使用 C API 回调到 Excel。Excel 调用的 XLL 命令可以调用 C API。当 VBA 本身被 Excel 调用时调用的 DLL 和 XLL 函数与功能可以调用 C API。例如，您无法设置对 XLL 的计时 Windows 回调并从其调用 C API，并且您无法从您的 XLL 创建的后台线程调用 C API。不建议从 DLL 或 XLL 使用 COM 异步调用 Excel。</span><span class="sxs-lookup"><span data-stu-id="b3135-p115">Excel allows XLLs to call the C API only when Excel has passed control to the XLL. A worksheet function that is called by Excel can call back into Excel by using the C API. An XLL command that is called by Excel can call the C API. DLL and XLL functions and commands that are called by VBA when VBA has itself been called by Excel can call the C API. You cannot, for example, set a timed Windows callback into your XLL and call the C API from it, and you cannot call the C API from a background thread created by your XLL. Calling Excel asynchronously by using COM from a DLL or XLL is not recommended.</span></span>
  
<span data-ttu-id="b3135-p116">因为在有些应用程序中您可能希望 Excel 对事件做出异步响应，因此这存在很大限制。例如，您可能希望 Excel 在 Internet 上检索数据并重新计算数据何时变更。或者您可能希望后台线程执行计算并让 Excel 重新计算其何时完成。</span><span class="sxs-lookup"><span data-stu-id="b3135-p116">This is very limiting because there may be applications in which you want Excel to react to an event asynchronously. For example, you might want Excel to retrieve a piece of data on the Internet and recalculate whenever that data changes. Or you might want a background thread to perform a calculation and have Excel recalculate when it is finished.</span></span>
  
<span data-ttu-id="b3135-p117">您可以通过让 Excel 积极轮询变更实现此操作，但这样做效率很低且会受限制，因为 Excel 会频繁中断常规活动。您可以使用 C API 或 VBA 设置重复的计时命令，尽管这并非理想的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3135-p117">You can do this by having Excel actively poll for changes, but this is inefficient and limiting because it involves Excel frequently interrupting its regular activity. You can set up repeated timed command using the C API or VBA, although this is not an ideal solution.</span></span>
  
<span data-ttu-id="b3135-p118">理想情况下，您可能需要一个更有效的外部过程来检查数据变更，并使该外部过程触发 Excel 以检索更新并执行重新计算。您可以通过一个使用 COM 与 Excel 进行交互的应用程序来实现此操作。COM 不会受到与 C API 相同的限制，即仅当 Excel 向其明确传递控制权时才能发出调用。只要 Excel 处于就绪状态，COM 应用程序就能调用 Excel 方法，尽管当显示对话框、拉下菜单或执行宏时这些方法调用可能会被忽略。</span><span class="sxs-lookup"><span data-stu-id="b3135-p118">Ideally you would want a more efficient external process to check for the change in data, and for that external process to trigger Excel to retrieve the update and perform a recalculation. You can do this by using an application that interfaces to Excel by using COM. COM is not restricted in the same manner as the C API to making calls only when Excel has explicitly passed it control. COM applications can invoke Excel methods whenever Excel is in a ready state, although these method calls might be ignored if dialog boxes are being displayed, menus are pulled down, or when a macro is executing.</span></span>
  
## <a name="c-api-and-its-relation-to-xlm"></a><span data-ttu-id="b3135-170">C API 及其与 XLM 的关系</span><span class="sxs-lookup"><span data-stu-id="b3135-170">C API and Its Relation to XLM</span></span>

<span data-ttu-id="b3135-p119">Excel 宏 (XLM) 语言是 Excel 中提供的第一个用户可访问的编程环境。它使用户能够在与常规工作表类似的特殊宏表上创建自定义命令和函数。XLM 宏表在 Excel 2013 中仍受支持。除了无法在工作表上输入的以下项目外，还可以在宏表上使用所有常见的工作表函数，例如 **SUM** 和 **LOG**：</span><span class="sxs-lookup"><span data-stu-id="b3135-p119">The Excel macro (XLM) language was the first user-accessible programming environment provided in Excel. It enabled users to create custom commands and functions on special macro sheets that look like ordinary worksheets. XLM macro sheets are still supported in Excel 2013. You can use all the usual worksheet functions like **SUM** and **LOG** on a macro sheet, in addition to the following items that cannot be entered on a worksheet:</span></span> 
  
- <span data-ttu-id="b3135-175">工作区信息函数，例如 **GET.CELL** 和 **GET.WORKBOOK**。</span><span class="sxs-lookup"><span data-stu-id="b3135-175">Workspace information functions such as **GET.CELL** and **GET.WORKBOOK**.</span></span>
    
- <span data-ttu-id="b3135-176">启用常规用户操作自动化的命令等效函数，如 **DEFINE.NAME** 和 **PASTE**。</span><span class="sxs-lookup"><span data-stu-id="b3135-176">Command-equivalent functions that enable automation of ordinary user operations such as **DEFINE.NAME** and **PASTE**.</span></span>
    
- <span data-ttu-id="b3135-177">与加载项相关的函数，如 **REGISTER**。</span><span class="sxs-lookup"><span data-stu-id="b3135-177">Functions that relate to add-ins such as **REGISTER**.</span></span>
    
- <span data-ttu-id="b3135-178">命令等效事件陷阱，如 **ON.ENRTY** 和 **ON.TIME**。</span><span class="sxs-lookup"><span data-stu-id="b3135-178">Command-equivalent event traps such as **ON.ENRTY** and **ON.TIME**.</span></span>
    
- <span data-ttu-id="b3135-179">宏函数特定的操作，如 **ARGUMENT** 和 **VOLATILE**。</span><span class="sxs-lookup"><span data-stu-id="b3135-179">Macro function-specific operations such as **ARGUMENT** and **VOLATILE**.</span></span>
    
- <span data-ttu-id="b3135-180">流控制操作，如 **GOTO** 和 **RETURN**。</span><span class="sxs-lookup"><span data-stu-id="b3135-180">Flow-control operations such as **GOTO** and **RETURN**.</span></span>
    
<span data-ttu-id="b3135-p120">Excel 版本 3 中存在 C API 的限制版本。但是，在 Excel 版本 4 中，XLM 语言映射到了 C API。此后，DLL 已经能够调用所有工作表函数、宏表信息函数和命令，并且能够设置事件陷阱。DLL 无法从 C API 中调用 XLM 流控制函数。这些宏表函数和命令记录在帮助文件 XLMacr8.hlp（以前名为 Macrofun.hlp）中。要获取此帮助文件，请转到 [Microsoft 下载中心](http://download.microsoft.com)并搜索“XLMacr8.hlp”。</span><span class="sxs-lookup"><span data-stu-id="b3135-p120">A limited version of the C API existed in Excel version 3. However, in Excel version 4, the XLM language was mapped to the C API. Since then, DLLs have been able to call all worksheet functions, macro sheet information functions, and commands, and to set event traps. DLLs cannot call XLM flow control functions from within the C API. These macro-sheet functions and commands are documented in the Help file XLMacr8.hlp (formerly named Macrofun.hlp). To obtain this help file, go to the [Microsoft Download Center](http://download.microsoft.com) and search for "XLMacr8.hlp".</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b3135-187">Windows Vista 和 Windows 7 不会直接支持 .hlp 文件，但可以从 Microsoft 下载[适用于 Windows Vista 的 Windows 帮助程序 (WinHlp32.exe)](http://go.microsoft.com/fwlink/?LinkID=82148) 或[适用于 Windows 7 的 Windows 帮助程序 (WinHlp32.exe)](http://www.microsoft.com/download/en/details.aspx?id=91)，并将其从中打开。</span><span class="sxs-lookup"><span data-stu-id="b3135-187">Windows Vista and Windows 7 do not directly support .hlp files, but you can download the [Windows Help program (WinHlp32.exe) for Windows Vista](http://go.microsoft.com/fwlink/?LinkID=82148) or the [Windows Help program (WinHlp32.exe) for Windows 7](http://www.microsoft.com/download/en/details.aspx?id=91) from Microsoft that enables them to be opened.</span></span> 
  
<span data-ttu-id="b3135-p121">DLL 使用回调函数 **Excel4**、**Excel4v**、**Excel12** 和 **Excel12v**（后两个在 Excel 2007 中引入）调用这些函数和命令的 C API 等效项。与每个函数和命令对应的枚举常量在头文件中定义，并作为一个参数传递到这些回调。例如，**GET.CELL** 由 **xlfGetCell** 表示、**REGISTER** 由 **xlfRegister** 表示、**DEFINE.NAME** 由 **xlcDefineName** 表示。</span><span class="sxs-lookup"><span data-stu-id="b3135-p121">DLLs call C API equivalents of these functions and commands by using the callback functions **Excel4**, **Excel4v**, **Excel12**, and **Excel12v** (the last two were introduced in Excel 2007). Enumerated constants that correspond to each function and command are defined in a header file and passed as one of the arguments to these callbacks. For example, **GET.CELL** is represented by **xlfGetCell**, **REGISTER** by **xlfRegister**, and **DEFINE.NAME** by **xlcDefineName**.</span></span>
  
<span data-ttu-id="b3135-p122">除提供工作表函数和宏表函数与命令外，C API 还提供只能从 DLL 中使用这些回调进行调用的函数和命令枚举。例如，**xlGetName** 使 DLL 能够查明自己的完整路径和文件名，在 Excel 中注册函数和命令时需要此信息。</span><span class="sxs-lookup"><span data-stu-id="b3135-p122">In addition to providing the worksheet functions and macro-sheet functions and commands, the C API provides function and command enumerations that can be called only by using these callbacks from within a DLL. For example, **xlGetName** enables the DLL to find out its own the full path and file name, which is required when you register functions and commands with Excel.</span></span> 
  
<span data-ttu-id="b3135-p123">在 Excel 版本 5 中引入 Visual Basic for Applications (VBA) 表，在版本 8 (Excel 97) 中引入 Visual Basic Editor (VBE) 后，用户自定义 Excel 最简单的方式就是使用 VBA，而非 XLM。因此，Excel 更高版本中引入的很多新功能均通过 VBA 提供，但不通过 XLM 或 C API 提供。例如，多个命令、事件陷阱和增强对话框功能均通过 VBA 提供，但不通过 XLM 或 C API 提供。</span><span class="sxs-lookup"><span data-stu-id="b3135-p123">Since the introduction of Visual Basic for Applications (VBA) sheets in Excel version 5, and the Visual Basic Editor (VBE) in version 8 (Excel 97), the easiest way for users to customize Excel is to use VBA instead of XLM. Consequently, much of the new functionality introduced in later versions of Excel is available through VBA, but not through XLM or the C API. For example, several commands, event traps, and enhanced dialog box capabilities are available through VBA, but not through XLM or the C API.</span></span>
  
<span data-ttu-id="b3135-196">有关详细信息，请参阅[适用于 Excel 的 C API 中的新增功能](what-s-new-in-the-c-api-for-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="b3135-196">For more information, see [What's New in the C API for Excel](what-s-new-in-the-c-api-for-excel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b3135-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3135-197">See also</span></span>



[<span data-ttu-id="b3135-198">适用于 Excel 的 C API 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b3135-198">What's New in the C API for Excel</span></span>](what-s-new-in-the-c-api-for-excel.md)
  
[<span data-ttu-id="b3135-199">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="b3135-199">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md)


[<span data-ttu-id="b3135-200">Excel XLL SDK 入门</span><span class="sxs-lookup"><span data-stu-id="b3135-200">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

