---
title: fDance
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fDance
keywords:
- fdance 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 8c2f2d83-b7aa-456e-b473-a54897bc35ae
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a191c07d2a06a1cb6123c235e8fac69d90426758
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409046"
---
# <a name="fdance"></a><span data-ttu-id="25739-104">fDance</span><span class="sxs-lookup"><span data-stu-id="25739-104">fDance</span></span>

 <span data-ttu-id="25739-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="25739-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="25739-106">示例用户定义命令，该命令将活动工作表上的选定单元格四处更改，直到用户按 **ESC。**</span><span class="sxs-lookup"><span data-stu-id="25739-106">Example user-defined command that changes the selected cells on the active worksheet around until the user presses **ESC**.</span></span> <span data-ttu-id="25739-107">加载 GENERIC.xll 时，它将创建一个用户定义的菜单 Generic，通过该菜单可以访问此命令。</span><span class="sxs-lookup"><span data-stu-id="25739-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span>
  
```cs
int WINAPI fDance(void);
```

## <a name="parameters"></a><span data-ttu-id="25739-108">参数</span><span class="sxs-lookup"><span data-stu-id="25739-108">Parameters</span></span>

<span data-ttu-id="25739-109">该函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="25739-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="25739-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="25739-110">Property value/Return value</span></span>

<span data-ttu-id="25739-111">函数始终返回 1。</span><span class="sxs-lookup"><span data-stu-id="25739-111">The function always returns 1.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="25739-112">备注</span><span class="sxs-lookup"><span data-stu-id="25739-112">Remarks</span></span>

<span data-ttu-id="25739-113">这是一个冗长操作的示例。</span><span class="sxs-lookup"><span data-stu-id="25739-113">This is an example of a lengthy operation.</span></span> <span data-ttu-id="25739-114">它偶尔调用[函数 xlAbort。](xlabort.md)</span><span class="sxs-lookup"><span data-stu-id="25739-114">It calls the function [xlAbort](xlabort.md) occasionally.</span></span> <span data-ttu-id="25739-115">这样，处理器 (协作多任务) ，并检查用户是否已按 **ESC** 取消操作。</span><span class="sxs-lookup"><span data-stu-id="25739-115">This yields the processor (helping with cooperative multitasking), and checks whether the user has pressed **ESC** to cancel the operation.</span></span> <span data-ttu-id="25739-116">如果是这样，它将为用户提供取消中止的机会。</span><span class="sxs-lookup"><span data-stu-id="25739-116">If so, it offers the user a chance to cancel the abort.</span></span> 
  
### <a name="example"></a><span data-ttu-id="25739-117">示例</span><span class="sxs-lookup"><span data-stu-id="25739-117">Example</span></span>

<span data-ttu-id="25739-118">有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="25739-118">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="25739-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25739-119">See also</span></span>



[<span data-ttu-id="25739-120">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="25739-120">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

