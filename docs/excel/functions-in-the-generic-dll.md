---
title: 泛型 DLL 中的函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 泛型 dll [excel 2007，] 函数，函数 [Excel 2007，] 泛型 DLL
localization_priority: Normal
ms.assetid: 80ce2247-d69d-45b0-b5e2-4ff0d7078a2c
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: e78f276e58ca1c98786e28ed5167762cf0bfdf7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773767"
---
# <a name="functions-in-the-generic-dll"></a><span data-ttu-id="1fe53-104">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="1fe53-104">Functions in the Generic DLL</span></span>

 <span data-ttu-id="1fe53-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1fe53-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="1fe53-106">文件夹`\EXAMPLES\GENERIC\`包含 Microsoft Visual Studio 项目文件和所需编译该示例 DLL GENERIC.xll 源代码文件。</span><span class="sxs-lookup"><span data-stu-id="1fe53-106">The folder  `\EXAMPLES\GENERIC\` contains Microsoft Visual Studio project files and source code files that are needed to compile the example DLL GENERIC.xll.</span></span> <span data-ttu-id="1fe53-107">编写您自己的 Microsoft Excel Xll 可作为模板用于此项目。</span><span class="sxs-lookup"><span data-stu-id="1fe53-107">You can use this project as a template for writing your own Microsoft Excel XLLs.</span></span> <span data-ttu-id="1fe53-108">此项目中的源代码演示了许多 Excel C API 的功能。</span><span class="sxs-lookup"><span data-stu-id="1fe53-108">The source code in this project demonstrates many of the features of the Excel C API.</span></span> 
  
<span data-ttu-id="1fe53-109">当加载 GENERIC.xll 时，它使用四个命令创建一个新的**泛型**菜单：</span><span class="sxs-lookup"><span data-stu-id="1fe53-109">When you load GENERIC.xll, it creates a new **Generic** menu with four commands:</span></span> 
  
- <span data-ttu-id="1fe53-110">**对话框**-显示 Microsoft Excel 对话框。</span><span class="sxs-lookup"><span data-stu-id="1fe53-110">**Dialog** - Displays a Microsoft Excel dialog box.</span></span> 
    
- <span data-ttu-id="1fe53-111">**舞**-移动所选内容，直到您按**ESC**键。</span><span class="sxs-lookup"><span data-stu-id="1fe53-111">**Dance** - Moves the selection around until you press the **ESC** key.</span></span> 
    
- <span data-ttu-id="1fe53-112">**本机对话框**-显示 Windows 对话框。</span><span class="sxs-lookup"><span data-stu-id="1fe53-112">**Native Dialog** - Displays a Windows dialog box.</span></span> 
    
- <span data-ttu-id="1fe53-113">**退出**-卸载 GENERIC.xll 并删除**通用**菜单。</span><span class="sxs-lookup"><span data-stu-id="1fe53-113">**Exit** - Unloads GENERIC.xll and removes the **Generic** menu.</span></span> 
    
<span data-ttu-id="1fe53-114">GENERIC.xll 还提供了三个工作表函数、 Func1、 FuncSum 和 FuncFib，每当加载 GENERIC.xll 可以使用它。</span><span class="sxs-lookup"><span data-stu-id="1fe53-114">GENERIC.xll also provides three worksheet functions, Func1, FuncSum, and FuncFib, which can be used whenever GENERIC.xll is loaded.</span></span> <span data-ttu-id="1fe53-115">可使用的加载项管理器中，加载 GENERIC.xll 或加载如果在正常的最后一个 Excel 会话结束处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="1fe53-115">GENERIC.xll can be loaded using the Add-in Manager, or it is loaded if it was active at the normal end of the last Excel session.</span></span>
  
<span data-ttu-id="1fe53-116">此项目使用 framework 库 (FRMWRK32.lib)。</span><span class="sxs-lookup"><span data-stu-id="1fe53-116">This project uses the framework library (FRMWRK32.lib).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="1fe53-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="1fe53-117">In this section</span></span>

[<span data-ttu-id="1fe53-118">DIALOGMsgProc</span><span class="sxs-lookup"><span data-stu-id="1fe53-118">DIALOGMsgProc</span></span>](dialogmsgproc.md)
  
[<span data-ttu-id="1fe53-119">ExcelCursorProc</span><span class="sxs-lookup"><span data-stu-id="1fe53-119">ExcelCursorProc</span></span>](excelcursorproc.md)
  
[<span data-ttu-id="1fe53-120">HookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="1fe53-120">HookExcelWindow</span></span>](hookexcelwindow.md)
  
[<span data-ttu-id="1fe53-121">UnhookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="1fe53-121">UnhookExcelWindow</span></span>](unhookexcelwindow.md)
  
[<span data-ttu-id="1fe53-122">fShowDialog</span><span class="sxs-lookup"><span data-stu-id="1fe53-122">fShowDialog</span></span>](fshowdialog.md)
  
[<span data-ttu-id="1fe53-123">fDance</span><span class="sxs-lookup"><span data-stu-id="1fe53-123">fDance</span></span>](fdance.md)
  
[<span data-ttu-id="1fe53-124">fDialog/fDialog12</span><span class="sxs-lookup"><span data-stu-id="1fe53-124">fDialog/fDialog12</span></span>](fdialog-fdialog12.md)
  
[<span data-ttu-id="1fe53-125">fExit</span><span class="sxs-lookup"><span data-stu-id="1fe53-125">fExit</span></span>](fexit.md)
  
[<span data-ttu-id="1fe53-126">Func1</span><span class="sxs-lookup"><span data-stu-id="1fe53-126">Func1</span></span>](func1.md)
  
[<span data-ttu-id="1fe53-127">FuncSum</span><span class="sxs-lookup"><span data-stu-id="1fe53-127">FuncSum</span></span>](funcsum.md)
  
[<span data-ttu-id="1fe53-128">FuncFib</span><span class="sxs-lookup"><span data-stu-id="1fe53-128">FuncFib</span></span>](funcfib.md)
  
## <a name="see-also"></a><span data-ttu-id="1fe53-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fe53-129">See also</span></span>



[<span data-ttu-id="1fe53-130">Framework 库中的函数</span><span class="sxs-lookup"><span data-stu-id="1fe53-130">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

