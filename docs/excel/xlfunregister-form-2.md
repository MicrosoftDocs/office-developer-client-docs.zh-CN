---
title: xlfUnregister（窗体 2）
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfUnregister (Form 2)
keywords:
- xlfunregister [excel 2007]
localization_priority: Normal
ms.assetid: 39c6eba7-ba41-4e7b-9a28-2b662378ff5a
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 8bf1151e1ba4c165e784b88dce80096a2eaa62de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419903"
---
# <a name="xlfunregister-form-2"></a><span data-ttu-id="30714-104">xlfUnregister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="30714-104">xlfUnregister (Form 2)</span></span>

<span data-ttu-id="30714-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="30714-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="30714-106">可以从 DLL 或 XLL 命令调用，该命令本身已由 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="30714-106">Can be called from a DLL or XLL command that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="30714-107">这相当于从 XLM 宏表Excel **UNREGISTER。**</span><span class="sxs-lookup"><span data-stu-id="30714-107">This is equivalent to calling **UNREGISTER** from an Excel XLM macro sheet.</span></span> 
  
<span data-ttu-id="30714-108">**xlfUnregister** 可以两种形式调用：</span><span class="sxs-lookup"><span data-stu-id="30714-108">**xlfUnregister** can be called in two forms:</span></span> 
  
- <span data-ttu-id="30714-109">表单 1：取消注册单个命令或函数。</span><span class="sxs-lookup"><span data-stu-id="30714-109">Form 1: Unregisters an individual command or function.</span></span>
    
- <span data-ttu-id="30714-110">表单 2：卸载和停用 XLL。</span><span class="sxs-lookup"><span data-stu-id="30714-110">Form 2: Unloads and deactivates an XLL.</span></span>
    
<span data-ttu-id="30714-111">在表单 2 中调用此函数会强制完全卸载 DLL 或代码资源。</span><span class="sxs-lookup"><span data-stu-id="30714-111">Called in Form 2, this function forces a DLL or code resource to be unloaded completely.</span></span> <span data-ttu-id="30714-112">它取消注册 DLL 中所有函数，即使它们当前正由另一个宏使用，无论使用计数如何。</span><span class="sxs-lookup"><span data-stu-id="30714-112">It unregisters all of the functions in a DLL, even if they are currently in use by another macro, no matter what the use count.</span></span> <span data-ttu-id="30714-113">此函数调用 **xlAutoClose**，然后取消注册 DLL 中所有函数。</span><span class="sxs-lookup"><span data-stu-id="30714-113">This function calls **xlAutoClose**, and then unregisters all the functions in the DLL.</span></span>
  
```cs
Excel12(xlfUnregister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a><span data-ttu-id="30714-114">参数</span><span class="sxs-lookup"><span data-stu-id="30714-114">Parameters</span></span>

<span data-ttu-id="30714-115">_pxModuleText_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="30714-115">_pxModuleText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="30714-116">DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="30714-116">The name of the DLL.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="30714-117">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="30714-117">Property value/Return value</span></span>

<span data-ttu-id="30714-118">如果成功，则返回 **xltypeBool** (TRUE) 。 </span><span class="sxs-lookup"><span data-stu-id="30714-118">If successful, returns **TRUE** (**xltypeBool**).</span></span> <span data-ttu-id="30714-119">如果失败，则返回 **FALSE**。</span><span class="sxs-lookup"><span data-stu-id="30714-119">If unsuccessful, returns **FALSE**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="30714-120">备注</span><span class="sxs-lookup"><span data-stu-id="30714-120">Remarks</span></span>

> [!NOTE] 
> <span data-ttu-id="30714-121">不要从 [xlAutoClose](xlautoclose.md) 的实现中调用此形式的函数，以尝试通过一个简单的函数调用注销 DLL 的所有资源。</span><span class="sxs-lookup"><span data-stu-id="30714-121">Do not call this form of the function from your implementation of the [xlAutoClose](xlautoclose.md) in an attempt to unregister all of the DLL's resources with one simple function call.</span></span> <span data-ttu-id="30714-122">这将导致递归调用 **xlAutoClose** 和堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="30714-122">This leads to recursive calling of **xlAutoClose** and a stack overflow.</span></span> 
  
### <a name="remember-to-delete-names"></a><span data-ttu-id="30714-123">请记住删除名称</span><span class="sxs-lookup"><span data-stu-id="30714-123">Remember to delete names</span></span>

<span data-ttu-id="30714-124">如果将  _pxFunctionText_ 参数指定为 **xlfRegister**，则注册 DLL 的函数和命令时，必须通过调用每个函数的 **xlfSetName** 来明确删除名称，同时省略第二个参数，以便函数不再显示在函数向导中。</span><span class="sxs-lookup"><span data-stu-id="30714-124">If you specified the  _pxFunctionText_ argument to **xlfRegister**, when registering the DLL's functions and commands, you must explicitly delete the names by calling **xlfSetName** for each one, omitting the second argument so that the function no longer appears in the Function Wizard.</span></span> <span data-ttu-id="30714-125">有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="30714-125">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="30714-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30714-126">See also</span></span>

- [<span data-ttu-id="30714-127">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="30714-127">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="30714-128">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="30714-128">xlfRegisterId</span></span>](xlfregisterid.md)
- [<span data-ttu-id="30714-129">xlfUnregister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="30714-129">xlfUnregister (Form 1)</span></span>](xlfunregister-form-1.md)
- [<span data-ttu-id="30714-130">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="30714-130">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

