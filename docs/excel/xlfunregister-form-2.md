---
title: xlfUnregister (窗体 2)
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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: e0154e380b65b8c57e7e96a98ef131e26b49e203
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773865"
---
# <a name="xlfunregister-form-2"></a><span data-ttu-id="ec88d-104">xlfUnregister (窗体 2)</span><span class="sxs-lookup"><span data-stu-id="ec88d-104">xlfUnregister (Form 2)</span></span>

<span data-ttu-id="ec88d-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ec88d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="ec88d-106">可从 DLL 或 XLL 命令的本身已调用由 Microsoft Excel 进行调用。</span><span class="sxs-lookup"><span data-stu-id="ec88d-106">Can be called from a DLL or XLL command that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="ec88d-107">这是等效于从 Excel XLM 宏工作表调用**注销**。</span><span class="sxs-lookup"><span data-stu-id="ec88d-107">This is equivalent to calling **UNREGISTER** from an Excel XLM macro sheet.</span></span> 
  
<span data-ttu-id="ec88d-108">可在两个窗体中调用**xlfUnregister** :</span><span class="sxs-lookup"><span data-stu-id="ec88d-108">**xlfUnregister** can be called in two forms:</span></span> 
  
- <span data-ttu-id="ec88d-109">窗体 1： 取消注册的单个命令或函数。</span><span class="sxs-lookup"><span data-stu-id="ec88d-109">Form 1: Unregisters an individual command or function.</span></span>
    
- <span data-ttu-id="ec88d-110">窗体 2： 卸载并停用 XLL。</span><span class="sxs-lookup"><span data-stu-id="ec88d-110">Form 2: Unloads and deactivates an XLL.</span></span>
    
<span data-ttu-id="ec88d-111">此函数调用窗体 2 中，强制 DLL 或代码资源被完全卸载。</span><span class="sxs-lookup"><span data-stu-id="ec88d-111">Called in Form 2, this function forces a DLL or code resource to be unloaded completely.</span></span> <span data-ttu-id="ec88d-112">即使当前正在使用由另一个宏，无论使用计数，它注销所有在 DLL 中的功能。</span><span class="sxs-lookup"><span data-stu-id="ec88d-112">It unregisters all of the functions in a DLL, even if they are currently in use by another macro, no matter what the use count.</span></span> <span data-ttu-id="ec88d-113">此函数调用**xlAutoClose**，然后取消注册 DLL 中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="ec88d-113">This function calls **xlAutoClose**, and then unregisters all the functions in the DLL.</span></span>
  
```cs
Excel12(xlfUnregister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a><span data-ttu-id="ec88d-114">参数</span><span class="sxs-lookup"><span data-stu-id="ec88d-114">Parameters</span></span>

<span data-ttu-id="ec88d-115">_pxModuleText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="ec88d-115">_pxModuleText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="ec88d-116">DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="ec88d-116">The name of the DLL.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ec88d-117">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="ec88d-117">Property value/Return value</span></span>

<span data-ttu-id="ec88d-118">如果成功，则返回**TRUE** (**xltypeBool**)。</span><span class="sxs-lookup"><span data-stu-id="ec88d-118">If successful, returns **TRUE** (**xltypeBool**).</span></span> <span data-ttu-id="ec88d-119">如果不成功，则返回**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="ec88d-119">If unsuccessful, returns **FALSE**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ec88d-120">备注</span><span class="sxs-lookup"><span data-stu-id="ec88d-120">Remarks</span></span>

> [!NOTE] 
> <span data-ttu-id="ec88d-121">不要尝试取消注册的所有与一个简单的函数调用的 DLL 的资源的[xlAutoClose](xlautoclose.md)实现调用此函数的形式。</span><span class="sxs-lookup"><span data-stu-id="ec88d-121">Do not call this form of the function from your implementation of the [xlAutoClose](xlautoclose.md) in an attempt to unregister all of the DLL's resources with one simple function call.</span></span> <span data-ttu-id="ec88d-122">这将导致**xlAutoClose**和堆栈溢出递归呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec88d-122">This leads to recursive calling of **xlAutoClose** and a stack overflow.</span></span> 
  
### <a name="remember-to-delete-names"></a><span data-ttu-id="ec88d-123">请记住删除名称</span><span class="sxs-lookup"><span data-stu-id="ec88d-123">Remember to delete names</span></span>

<span data-ttu-id="ec88d-124">如果您指定**xlfRegister**， _pxFunctionText_参数注册的 DLL 函数和命令时，必须明确名称通过调用删除**xlfSetName**每个省略第二个参数，以便函数不再显示在函数向导。</span><span class="sxs-lookup"><span data-stu-id="ec88d-124">If you specified the  _pxFunctionText_ argument to **xlfRegister**, when registering the DLL's functions and commands, you must explicitly delete the names by calling **xlfSetName** for each one, omitting the second argument so that the function no longer appears in the Function Wizard.</span></span> <span data-ttu-id="ec88d-125">有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="ec88d-125">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec88d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec88d-126">See also</span></span>

- [<span data-ttu-id="ec88d-127">xlfRegister (窗体 1)</span><span class="sxs-lookup"><span data-stu-id="ec88d-127">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="ec88d-128">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="ec88d-128">xlfRegisterId</span></span>](xlfregisterid.md)
- [<span data-ttu-id="ec88d-129">xlfUnregister (窗体 1)</span><span class="sxs-lookup"><span data-stu-id="ec88d-129">xlfUnregister (Form 1)</span></span>](xlfunregister-form-1.md)
- [<span data-ttu-id="ec88d-130">关键及有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="ec88d-130">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

