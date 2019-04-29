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
# <a name="fdance"></a><span data-ttu-id="454ab-104">fDance</span><span class="sxs-lookup"><span data-stu-id="454ab-104">fDance</span></span>

 <span data-ttu-id="454ab-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="454ab-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="454ab-106">用于更改活动工作表上的选定单元格的用户定义命令的示例, 直到用户按**ESC**。</span><span class="sxs-lookup"><span data-stu-id="454ab-106">Example user-defined command that changes the selected cells on the active worksheet around until the user presses **ESC**.</span></span> <span data-ttu-id="454ab-107">当加载了 generic xll 时, 它将创建一个用户定义的菜单 (通用), 通过该菜单可访问此命令。</span><span class="sxs-lookup"><span data-stu-id="454ab-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span>
  
```cs
int WINAPI fDance(void);
```

## <a name="parameters"></a><span data-ttu-id="454ab-108">参数</span><span class="sxs-lookup"><span data-stu-id="454ab-108">Parameters</span></span>

<span data-ttu-id="454ab-109">函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="454ab-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="454ab-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="454ab-110">Property value/Return value</span></span>

<span data-ttu-id="454ab-111">函数总是返回1。</span><span class="sxs-lookup"><span data-stu-id="454ab-111">The function always returns 1.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="454ab-112">说明</span><span class="sxs-lookup"><span data-stu-id="454ab-112">Remarks</span></span>

<span data-ttu-id="454ab-113">这是一个漫长的操作示例。</span><span class="sxs-lookup"><span data-stu-id="454ab-113">This is an example of a lengthy operation.</span></span> <span data-ttu-id="454ab-114">它偶尔调用函数[xlAbort](xlabort.md) 。</span><span class="sxs-lookup"><span data-stu-id="454ab-114">It calls the function [xlAbort](xlabort.md) occasionally.</span></span> <span data-ttu-id="454ab-115">这将生成处理器 (帮助协作多任务), 并检查用户是否已按**ESC**取消操作。</span><span class="sxs-lookup"><span data-stu-id="454ab-115">This yields the processor (helping with cooperative multitasking), and checks whether the user has pressed **ESC** to cancel the operation.</span></span> <span data-ttu-id="454ab-116">如果是这样, 它向用户提供了取消中止的机会。</span><span class="sxs-lookup"><span data-stu-id="454ab-116">If so, it offers the user a chance to cancel the abort.</span></span> 
  
### <a name="example"></a><span data-ttu-id="454ab-117">示例</span><span class="sxs-lookup"><span data-stu-id="454ab-117">Example</span></span>

<span data-ttu-id="454ab-118">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="454ab-118">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="454ab-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="454ab-119">See also</span></span>



[<span data-ttu-id="454ab-120">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="454ab-120">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

