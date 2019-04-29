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
- tempmissing 函数 [excel 2007], TempMissing12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: d9cb6afc-1fbb-45d6-88e5-84eba3af3c60
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 37c127b2252f18643b34dfc72fd9929885a68d01
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435955"
---
# <a name="tempmissingtempmissing12"></a><span data-ttu-id="7aaf6-104">TempMissing/TempMissing12</span><span class="sxs-lookup"><span data-stu-id="7aaf6-104">TempMissing/TempMissing12</span></span>

 <span data-ttu-id="7aaf6-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7aaf6-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="7aaf6-106">创建**xltypeMissing**类型的临时**XLOPER**/ **XLOPER12**的框架库函数。</span><span class="sxs-lookup"><span data-stu-id="7aaf6-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** of type **xltypeMissing**.</span></span>
  
```cs
LPXLOPER TempMissing(void);
LPXLOPER12 TempMissing12(void);
```

## <a name="parameters"></a><span data-ttu-id="7aaf6-107">参数</span><span class="sxs-lookup"><span data-stu-id="7aaf6-107">Parameters</span></span>

<span data-ttu-id="7aaf6-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="7aaf6-108">This function takes no parameters.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="7aaf6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7aaf6-109">Return value</span></span>

<span data-ttu-id="7aaf6-110">返回指向**xltypeMissing** **XLOPER**/ **XLOPER12**的指针。</span><span class="sxs-lookup"><span data-stu-id="7aaf6-110">Returns a pointer to an **xltypeMissing** **XLOPER**/ **XLOPER12**.</span></span>
  
## <a name="example"></a><span data-ttu-id="7aaf6-111">示例</span><span class="sxs-lookup"><span data-stu-id="7aaf6-111">Example</span></span>

<span data-ttu-id="7aaf6-112">此示例使用**TempMissing12**为**xlcWorkspace**提供了三个缺少的参数, 后跟一个**布尔** **FALSE** , 以禁止显示工作表滚动条。</span><span class="sxs-lookup"><span data-stu-id="7aaf6-112">This example uses **TempMissing12** to provide three missing arguments to **xlcWorkspace** followed by a **Boolean** **FALSE** to suppress the display of worksheet scroll bars.</span></span> <span data-ttu-id="7aaf6-113">前三个参数对应于不受影响的其他工作区设置。</span><span class="sxs-lookup"><span data-stu-id="7aaf6-113">The first three arguments correspond to other workspace settings which are unaffected.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="7aaf6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7aaf6-114">See also</span></span>



[<span data-ttu-id="7aaf6-115">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="7aaf6-115">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

