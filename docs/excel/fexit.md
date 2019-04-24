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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 97f0a1ec797176fb51c87c58f94e46a323ae5b32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310855"
---
# <a name="fexit"></a><span data-ttu-id="866e0-104">fExit</span><span class="sxs-lookup"><span data-stu-id="866e0-104">fExit</span></span>

 <span data-ttu-id="866e0-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="866e0-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="866e0-106">用于卸载通用 xll 的用户定义命令示例。</span><span class="sxs-lookup"><span data-stu-id="866e0-106">Example user-defined command that unloads GENERIC.xll.</span></span> <span data-ttu-id="866e0-107">当加载了 generic xll 时, 它将创建一个用户定义的菜单 (通用), 通过该菜单可访问此命令。</span><span class="sxs-lookup"><span data-stu-id="866e0-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span> 
  
```cs
int WINAPI fExit(void);
```

## <a name="parameters"></a><span data-ttu-id="866e0-108">参数</span><span class="sxs-lookup"><span data-stu-id="866e0-108">Parameters</span></span>

<span data-ttu-id="866e0-109">函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="866e0-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="866e0-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="866e0-110">Property value/Return value</span></span>

<span data-ttu-id="866e0-111">函数总是返回1。</span><span class="sxs-lookup"><span data-stu-id="866e0-111">The function always returns 1.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="866e0-112">注解</span><span class="sxs-lookup"><span data-stu-id="866e0-112">Remarks</span></span>

<span data-ttu-id="866e0-113">这是用户启动的用于退出 GENERIC 的例程。您应避免只是在`UNREGISTER("GENERIC.XLL")`此函数中调用。</span><span class="sxs-lookup"><span data-stu-id="866e0-113">This is a user-initiated routine to exit GENERIC.xll You should avoid simply calling  `UNREGISTER("GENERIC.XLL")` in this function.</span></span> <span data-ttu-id="866e0-114">这将强制注销此 DLL 中的所有函数, 即使它们在其他位置注册也是如此。</span><span class="sxs-lookup"><span data-stu-id="866e0-114">This would forcefully unregister all the functions in this DLL, even if they are registered somewhere else.</span></span> <span data-ttu-id="866e0-115">相反, 一次注销一个函数。</span><span class="sxs-lookup"><span data-stu-id="866e0-115">Instead, unregister the functions one at a time.</span></span> 
  
### <a name="example"></a><span data-ttu-id="866e0-116">示例</span><span class="sxs-lookup"><span data-stu-id="866e0-116">Example</span></span>

<span data-ttu-id="866e0-117">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="866e0-117">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="866e0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="866e0-118">See also</span></span>



[<span data-ttu-id="866e0-119">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="866e0-119">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

