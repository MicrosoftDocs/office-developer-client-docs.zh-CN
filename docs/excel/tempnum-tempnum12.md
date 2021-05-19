---
title: TempNum/TempNum12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempNum
- TempNum12
keywords:
- tempnum12 函数 [excel 2007]，TempNum 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 5b74d618-db3a-4d84-bd17-4fee7ae3b51e
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: cabd44ab828a2cfe22253e9aaf12abf7b7709d69
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426630"
---
# <a name="tempnumtempnum12"></a><span data-ttu-id="994f7-104">TempNum/TempNum12</span><span class="sxs-lookup"><span data-stu-id="994f7-104">TempNum/TempNum12</span></span>

 <span data-ttu-id="994f7-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="994f7-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="994f7-106">创建临时 /  **XLOPER XLOPER12** 的框架库函数，其中包含 IEEE Microsoft Excel 8 字节 (的工作表) 。</span><span class="sxs-lookup"><span data-stu-id="994f7-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** containing a Microsoft Excel worksheet number (an IEEE 8-byte double).</span></span> 
  
```cs
LPXLOPER TempNum(double d);
LPXLOPER12 TempNum12(double d);
```

## <a name="parameters"></a><span data-ttu-id="994f7-107">参数</span><span class="sxs-lookup"><span data-stu-id="994f7-107">Parameters</span></span>

 <span data-ttu-id="994f7-108">_d_ (**double)**</span><span class="sxs-lookup"><span data-stu-id="994f7-108">_d_ (**double**)</span></span>
  
<span data-ttu-id="994f7-109">预期值。</span><span class="sxs-lookup"><span data-stu-id="994f7-109">The intended value.</span></span> <span data-ttu-id="994f7-110">请注意，IEEE 次正常数字当前不受支持，并且四舍五入为零。</span><span class="sxs-lookup"><span data-stu-id="994f7-110">Note that IEEE sub-normal numbers are not currently supported and are rounded to zero.</span></span> <span data-ttu-id="994f7-111">支持负无穷大。</span><span class="sxs-lookup"><span data-stu-id="994f7-111">Negative infinity is supported.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="994f7-112">返回值</span><span class="sxs-lookup"><span data-stu-id="994f7-112">Return value</span></span>

<span data-ttu-id="994f7-113">返回一个 **数值 xltypeNum，** 如果传入的值是次正常值，则包含传入或零的值。</span><span class="sxs-lookup"><span data-stu-id="994f7-113">Returns a numeric **xltypeNum** containing the value passed in or zero if the passed in value was sub-normal.</span></span> 
  
## <a name="example"></a><span data-ttu-id="994f7-114">示例</span><span class="sxs-lookup"><span data-stu-id="994f7-114">Example</span></span>

<span data-ttu-id="994f7-115">此示例使用 **TempNum12** 函数将参数传递给 **xlfGetWorkspace**。</span><span class="sxs-lookup"><span data-stu-id="994f7-115">This example uses the **TempNum12** function to pass an argument to **xlfGetWorkspace**.</span></span>
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempNumExample(void)
{
   XLOPER12 xRes;
   Excel12f(xlfGetWorkspace, &xRes, 1, TempNum12(44));
   Excel12f(xlFree, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="994f7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="994f7-116">See also</span></span>



[<span data-ttu-id="994f7-117">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="994f7-117">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

