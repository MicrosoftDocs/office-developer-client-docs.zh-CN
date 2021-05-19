---
title: xlfRegister（窗体 2）
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfRegister
keywords:
- xlfregister 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 3ebbd775-f3d2-4ba7-8835-a5b38ad2267a
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 66af741456ab763ef346a8777429f0ae1be77c11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416039"
---
# <a name="xlfregister-form-2"></a><span data-ttu-id="631e3-104">xlfRegister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="631e3-104">xlfRegister (Form 2)</span></span>

 <span data-ttu-id="631e3-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="631e3-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="631e3-106">可以从 DLL 或 XLL 命令调用，该命令本身已由 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="631e3-106">Can be called from a DLL or XLL command that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="631e3-107">这相当于从 **XLM** 宏表Excel REGISTER。</span><span class="sxs-lookup"><span data-stu-id="631e3-107">This is equivalent to calling **REGISTER** from an Excel XLM macro sheet.</span></span> 
  
<span data-ttu-id="631e3-108">**xlfRegister** 函数可以两种形式调用：</span><span class="sxs-lookup"><span data-stu-id="631e3-108">The **xlfRegister** function can be called in two forms:</span></span> 
  
- <span data-ttu-id="631e3-109">[xlfRegister (Form 1) ](xlfregister-form-1.md)：注册单个命令或函数。</span><span class="sxs-lookup"><span data-stu-id="631e3-109">[xlfRegister (Form 1)](xlfregister-form-1.md): Registers an individual command or function.</span></span>
    
- <span data-ttu-id="631e3-110">xlfRegister (表单 2) ：加载并激活 XLL。</span><span class="sxs-lookup"><span data-stu-id="631e3-110">xlfRegister (Form 2): Loads and activates an XLL.</span></span>
    
<span data-ttu-id="631e3-111">此函数在窗体 2 中调用，只能用于加载和激活包含 [xlAutoOpen](xlautoopen.md) 过程 XLL。</span><span class="sxs-lookup"><span data-stu-id="631e3-111">Called in Form 2, this function can only be used to load and activate an XLL containing an [xlAutoOpen](xlautoopen.md) procedure.</span></span> 
  
```cs
Excel12(xlfRegister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a><span data-ttu-id="631e3-112">参数</span><span class="sxs-lookup"><span data-stu-id="631e3-112">Parameters</span></span>

 <span data-ttu-id="631e3-113">_pxModuleText_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="631e3-113">_pxModuleText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="631e3-114">要加载和激活的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="631e3-114">The name of the DLL to be loaded and activated.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="631e3-115">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="631e3-115">Property value/Return value</span></span>

<span data-ttu-id="631e3-116">如果成功，这将返回 **xltypeStr** (DLL) 。</span><span class="sxs-lookup"><span data-stu-id="631e3-116">If successful, this returns the name of the DLL (**xltypeStr**).</span></span> <span data-ttu-id="631e3-117">否则，它将返回#VALUE！</span><span class="sxs-lookup"><span data-stu-id="631e3-117">Otherwise it returns a #VALUE!</span></span> <span data-ttu-id="631e3-118">error。</span><span class="sxs-lookup"><span data-stu-id="631e3-118">error.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="631e3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="631e3-119">See also</span></span>



[<span data-ttu-id="631e3-120">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="631e3-120">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

