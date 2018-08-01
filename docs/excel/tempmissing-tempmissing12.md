---
title: TempMissing/TempMissing12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempMissing
- TempMissing12
keywords:
- tempmissing 函数 [excel 2007，] TempMissing12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: d9cb6afc-1fbb-45d6-88e5-84eba3af3c60
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a6db2e1f2917ecd9361043577f4bf203b3267a5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773822"
---
# <a name="tempmissingtempmissing12"></a><span data-ttu-id="f5609-104">TempMissing/TempMissing12</span><span class="sxs-lookup"><span data-stu-id="f5609-104">TempMissing/TempMissing12</span></span>

 <span data-ttu-id="f5609-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f5609-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="f5609-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**的类型**xltypeMissing**。</span><span class="sxs-lookup"><span data-stu-id="f5609-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** of type **xltypeMissing**.</span></span>
  
```cs
LPXLOPER TempMissing(void);
LPXLOPER12 TempMissing12(void);
```

## <a name="parameters"></a><span data-ttu-id="f5609-107">参数</span><span class="sxs-lookup"><span data-stu-id="f5609-107">Parameters</span></span>

<span data-ttu-id="f5609-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="f5609-108">This function takes no parameters.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="f5609-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f5609-109">Return value</span></span>

<span data-ttu-id="f5609-110">返回一个指向**xltypeMissing** **XLOPER**/ **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="f5609-110">Returns a pointer to an **xltypeMissing** **XLOPER**/ **XLOPER12**.</span></span>
  
## <a name="example"></a><span data-ttu-id="f5609-111">示例</span><span class="sxs-lookup"><span data-stu-id="f5609-111">Example</span></span>

<span data-ttu-id="f5609-112">此示例使用**TempMissing12**提供三个缺少参数**xlcWorkspace**跟**布尔值** **FALSE**可禁止显示工作表的滚动条。</span><span class="sxs-lookup"><span data-stu-id="f5609-112">This example uses **TempMissing12** to provide three missing arguments to **xlcWorkspace** followed by a **Boolean** **FALSE** to suppress the display of worksheet scroll bars.</span></span> <span data-ttu-id="f5609-113">前三个参数对应于其他工作区设置其不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="f5609-113">The first three arguments correspond to other workspace settings which are unaffected.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempMissingExample(void)
{
   XLOPER12 xBool;
   xBool.xltype = xltypeBool;
   xBool.val.xbool = 0;
   Excel12f(xlcWorkspace, 0, 4, TempMissing12(), TempMissing12(),
      TempMissing12(), (LPXLOPER12)&xBool);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="f5609-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5609-114">See also</span></span>



[<span data-ttu-id="f5609-115">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="f5609-115">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

