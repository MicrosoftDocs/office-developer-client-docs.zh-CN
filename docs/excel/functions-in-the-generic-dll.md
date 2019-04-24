---
title: 通用 DLL 中的函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 泛型 dll [excel 2007], 函数, 函数 [excel 2007], 泛型 dll
localization_priority: Normal
ms.assetid: 80ce2247-d69d-45b0-b5e2-4ff0d7078a2c
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3064e1a09ad8850e121da678f3702a6236574599
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304086"
---
# <a name="functions-in-the-generic-dll"></a><span data-ttu-id="a0fe1-104">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="a0fe1-104">Functions in the Generic DLL</span></span>

 <span data-ttu-id="a0fe1-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a0fe1-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a0fe1-106">该文件夹`\EXAMPLES\GENERIC\`包含用于编译示例 DLL 的示例常规 xll 的 Microsoft Visual Studio 项目文件和源代码文件。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-106">The folder  `\EXAMPLES\GENERIC\` contains Microsoft Visual Studio project files and source code files that are needed to compile the example DLL GENERIC.xll.</span></span> <span data-ttu-id="a0fe1-107">您可以将此项目用作模板, 以编写自己的 Microsoft Excel xll。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-107">You can use this project as a template for writing your own Microsoft Excel XLLs.</span></span> <span data-ttu-id="a0fe1-108">此项目中的源代码演示了 Excel C API 的许多功能。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-108">The source code in this project demonstrates many of the features of the Excel C API.</span></span> 
  
<span data-ttu-id="a0fe1-109">加载 GENERIC 时, 它将创建一个具有四个命令的新的**通用**菜单:</span><span class="sxs-lookup"><span data-stu-id="a0fe1-109">When you load GENERIC.xll, it creates a new **Generic** menu with four commands:</span></span> 
  
- <span data-ttu-id="a0fe1-110">**对话框**-显示 "Microsoft Excel" 对话框。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-110">**Dialog** - Displays a Microsoft Excel dialog box.</span></span> 
    
- <span data-ttu-id="a0fe1-111">**Dance** -在周围移动所选内容, 直到按**ESC**键。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-111">**Dance** - Moves the selection around until you press the **ESC** key.</span></span> 
    
- <span data-ttu-id="a0fe1-112">"**本机对话框**"-显示 Windows 对话框。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-112">**Native Dialog** - Displays a Windows dialog box.</span></span> 
    
- <span data-ttu-id="a0fe1-113">**退出**-卸载 generic 并删除**通用**菜单。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-113">**Exit** - Unloads GENERIC.xll and removes the **Generic** menu.</span></span> 
    
<span data-ttu-id="a0fe1-114">generic 还提供了三个工作表函数、Func1、FuncSum 和 FuncFib, 可以在加载 GENERIC xll 时使用这些函数。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-114">GENERIC.xll also provides three worksheet functions, Func1, FuncSum, and FuncFib, which can be used whenever GENERIC.xll is loaded.</span></span> <span data-ttu-id="a0fe1-115">可以使用加载项管理器加载常规 xll, 如果它在最后一个 Excel 会话的正常结束时处于活动状态, 则会加载。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-115">GENERIC.xll can be loaded using the Add-in Manager, or it is loaded if it was active at the normal end of the last Excel session.</span></span>
  
<span data-ttu-id="a0fe1-116">此项目使用框架库 (FRMWRK32)。</span><span class="sxs-lookup"><span data-stu-id="a0fe1-116">This project uses the framework library (FRMWRK32.lib).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a0fe1-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="a0fe1-117">In this section</span></span>

[<span data-ttu-id="a0fe1-118">DIALOGMsgProc</span><span class="sxs-lookup"><span data-stu-id="a0fe1-118">DIALOGMsgProc</span></span>](dialogmsgproc.md)
  
[<span data-ttu-id="a0fe1-119">ExcelCursorProc</span><span class="sxs-lookup"><span data-stu-id="a0fe1-119">ExcelCursorProc</span></span>](excelcursorproc.md)
  
[<span data-ttu-id="a0fe1-120">HookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="a0fe1-120">HookExcelWindow</span></span>](hookexcelwindow.md)
  
[<span data-ttu-id="a0fe1-121">UnhookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="a0fe1-121">UnhookExcelWindow</span></span>](unhookexcelwindow.md)
  
[<span data-ttu-id="a0fe1-122">fShowDialog</span><span class="sxs-lookup"><span data-stu-id="a0fe1-122">fShowDialog</span></span>](fshowdialog.md)
  
[<span data-ttu-id="a0fe1-123">fDance</span><span class="sxs-lookup"><span data-stu-id="a0fe1-123">fDance</span></span>](fdance.md)
  
[<span data-ttu-id="a0fe1-124">fDialog/fDialog12</span><span class="sxs-lookup"><span data-stu-id="a0fe1-124">fDialog/fDialog12</span></span>](fdialog-fdialog12.md)
  
[<span data-ttu-id="a0fe1-125">fExit</span><span class="sxs-lookup"><span data-stu-id="a0fe1-125">fExit</span></span>](fexit.md)
  
[<span data-ttu-id="a0fe1-126">Func1</span><span class="sxs-lookup"><span data-stu-id="a0fe1-126">Func1</span></span>](func1.md)
  
[<span data-ttu-id="a0fe1-127">FuncSum</span><span class="sxs-lookup"><span data-stu-id="a0fe1-127">FuncSum</span></span>](funcsum.md)
  
[<span data-ttu-id="a0fe1-128">FuncFib</span><span class="sxs-lookup"><span data-stu-id="a0fe1-128">FuncFib</span></span>](funcfib.md)
  
## <a name="see-also"></a><span data-ttu-id="a0fe1-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0fe1-129">See also</span></span>



[<span data-ttu-id="a0fe1-130">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="a0fe1-130">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

