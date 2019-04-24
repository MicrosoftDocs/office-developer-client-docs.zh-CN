---
title: TempActiveRow/TempActiveRow12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveRow
- TempActiveRow12
keywords:
- tempactiverow 函数 [excel 2007], TempActiveRow12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: cbb9181c-59b0-4133-a085-94a94ac3f229
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 1f89c458a521b41e4f172f8a6c53526440bb472b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310414"
---
# <a name="tempactiverowtempactiverow12"></a><span data-ttu-id="46af6-104">TempActiveRow/TempActiveRow12</span><span class="sxs-lookup"><span data-stu-id="46af6-104">TempActiveRow/TempActiveRow12</span></span>

 <span data-ttu-id="46af6-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="46af6-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="46af6-106">框架库函数, 用于创建一个临时的**XLOPER**/ **XLOPER12** , 其中包含对活动工作表中整行的外部引用。</span><span class="sxs-lookup"><span data-stu-id="46af6-106">Framework library functions that create a temporary **XLOPER**/ **XLOPER12** containing an external reference to an entire row on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveRow(WORD row);
LPXLOPER12 TempActiveRow12(ROW row);
```

## <a name="parameters"></a><span data-ttu-id="46af6-107">参数</span><span class="sxs-lookup"><span data-stu-id="46af6-107">Parameters</span></span>

 <span data-ttu-id="46af6-108">_行_</span><span class="sxs-lookup"><span data-stu-id="46af6-108">_row_</span></span>
  
<span data-ttu-id="46af6-109">要引用的行。</span><span class="sxs-lookup"><span data-stu-id="46af6-109">The row to be referenced.</span></span> <span data-ttu-id="46af6-110">行参数从零开始, 以便将行1作为0传递。</span><span class="sxs-lookup"><span data-stu-id="46af6-110">Row arguments are zero-based so that row 1 is passed as 0.</span></span> <span data-ttu-id="46af6-111">在 Microsoft Office Excel 2003 及更早版本中, 在兼容模式下运行工作簿的 excel 2007 中, 最大值为 65535 = 2 ^ 16-1, 是单词整数可以采用的最大值。</span><span class="sxs-lookup"><span data-stu-id="46af6-111">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 65,535 = 2^16 - 1 and is the maximum value that can be taken by a WORD integer.</span></span> <span data-ttu-id="46af6-112">从运行工作簿的 Excel 2007 开始, 最大值为 1048575 = 2 ^ 20-1。</span><span class="sxs-lookup"><span data-stu-id="46af6-112">Starting in Excel 2007 running a workbook, the maximum value is 1,048,575 = 2^20 - 1.</span></span> <span data-ttu-id="46af6-113">RW 在 xlcall.h 中定义为32位有符号整数。水平.</span><span class="sxs-lookup"><span data-stu-id="46af6-113">RW is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="46af6-114">返回值</span><span class="sxs-lookup"><span data-stu-id="46af6-114">Return value</span></span>

<span data-ttu-id="46af6-115">返回对传入的行单元格的**xltypeRef**外部引用。</span><span class="sxs-lookup"><span data-stu-id="46af6-115">Returns an **xltypeRef** external reference to row cells passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="46af6-116">示例</span><span class="sxs-lookup"><span data-stu-id="46af6-116">Example</span></span>

<span data-ttu-id="46af6-117">此示例使用**TempActiveRow12**函数选择行113。</span><span class="sxs-lookup"><span data-stu-id="46af6-117">This example uses the **TempActiveRow12** function to select row 113.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveRowExample(void)
{
   Excel12f(xlcSelect, 0, 1, TempActiveRow12(112));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="46af6-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46af6-118">See also</span></span>



[<span data-ttu-id="46af6-119">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="46af6-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

