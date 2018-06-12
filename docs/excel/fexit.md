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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 3abb5cd68a45fbcd16665dbc4d492d764bbd315e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773739"
---
# <a name="fexit"></a><span data-ttu-id="db570-104">fExit</span><span class="sxs-lookup"><span data-stu-id="db570-104">fExit</span></span>

 <span data-ttu-id="db570-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="db570-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="db570-106">示例用户定义卸载 GENERIC.xll 的命令。</span><span class="sxs-lookup"><span data-stu-id="db570-106">Example user-defined command that unloads GENERIC.xll.</span></span> <span data-ttu-id="db570-107">当加载 GENERIC.xll 时，它会创建用户定义的菜单中，一般，通过其访问此命令。</span><span class="sxs-lookup"><span data-stu-id="db570-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span> 
  
```cs
int WINAPI fExit(void);
```

## <a name="parameters"></a><span data-ttu-id="db570-108">参数</span><span class="sxs-lookup"><span data-stu-id="db570-108">Parameters</span></span>

<span data-ttu-id="db570-109">函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="db570-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="db570-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="db570-110">Property value/Return value</span></span>

<span data-ttu-id="db570-111">此函数始终返回 1。</span><span class="sxs-lookup"><span data-stu-id="db570-111">The function always returns 1.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="db570-112">备注</span><span class="sxs-lookup"><span data-stu-id="db570-112">Remarks</span></span>

<span data-ttu-id="db570-113">这是一个用户启动例程，退出 GENERIC.xll 应避免只需调用`UNREGISTER("GENERIC.XLL")`在此函数。</span><span class="sxs-lookup"><span data-stu-id="db570-113">This is a user-initiated routine to exit GENERIC.xll You should avoid simply calling  `UNREGISTER("GENERIC.XLL")` in this function.</span></span> <span data-ttu-id="db570-114">即使它们注册其他地方 else，这会关闭注销此 DLL 中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="db570-114">This would forcefully unregister all the functions in this DLL, even if they are registered somewhere else.</span></span> <span data-ttu-id="db570-115">相反，一次注销一个的功能。</span><span class="sxs-lookup"><span data-stu-id="db570-115">Instead, unregister the functions one at a time.</span></span> 
  
### <a name="example"></a><span data-ttu-id="db570-116">示例</span><span class="sxs-lookup"><span data-stu-id="db570-116">Example</span></span>

<span data-ttu-id="db570-117">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="db570-117">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="db570-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db570-118">See also</span></span>



[<span data-ttu-id="db570-119">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="db570-119">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

