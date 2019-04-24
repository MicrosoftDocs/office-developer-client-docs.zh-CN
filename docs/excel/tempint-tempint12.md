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
- tempint12 函数 [excel 2007], TempInt 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 86d690b8-caca-450d-93f7-69ca4cd1a6e0
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 16a2222dbc51ad9480dbd5941ca2ed13f65b55e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310477"
---
# <a name="tempinttempint12"></a><span data-ttu-id="4802e-104">TempInt/TempInt12</span><span class="sxs-lookup"><span data-stu-id="4802e-104">TempInt/TempInt12</span></span>

 <span data-ttu-id="4802e-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4802e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="4802e-106">创建包含整数的临时**XLOPER**/ **XLOPER12**的框架库函数。</span><span class="sxs-lookup"><span data-stu-id="4802e-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** that contains an integer.</span></span> 
  
```cs
LPXLOPER TempInt(short int i);
LPXLOPER12 TempInt12(int i);
```

## <a name="parameters"></a><span data-ttu-id="4802e-107">参数</span><span class="sxs-lookup"><span data-stu-id="4802e-107">Parameters</span></span>

 <span data-ttu-id="4802e-108">_得到_</span><span class="sxs-lookup"><span data-stu-id="4802e-108">_i_</span></span>
  
<span data-ttu-id="4802e-109">所需的整数值。</span><span class="sxs-lookup"><span data-stu-id="4802e-109">The intended integer value.</span></span> <span data-ttu-id="4802e-110">请注意, **XLOPER** integer 是一个有符号的16位整数 (short int), 而**XLOPER12**整数是一个有符号的32位整数 ([long] int)。</span><span class="sxs-lookup"><span data-stu-id="4802e-110">Note that the **XLOPER** integer is a signed 16-bit integer (short int), whereas the **XLOPER12** integer is a signed 32-bit integer ([long] int).</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="4802e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4802e-111">Return value</span></span>

<span data-ttu-id="4802e-112">返回一个**xltypeInt**整数, 该整数包含传入的值。</span><span class="sxs-lookup"><span data-stu-id="4802e-112">Returns an **xltypeInt** integer containing the value passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="4802e-113">示例</span><span class="sxs-lookup"><span data-stu-id="4802e-113">Example</span></span>

<span data-ttu-id="4802e-114">此示例使用**TempInt12**函数将参数传递给**xlfGetWorkspace**。</span><span class="sxs-lookup"><span data-stu-id="4802e-114">This example uses the **TempInt12** function to pass an argument to **xlfGetWorkspace**.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="4802e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4802e-115">See also</span></span>



[<span data-ttu-id="4802e-116">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="4802e-116">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

