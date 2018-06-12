---
title: xlfRegister (窗体 2)
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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: a535018e2b644966d183ba9ae862ce83670c9231
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773842"
---
# <a name="xlfregister-form-2"></a><span data-ttu-id="08895-104">xlfRegister (窗体 2)</span><span class="sxs-lookup"><span data-stu-id="08895-104">xlfRegister (Form 2)</span></span>

 <span data-ttu-id="08895-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="08895-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="08895-106">可从 DLL 或 XLL 命令的本身已调用由 Microsoft Excel 进行调用。</span><span class="sxs-lookup"><span data-stu-id="08895-106">Can be called from a DLL or XLL command that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="08895-107">这是等效于从 Excel XLM 宏工作表调用**注册**。</span><span class="sxs-lookup"><span data-stu-id="08895-107">This is equivalent to calling **REGISTER** from an Excel XLM macro sheet.</span></span> 
  
<span data-ttu-id="08895-108">可在两个窗体中调用**xlfRegister**函数：</span><span class="sxs-lookup"><span data-stu-id="08895-108">The **xlfRegister** function can be called in two forms:</span></span> 
  
- <span data-ttu-id="08895-109">[xlfRegister (窗体 1)](xlfregister-form-1.md): 注册单个命令或函数。</span><span class="sxs-lookup"><span data-stu-id="08895-109">[xlfRegister (Form 1)](xlfregister-form-1.md): Registers an individual command or function.</span></span>
    
- <span data-ttu-id="08895-110">xlfRegister (窗体 2): 加载并激活 XLL。</span><span class="sxs-lookup"><span data-stu-id="08895-110">xlfRegister (Form 2): Loads and activates an XLL.</span></span>
    
<span data-ttu-id="08895-111">调用窗体 2 中，此函数可以仅用于加载和激活包含[xlAutoOpen](xlautoopen.md)过程 XLL。</span><span class="sxs-lookup"><span data-stu-id="08895-111">Called in Form 2, this function can only be used to load and activate an XLL containing an [xlAutoOpen](xlautoopen.md) procedure.</span></span> 
  
```cs
Excel12(xlfRegister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a><span data-ttu-id="08895-112">参数</span><span class="sxs-lookup"><span data-stu-id="08895-112">Parameters</span></span>

 <span data-ttu-id="08895-113">_pxModuleText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="08895-113">_pxModuleText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="08895-114">要加载并激活的 dll 名称。</span><span class="sxs-lookup"><span data-stu-id="08895-114">The name of the DLL to be loaded and activated.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="08895-115">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="08895-115">Property value/Return value</span></span>

<span data-ttu-id="08895-116">如果成功，这将返回 DLL (**xltypeStr**) 的名称。</span><span class="sxs-lookup"><span data-stu-id="08895-116">If successful, this returns the name of the DLL (**xltypeStr**).</span></span> <span data-ttu-id="08895-117">否则，它返回 #VALUE ！</span><span class="sxs-lookup"><span data-stu-id="08895-117">Otherwise it returns a #VALUE!</span></span> <span data-ttu-id="08895-118">错误。</span><span class="sxs-lookup"><span data-stu-id="08895-118">error.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="08895-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08895-119">See also</span></span>



[<span data-ttu-id="08895-120">关键及有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="08895-120">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

