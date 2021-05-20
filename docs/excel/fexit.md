---
title: fExit
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fExit
keywords:
- fexit 函数 [excel 2007]
localization_priority: Normal
ms.assetid: d85685fa-df70-45bb-b629-a9d43b5cb926
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 97f0a1ec797176fb51c87c58f94e46a323ae5b32
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429913"
---
# <a name="fexit"></a><span data-ttu-id="f836e-104">fExit</span><span class="sxs-lookup"><span data-stu-id="f836e-104">fExit</span></span>

 <span data-ttu-id="f836e-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f836e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="f836e-106">卸载 GENERIC.xll 的用户定义命令示例。</span><span class="sxs-lookup"><span data-stu-id="f836e-106">Example user-defined command that unloads GENERIC.xll.</span></span> <span data-ttu-id="f836e-107">加载 GENERIC.xll 时，它将创建一个用户定义的菜单 Generic，通过该菜单可以访问此命令。</span><span class="sxs-lookup"><span data-stu-id="f836e-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span> 
  
```cs
int WINAPI fExit(void);
```

## <a name="parameters"></a><span data-ttu-id="f836e-108">参数</span><span class="sxs-lookup"><span data-stu-id="f836e-108">Parameters</span></span>

<span data-ttu-id="f836e-109">该函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="f836e-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f836e-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="f836e-110">Property value/Return value</span></span>

<span data-ttu-id="f836e-111">函数始终返回 1。</span><span class="sxs-lookup"><span data-stu-id="f836e-111">The function always returns 1.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f836e-112">备注</span><span class="sxs-lookup"><span data-stu-id="f836e-112">Remarks</span></span>

<span data-ttu-id="f836e-113">这是用户启动的用于退出 GENERIC.xll 的例程 应避免在此函数  `UNREGISTER("GENERIC.XLL")` 中调用。</span><span class="sxs-lookup"><span data-stu-id="f836e-113">This is a user-initiated routine to exit GENERIC.xll You should avoid simply calling  `UNREGISTER("GENERIC.XLL")` in this function.</span></span> <span data-ttu-id="f836e-114">这将强制取消注册此 DLL 中所有函数，即使它们已在其他地方注册。</span><span class="sxs-lookup"><span data-stu-id="f836e-114">This would forcefully unregister all the functions in this DLL, even if they are registered somewhere else.</span></span> <span data-ttu-id="f836e-115">相反，应一次注销一个函数。</span><span class="sxs-lookup"><span data-stu-id="f836e-115">Instead, unregister the functions one at a time.</span></span> 
  
### <a name="example"></a><span data-ttu-id="f836e-116">示例</span><span class="sxs-lookup"><span data-stu-id="f836e-116">Example</span></span>

<span data-ttu-id="f836e-117">有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="f836e-117">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f836e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f836e-118">See also</span></span>



[<span data-ttu-id="f836e-119">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="f836e-119">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

