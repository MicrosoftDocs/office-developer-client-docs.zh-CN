---
title: TempBool/TempBool12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempBool
- TempBool12
keywords:
- tempbool 函数 [excel 2007，] TempBool12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 0cf1fa58-416f-4692-a2e3-422473c19492
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 30874e7b918d8cd780bef60b4b02de1319f0f9ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773815"
---
# <a name="tempbooltempbool12"></a><span data-ttu-id="d1d77-104">TempBool/TempBool12</span><span class="sxs-lookup"><span data-stu-id="d1d77-104">TempBool/TempBool12</span></span>

 <span data-ttu-id="d1d77-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d1d77-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d1d77-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**包含**布尔值** **TRUE**或**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="d1d77-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** containing **Boolean** **TRUE** or **FALSE**.</span></span>
  
```cs
LPXLOPER TempBool(int b);
LPXLOPER12 TempBool12(int b);
```

## <a name="parameters"></a><span data-ttu-id="d1d77-107">参数</span><span class="sxs-lookup"><span data-stu-id="d1d77-107">Parameters</span></span>

 <span data-ttu-id="d1d77-108">_b_ (**int**)</span><span class="sxs-lookup"><span data-stu-id="d1d77-108">_b_ (**int**)</span></span>
  
<span data-ttu-id="d1d77-109">使用 0，则返回**FALSE**;使用任何其他值返回**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="d1d77-109">Use 0 to return **FALSE**; use any other value to return **TRUE**.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d1d77-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d1d77-110">Property value/Return value</span></span>

<span data-ttu-id="d1d77-111">返回**xltypeBool** **布尔**包含传入的逻辑值。</span><span class="sxs-lookup"><span data-stu-id="d1d77-111">Returns an **xltypeBool** **Boolean** containing the logical value passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="d1d77-112">示例</span><span class="sxs-lookup"><span data-stu-id="d1d77-112">Example</span></span>

<span data-ttu-id="d1d77-113">下面的示例使用**TempBool12**函数以清除状态栏。</span><span class="sxs-lookup"><span data-stu-id="d1d77-113">The following example uses the **TempBool12** function to clear the status bar.</span></span> <span data-ttu-id="d1d77-114">调用[Excel/Excel12f](excel-excel12f.md)函数时释放临时内存。</span><span class="sxs-lookup"><span data-stu-id="d1d77-114">Temporary memory is freed when the [Excel/Excel12f](excel-excel12f.md) function is called.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short int WINAPI TempBoolExample(void)
{
    Excel12f(xlcMessage, 0, 1, TempBool12(0));
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="d1d77-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1d77-115">See also</span></span>



[<span data-ttu-id="d1d77-116">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="d1d77-116">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

