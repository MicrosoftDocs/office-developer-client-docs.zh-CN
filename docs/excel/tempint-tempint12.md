---
title: TempInt/TempInt12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempInt
- TempInt12
keywords:
- tempint12 函数 [excel 2007，] TempInt 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 86d690b8-caca-450d-93f7-69ca4cd1a6e0
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: eb1dd9be0c0b20e533d9cd8202f8878c43b997be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773821"
---
# <a name="tempinttempint12"></a><span data-ttu-id="33b45-104">TempInt/TempInt12</span><span class="sxs-lookup"><span data-stu-id="33b45-104">TempInt/TempInt12</span></span>

 <span data-ttu-id="33b45-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="33b45-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="33b45-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**包含一个整数。</span><span class="sxs-lookup"><span data-stu-id="33b45-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** that contains an integer.</span></span> 
  
```cs
LPXLOPER TempInt(short int i);
LPXLOPER12 TempInt12(int i);
```

## <a name="parameters"></a><span data-ttu-id="33b45-107">参数</span><span class="sxs-lookup"><span data-stu-id="33b45-107">Parameters</span></span>

 <span data-ttu-id="33b45-108">_我_</span><span class="sxs-lookup"><span data-stu-id="33b45-108">_i_</span></span>
  
<span data-ttu-id="33b45-109">预期的整数值。</span><span class="sxs-lookup"><span data-stu-id="33b45-109">The intended integer value.</span></span> <span data-ttu-id="33b45-110">请注意， **XLOPER**整数 16 位有符号的整数 (短 int)，而**XLOPER12**整数是一个有符号的 32 位整数 ([长] int)。</span><span class="sxs-lookup"><span data-stu-id="33b45-110">Note that the **XLOPER** integer is a signed 16-bit integer (short int), whereas the **XLOPER12** integer is a signed 32-bit integer ([long] int).</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="33b45-111">返回值</span><span class="sxs-lookup"><span data-stu-id="33b45-111">Return value</span></span>

<span data-ttu-id="33b45-112">返回一个包含中传递的值的**xltypeInt**整数。</span><span class="sxs-lookup"><span data-stu-id="33b45-112">Returns an **xltypeInt** integer containing the value passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="33b45-113">示例</span><span class="sxs-lookup"><span data-stu-id="33b45-113">Example</span></span>

<span data-ttu-id="33b45-114">本示例使用**TempInt12**函数将参数传递给**xlfGetWorkspace**。</span><span class="sxs-lookup"><span data-stu-id="33b45-114">This example uses the **TempInt12** function to pass an argument to **xlfGetWorkspace**.</span></span>
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempIntExample(void)
{
    XLOPER12 xRes;
    Excel12f(xlfGetWorkspace, (LPXLOPER12)&xRes, 1, TempInt12(44));
    Excel12f(xlFree, 0, 1, (LPXLOPER12)&xRes);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="33b45-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33b45-115">See also</span></span>



[<span data-ttu-id="33b45-116">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="33b45-116">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

