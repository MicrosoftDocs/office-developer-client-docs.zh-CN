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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 26439f1fb05aae2077844ce19935d9ff99e4f701
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773749"
---
# <a name="func1"></a><span data-ttu-id="2573c-104">Func1</span><span class="sxs-lookup"><span data-stu-id="2573c-104">Func1</span></span>

 <span data-ttu-id="2573c-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2573c-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2573c-106">示例用户定义的工作表函数演示的静态的字符串值返回。</span><span class="sxs-lookup"><span data-stu-id="2573c-106">Example user-defined worksheet function demonstrates the return of a static string value.</span></span> <span data-ttu-id="2573c-107">加载 GENERIC.xll 时，以便它可以调用从工作表中注册此函数。</span><span class="sxs-lookup"><span data-stu-id="2573c-107">When GENERIC.xll is loaded, it registers this function so that it can be called from the worksheet.</span></span>
  
```cs
LPXLOPER12 WINAPI Func1(LPXLOPER12 px);
```

## <a name="parameters"></a><span data-ttu-id="2573c-108">参数</span><span class="sxs-lookup"><span data-stu-id="2573c-108">Parameters</span></span>

 <span data-ttu-id="2573c-109">_像素_(**LPXLOPER**)</span><span class="sxs-lookup"><span data-stu-id="2573c-109">_px_ (**LPXLOPER**)</span></span>
  
<span data-ttu-id="2573c-110">此参数被忽略，并且可仅对触发器 Microsoft Excel 将调用的函数。</span><span class="sxs-lookup"><span data-stu-id="2573c-110">This argument is ignored, and serves only to trigger Microsoft Excel to call the function.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2573c-111">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="2573c-111">Property value/Return value</span></span>

 <span data-ttu-id="2573c-112">**LPXLOPER12**： 始终字符串"Func1"</span><span class="sxs-lookup"><span data-stu-id="2573c-112">**LPXLOPER12**: Always the string "Func1"</span></span>
  
### <a name="example"></a><span data-ttu-id="2573c-113">示例</span><span class="sxs-lookup"><span data-stu-id="2573c-113">Example</span></span>

<span data-ttu-id="2573c-114">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="2573c-114">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2573c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2573c-115">See also</span></span>



[<span data-ttu-id="2573c-116">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="2573c-116">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

