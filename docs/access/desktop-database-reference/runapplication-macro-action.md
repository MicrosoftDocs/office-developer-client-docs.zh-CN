---
title: RunApplication 宏操作
TOCTitle: RunApplication macro action
ms:assetid: 29967e6e-c441-b115-3ee6-2299b8a3bc25
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192038(v=office.15)
ms:contentKeyID: 48543885
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm93359
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: e7bf54934c6be215b2be5f32160d74fc2b4ab346
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721785"
---
# <a name="runapplication-macro-action"></a><span data-ttu-id="71cad-102">RunApplication 宏操作</span><span class="sxs-lookup"><span data-stu-id="71cad-102">RunApplication macro action</span></span>

<span data-ttu-id="71cad-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="71cad-103">**Applies to**: Access 2013, Office 2013</span></span>

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="安全说明" alt="Security note" /><span data-ttu-id="71cad-105"><strong>安全注释</strong></span><span class="sxs-lookup"><span data-stu-id="71cad-105"><strong>Security Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="71cad-p101">在运行可执行文件或者宏或应用程序中的代码时，请务必小心。可执行文件或代码所执行的操作可能会损害您的计算机和数据的安全性。</span><span class="sxs-lookup"><span data-stu-id="71cad-p101">Use caution when running executable files or code in macros or applications. Executable files or code can be used to carry out actions that might compromise the security of your computer and data.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="71cad-p102">可以使用 **RunApplication** 操作在 Microsoft Access 内部运行基于 Microsoft Windows 或基于 MS-DOS 的应用程序，例如 Microsoft Excel、Microsoft Word 或 Microsoft PowerPoint。例如，您可能想将 Excel 电子表格数据贴粘到 Access 数据库中。</span><span class="sxs-lookup"><span data-stu-id="71cad-p102">You can use the **RunApplication** action to run a Microsoft Windows-based or MS-DOS-based application, such as Microsoft Excel, Microsoft Word, or Microsoft PowerPoint, from within Microsoft Access. For example, you may want to paste Excel spreadsheet data into your Access database.</span></span>

> [!NOTE]
> <span data-ttu-id="71cad-110">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="71cad-110">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="71cad-111">设置</span><span class="sxs-lookup"><span data-stu-id="71cad-111">Setting</span></span>

<span data-ttu-id="71cad-112">**RunApplication** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="71cad-112">The **RunApplication** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="71cad-113">操作参数</span><span class="sxs-lookup"><span data-stu-id="71cad-113">Action argument</span></span></p></th>
<th><p><span data-ttu-id="71cad-114">说明</span><span class="sxs-lookup"><span data-stu-id="71cad-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71cad-115"><strong>命令行</strong></span><span class="sxs-lookup"><span data-stu-id="71cad-115"><strong>Command Line</strong></span></span></p></td>
<td><p><span data-ttu-id="71cad-p103">用来启动应用程序的命令行（包括路径和任何其他必选参数，例如让应用程序在特定模式下运行的开关）。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“命令行”</strong>框中输入命令行。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="71cad-p103">The command line used to start the application (including the path and any other necessary parameters, such as switches that run the application in a particular mode). Enter the command line in the <strong>Command Line</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. This is a required argument.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="71cad-119">说明</span><span class="sxs-lookup"><span data-stu-id="71cad-119">Remarks</span></span>

<span data-ttu-id="71cad-p104">通过此操作选择的应用程序在前台加载和运行。启动应用程序后，包含此操作的宏将继续运行。</span><span class="sxs-lookup"><span data-stu-id="71cad-p104">The application selected with this action loads and runs in the foreground. The macro containing this action continues to run after starting the application.</span></span>

<span data-ttu-id="71cad-p105">通过使用 Microsoft Windows 动态数据交换 (DDE) 功能或剪贴板，您可以在其他应用程序与 Access 之间传输数据。可以使用 **SendKeys** 操作将键击发送到其他应用程序，但 DDE 是更加高效的数据传输方法。还可以使用自动化功能在应用程序之间共享数据。</span><span class="sxs-lookup"><span data-stu-id="71cad-p105">You can transfer data between the other application and Access by using the Microsoft Windows dynamic data exchange (DDE) facility or the Clipboard. You can use the **SendKeys** action to send keystrokes to the other application (although DDE is a more efficient method for transferring data). You can also share data among applications by using automation.</span></span>

<span data-ttu-id="71cad-125">基于 MS-DOS 的应用程序在 Windows 环境中的 MS-DOS 窗口中运行。</span><span class="sxs-lookup"><span data-stu-id="71cad-125">MS-DOS-based applications run in an MS-DOS window within the Windows environment.</span></span>

<span data-ttu-id="71cad-126">在 Windows 操作系统中，有多种运行应用程序的方法，包括从 Windows 资源管理器中启动程序，使用 **"开始"** 菜单上的 **"运行"** 命令，以及双击 Windows 桌面上的程序图标。</span><span class="sxs-lookup"><span data-stu-id="71cad-126">In Windows operating systems, there are a number of ways to run an application, including starting the program from the Windows Explorer, using the **Run** command on the **Start** menu, and double-clicking a program icon on the Windows Desktop.</span></span>

<span data-ttu-id="71cad-p106">不能在 Visual Basic for Applications (VBA) 模块中运行 **RunApplication** 操作。请改用 VBA **Shell** 函数。</span><span class="sxs-lookup"><span data-stu-id="71cad-p106">You can't run the **RunApplication** action in a Visual Basic for Applications (VBA) module. Use the VBA **Shell** function instead.</span></span>

