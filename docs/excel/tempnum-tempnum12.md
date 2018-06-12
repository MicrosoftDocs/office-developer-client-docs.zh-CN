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
- tempnum12 函数 [excel 2007，] TempNum 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 5b74d618-db3a-4d84-bd17-4fee7ae3b51e
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 5ebe58dba32c2cf0382bf0811713eaa0a5471dda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773818"
---
# <a name="tempnumtempnum12"></a><span data-ttu-id="45811-104">TempNum/TempNum12</span><span class="sxs-lookup"><span data-stu-id="45811-104">TempNum/TempNum12</span></span>

 <span data-ttu-id="45811-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="45811-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="45811-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**包含 Microsoft Excel 工作表数目 (IEEE 8 字节 double)。</span><span class="sxs-lookup"><span data-stu-id="45811-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** containing a Microsoft Excel worksheet number (an IEEE 8-byte double).</span></span> 
  
```cs
LPXLOPER TempNum(double d);
LPXLOPER12 TempNum12(double d);
```

## <a name="parameters"></a><span data-ttu-id="45811-107">参数</span><span class="sxs-lookup"><span data-stu-id="45811-107">Parameters</span></span>

 <span data-ttu-id="45811-108">_d_ (**double**)</span><span class="sxs-lookup"><span data-stu-id="45811-108">_d_ (**double**)</span></span>
  
<span data-ttu-id="45811-109">预期的值。</span><span class="sxs-lookup"><span data-stu-id="45811-109">The intended value.</span></span> <span data-ttu-id="45811-110">请注意，IEEE 子正常数字目前不支持四舍五入为零。</span><span class="sxs-lookup"><span data-stu-id="45811-110">Note that IEEE sub-normal numbers are not currently supported and are rounded to zero.</span></span> <span data-ttu-id="45811-111">支持无穷大负数。</span><span class="sxs-lookup"><span data-stu-id="45811-111">Negative infinity is supported.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="45811-112">返回值</span><span class="sxs-lookup"><span data-stu-id="45811-112">Return value</span></span>

<span data-ttu-id="45811-113">返回包含值的数值**xltypeNum**传入或零，如果已子正文中传递的值。</span><span class="sxs-lookup"><span data-stu-id="45811-113">Returns a numeric **xltypeNum** containing the value passed in or zero if the passed in value was sub-normal.</span></span> 
  
## <a name="example"></a><span data-ttu-id="45811-114">示例</span><span class="sxs-lookup"><span data-stu-id="45811-114">Example</span></span>

<span data-ttu-id="45811-115">本示例使用**TempNum12**函数将参数传递给**xlfGetWorkspace**。</span><span class="sxs-lookup"><span data-stu-id="45811-115">This example uses the **TempNum12** function to pass an argument to **xlfGetWorkspace**.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="45811-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45811-116">See also</span></span>



[<span data-ttu-id="45811-117">Framework 库中的函数</span><span class="sxs-lookup"><span data-stu-id="45811-117">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

