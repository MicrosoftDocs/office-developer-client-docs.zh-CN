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
- tempactiverow 函数 [excel 2007，] TempActiveRow12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: cbb9181c-59b0-4133-a085-94a94ac3f229
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: a406d6e5a8ffa91e103276cb39230058b4840614
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773811"
---
# <a name="tempactiverowtempactiverow12"></a><span data-ttu-id="6369d-104">TempActiveRow/TempActiveRow12</span><span class="sxs-lookup"><span data-stu-id="6369d-104">TempActiveRow/TempActiveRow12</span></span>

 <span data-ttu-id="6369d-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6369d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="6369d-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**包含对活动工作表的整行的外部引用。</span><span class="sxs-lookup"><span data-stu-id="6369d-106">Framework library functions that create a temporary **XLOPER**/ **XLOPER12** containing an external reference to an entire row on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveRow(WORD row);
LPXLOPER12 TempActiveRow12(ROW row);
```

## <a name="parameters"></a><span data-ttu-id="6369d-107">参数</span><span class="sxs-lookup"><span data-stu-id="6369d-107">Parameters</span></span>

 <span data-ttu-id="6369d-108">_行_</span><span class="sxs-lookup"><span data-stu-id="6369d-108">_row_</span></span>
  
<span data-ttu-id="6369d-109">要引用的行。</span><span class="sxs-lookup"><span data-stu-id="6369d-109">The row to be referenced.</span></span> <span data-ttu-id="6369d-110">行参数是从零开始的所以第 1 行传递为 0。</span><span class="sxs-lookup"><span data-stu-id="6369d-110">Row arguments are zero-based so that row 1 is passed as 0.</span></span> <span data-ttu-id="6369d-111">在 Microsoft Office Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 65535 = 2 ^16-1，WORD 整数可以采取的最大值。</span><span class="sxs-lookup"><span data-stu-id="6369d-111">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 65,535 = 2^16 - 1 and is the maximum value that can be taken by a WORD integer.</span></span> <span data-ttu-id="6369d-112">启动运行工作簿的 Excel 2007 中的最大值是 1048575 = 2 ^20-1。</span><span class="sxs-lookup"><span data-stu-id="6369d-112">Starting in Excel 2007 running a workbook, the maximum value is 1,048,575 = 2^20 - 1.</span></span> <span data-ttu-id="6369d-113">RW 被定义为 XLCALL 中的 32 位有符号整数。H。</span><span class="sxs-lookup"><span data-stu-id="6369d-113">RW is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="6369d-114">返回值</span><span class="sxs-lookup"><span data-stu-id="6369d-114">Return value</span></span>

<span data-ttu-id="6369d-115">返回对传入的行单元格的**xltypeRef**外部引用。</span><span class="sxs-lookup"><span data-stu-id="6369d-115">Returns an **xltypeRef** external reference to row cells passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="6369d-116">示例</span><span class="sxs-lookup"><span data-stu-id="6369d-116">Example</span></span>

<span data-ttu-id="6369d-117">本示例使用**TempActiveRow12**函数选择行 113。</span><span class="sxs-lookup"><span data-stu-id="6369d-117">This example uses the **TempActiveRow12** function to select row 113.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveRowExample(void)
{
   Excel12f(xlcSelect, 0, 1, TempActiveRow12(112));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="6369d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6369d-118">See also</span></span>



[<span data-ttu-id="6369d-119">Framework 库中的函数</span><span class="sxs-lookup"><span data-stu-id="6369d-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

