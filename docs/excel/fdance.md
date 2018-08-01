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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: b7a2fbdf723d06dcf9b02789178d7d12d0515884
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773752"
---
# <a name="fdance"></a><span data-ttu-id="c153d-104">fDance</span><span class="sxs-lookup"><span data-stu-id="c153d-104">fDance</span></span>

 <span data-ttu-id="c153d-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c153d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c153d-106">示例用户定义直到用户按**ESC**更改所选单元格周围活动工作表上的命令。</span><span class="sxs-lookup"><span data-stu-id="c153d-106">Example user-defined command that changes the selected cells on the active worksheet around until the user presses **ESC**.</span></span> <span data-ttu-id="c153d-107">当加载 GENERIC.xll 时，它会创建用户定义的菜单中，一般，通过其访问此命令。</span><span class="sxs-lookup"><span data-stu-id="c153d-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span>
  
```cs
int WINAPI fDance(void);
```

## <a name="parameters"></a><span data-ttu-id="c153d-108">参数</span><span class="sxs-lookup"><span data-stu-id="c153d-108">Parameters</span></span>

<span data-ttu-id="c153d-109">函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="c153d-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c153d-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="c153d-110">Property value/Return value</span></span>

<span data-ttu-id="c153d-111">此函数始终返回 1。</span><span class="sxs-lookup"><span data-stu-id="c153d-111">The function always returns 1.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c153d-112">说明</span><span class="sxs-lookup"><span data-stu-id="c153d-112">Remarks</span></span>

<span data-ttu-id="c153d-113">这是较长操作的示例。</span><span class="sxs-lookup"><span data-stu-id="c153d-113">This is an example of a lengthy operation.</span></span> <span data-ttu-id="c153d-114">有时，它调用函数[xlAbort](xlabort.md) 。</span><span class="sxs-lookup"><span data-stu-id="c153d-114">It calls the function [xlAbort](xlabort.md) occasionally.</span></span> <span data-ttu-id="c153d-115">这会产生处理器 （与协作式多任务帮助），并检查用户是否已按**esc 键**以取消操作。</span><span class="sxs-lookup"><span data-stu-id="c153d-115">This yields the processor (helping with cooperative multitasking), and checks whether the user has pressed **ESC** to cancel the operation.</span></span> <span data-ttu-id="c153d-116">如果是这样，它会向用户提供有机会在取消中止。</span><span class="sxs-lookup"><span data-stu-id="c153d-116">If so, it offers the user a chance to cancel the abort.</span></span> 
  
### <a name="example"></a><span data-ttu-id="c153d-117">示例</span><span class="sxs-lookup"><span data-stu-id="c153d-117">Example</span></span>

<span data-ttu-id="c153d-118">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="c153d-118">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c153d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c153d-119">See also</span></span>



[<span data-ttu-id="c153d-120">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="c153d-120">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

