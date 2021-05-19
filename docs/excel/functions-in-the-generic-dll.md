---
title: 通用 DLL 中的函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- generic dll [excel 2007]， functions，functions [Excel 2007]， Generic DLL
localization_priority: Normal
ms.assetid: 80ce2247-d69d-45b0-b5e2-4ff0d7078a2c
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3064e1a09ad8850e121da678f3702a6236574599
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420596"
---
# <a name="functions-in-the-generic-dll"></a><span data-ttu-id="0bb64-104">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="0bb64-104">Functions in the Generic DLL</span></span>

 <span data-ttu-id="0bb64-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0bb64-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="0bb64-106">该文件夹 `\EXAMPLES\GENERIC\` 包含Microsoft Visual Studio DLL GENERIC.xll 示例所需的项目文件和源代码文件。</span><span class="sxs-lookup"><span data-stu-id="0bb64-106">The folder  `\EXAMPLES\GENERIC\` contains Microsoft Visual Studio project files and source code files that are needed to compile the example DLL GENERIC.xll.</span></span> <span data-ttu-id="0bb64-107">您可以将此项目用作编写您自己的 XLL Microsoft Excel模板。</span><span class="sxs-lookup"><span data-stu-id="0bb64-107">You can use this project as a template for writing your own Microsoft Excel XLLs.</span></span> <span data-ttu-id="0bb64-108">此项目中的源代码演示了 C API Excel功能。</span><span class="sxs-lookup"><span data-stu-id="0bb64-108">The source code in this project demonstrates many of the features of the Excel C API.</span></span> 
  
<span data-ttu-id="0bb64-109">加载 GENERIC.xll 时，它会创建一个包含四个命令的新 **"通用** "菜单：</span><span class="sxs-lookup"><span data-stu-id="0bb64-109">When you load GENERIC.xll, it creates a new **Generic** menu with four commands:</span></span> 
  
- <span data-ttu-id="0bb64-110">**对话框**- 显示Microsoft Excel对话框。</span><span class="sxs-lookup"><span data-stu-id="0bb64-110">**Dialog** - Displays a Microsoft Excel dialog box.</span></span> 
    
- <span data-ttu-id="0bb64-111">**当** 按下 Esc 键之前，将所选内容 **四处** 移动。</span><span class="sxs-lookup"><span data-stu-id="0bb64-111">**Dance** - Moves the selection around until you press the **ESC** key.</span></span> 
    
- <span data-ttu-id="0bb64-112">**本机对话框**- 显示Windows对话框。</span><span class="sxs-lookup"><span data-stu-id="0bb64-112">**Native Dialog** - Displays a Windows dialog box.</span></span> 
    
- <span data-ttu-id="0bb64-113">**Exit** - 卸载 GENERIC.xll 并删除 **"泛型"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="0bb64-113">**Exit** - Unloads GENERIC.xll and removes the **Generic** menu.</span></span> 
    
<span data-ttu-id="0bb64-114">GENERIC.xll 还提供了三个工作表函数 Func1、FuncSum 和 FuncFib，每次加载 GENERIC.xll 时都可以使用。</span><span class="sxs-lookup"><span data-stu-id="0bb64-114">GENERIC.xll also provides three worksheet functions, Func1, FuncSum, and FuncFib, which can be used whenever GENERIC.xll is loaded.</span></span> <span data-ttu-id="0bb64-115">可以使用外接程序管理器加载 GENERIC.xll，或者，如果它在上一个加载项会话的普通末尾处于活动状态，Excel加载。</span><span class="sxs-lookup"><span data-stu-id="0bb64-115">GENERIC.xll can be loaded using the Add-in Manager, or it is loaded if it was active at the normal end of the last Excel session.</span></span>
  
<span data-ttu-id="0bb64-116">此项目使用 FRMWRK32.lib (框架库) 。</span><span class="sxs-lookup"><span data-stu-id="0bb64-116">This project uses the framework library (FRMWRK32.lib).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0bb64-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="0bb64-117">In this section</span></span>

[<span data-ttu-id="0bb64-118">DIALOGMsgProc</span><span class="sxs-lookup"><span data-stu-id="0bb64-118">DIALOGMsgProc</span></span>](dialogmsgproc.md)
  
[<span data-ttu-id="0bb64-119">ExcelCursorProc</span><span class="sxs-lookup"><span data-stu-id="0bb64-119">ExcelCursorProc</span></span>](excelcursorproc.md)
  
[<span data-ttu-id="0bb64-120">HookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="0bb64-120">HookExcelWindow</span></span>](hookexcelwindow.md)
  
[<span data-ttu-id="0bb64-121">UnhookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="0bb64-121">UnhookExcelWindow</span></span>](unhookexcelwindow.md)
  
[<span data-ttu-id="0bb64-122">fShowDialog</span><span class="sxs-lookup"><span data-stu-id="0bb64-122">fShowDialog</span></span>](fshowdialog.md)
  
[<span data-ttu-id="0bb64-123">fDance</span><span class="sxs-lookup"><span data-stu-id="0bb64-123">fDance</span></span>](fdance.md)
  
[<span data-ttu-id="0bb64-124">fDialog/fDialog12</span><span class="sxs-lookup"><span data-stu-id="0bb64-124">fDialog/fDialog12</span></span>](fdialog-fdialog12.md)
  
[<span data-ttu-id="0bb64-125">fExit</span><span class="sxs-lookup"><span data-stu-id="0bb64-125">fExit</span></span>](fexit.md)
  
[<span data-ttu-id="0bb64-126">Func1</span><span class="sxs-lookup"><span data-stu-id="0bb64-126">Func1</span></span>](func1.md)
  
[<span data-ttu-id="0bb64-127">FuncSum</span><span class="sxs-lookup"><span data-stu-id="0bb64-127">FuncSum</span></span>](funcsum.md)
  
[<span data-ttu-id="0bb64-128">FuncFib</span><span class="sxs-lookup"><span data-stu-id="0bb64-128">FuncFib</span></span>](funcfib.md)
  
## <a name="see-also"></a><span data-ttu-id="0bb64-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bb64-129">See also</span></span>



[<span data-ttu-id="0bb64-130">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="0bb64-130">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

