---
title: Func1
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Func1
keywords:
- func1 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 801b14ef-0be8-4b97-919d-a9d413705d1c
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a3d3c6bbd529f43bd75b31b9348498928390a8f5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408913"
---
# <a name="func1"></a><span data-ttu-id="79945-104">Func1</span><span class="sxs-lookup"><span data-stu-id="79945-104">Func1</span></span>

 <span data-ttu-id="79945-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79945-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="79945-106">用户定义的工作表函数示例演示了静态字符串值的返回。</span><span class="sxs-lookup"><span data-stu-id="79945-106">Example user-defined worksheet function demonstrates the return of a static string value.</span></span> <span data-ttu-id="79945-107">当加载了 GENERIC xll 时, 它将注册此函数, 以便可以从工作表中调用它。</span><span class="sxs-lookup"><span data-stu-id="79945-107">When GENERIC.xll is loaded, it registers this function so that it can be called from the worksheet.</span></span>
  
```cs
LPXLOPER12 WINAPI Func1(LPXLOPER12 px);
```

## <a name="parameters"></a><span data-ttu-id="79945-108">参数</span><span class="sxs-lookup"><span data-stu-id="79945-108">Parameters</span></span>

 <span data-ttu-id="79945-109">_px_(**LPXLOPER**)</span><span class="sxs-lookup"><span data-stu-id="79945-109">_px_ (**LPXLOPER**)</span></span>
  
<span data-ttu-id="79945-110">此参数将被忽略, 并且仅用于触发 Microsoft Excel 以调用函数。</span><span class="sxs-lookup"><span data-stu-id="79945-110">This argument is ignored, and serves only to trigger Microsoft Excel to call the function.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="79945-111">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="79945-111">Property value/Return value</span></span>

 <span data-ttu-id="79945-112">**LPXLOPER12**: 始终是字符串 "Func1"</span><span class="sxs-lookup"><span data-stu-id="79945-112">**LPXLOPER12**: Always the string "Func1"</span></span>
  
### <a name="example"></a><span data-ttu-id="79945-113">示例</span><span class="sxs-lookup"><span data-stu-id="79945-113">Example</span></span>

<span data-ttu-id="79945-114">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="79945-114">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="79945-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79945-115">See also</span></span>



[<span data-ttu-id="79945-116">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="79945-116">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

