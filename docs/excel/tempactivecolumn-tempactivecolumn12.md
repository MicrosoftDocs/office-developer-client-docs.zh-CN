---
title: TempActiveColumn/TempActiveColumn12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveColumn
- TempActiveColumn12
keywords:
- tempactivecolumn12 函数 [excel 2007], TempActiveColumn 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 4b1f34c4-e7fa-4a0b-8fc5-c9d465ebb70c
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d1399a407e3e269b78c7afbde8ff32c126b4b1bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310469"
---
# <a name="tempactivecolumntempactivecolumn12"></a><span data-ttu-id="f373b-104">TempActiveColumn/TempActiveColumn12</span><span class="sxs-lookup"><span data-stu-id="f373b-104">TempActiveColumn/TempActiveColumn12</span></span>

 <span data-ttu-id="f373b-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f373b-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="f373b-106">框架库函数, 用于创建一个临时的**XLOPER**/ **XLOPER12** , 其中包含对活动工作表上的整个列的外部引用。</span><span class="sxs-lookup"><span data-stu-id="f373b-106">Framework library functions that create a temporary **XLOPER**/ **XLOPER12** containing an external reference to an entire column on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveColumn(BYTE col);
LPXLOPER12 TempActiveColumn12(COL col);
```

## <a name="parameters"></a><span data-ttu-id="f373b-107">参数</span><span class="sxs-lookup"><span data-stu-id="f373b-107">Parameters</span></span>

 <span data-ttu-id="f373b-108">_col_(**字节**)</span><span class="sxs-lookup"><span data-stu-id="f373b-108">_col_ (**BYTE**)</span></span>
  
<span data-ttu-id="f373b-109">要引用的列。</span><span class="sxs-lookup"><span data-stu-id="f373b-109">The column to be referenced.</span></span> <span data-ttu-id="f373b-110">这是从零开始的, 以便将列 A 作为0传递。</span><span class="sxs-lookup"><span data-stu-id="f373b-110">This is zero-based so that column A is passed as 0.</span></span> <span data-ttu-id="f373b-111">在 Microsoft Office Excel 2003 及更早版本中, 在兼容模式下运行工作簿的 excel 2007 中, 最大值为 255 = 2 ^ 8-1, 是字节整数可以采用的最大值。</span><span class="sxs-lookup"><span data-stu-id="f373b-111">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 255 = 2^8 - 1 and is the maximum value that can be taken by a BYTE integer.</span></span> <span data-ttu-id="f373b-112">从运行工作簿的 Excel 2007 开始, 最大值为 16383 = 2 ^ 14-1。</span><span class="sxs-lookup"><span data-stu-id="f373b-112">Starting in Excel 2007 running a workbook, the maximum value is 16,383 = 2^14 - 1.</span></span> <span data-ttu-id="f373b-113">COL 在 xlcall.h 中定义为32位有符号整数。水平.</span><span class="sxs-lookup"><span data-stu-id="f373b-113">COL is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="f373b-114">返回值</span><span class="sxs-lookup"><span data-stu-id="f373b-114">Return value</span></span>

<span data-ttu-id="f373b-115">返回对传入的列的**xltypeRef**外部引用。</span><span class="sxs-lookup"><span data-stu-id="f373b-115">Returns an **xltypeRef** external reference to the column passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f373b-116">示例</span><span class="sxs-lookup"><span data-stu-id="f373b-116">Example</span></span>

<span data-ttu-id="f373b-117">下面的示例使用**TempActiveColumn12**选择整个列 B。</span><span class="sxs-lookup"><span data-stu-id="f373b-117">The following example uses **TempActiveColumn12** to select the entire column B.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveColumnExample(void)
{
    Excel12f(xlcSelect, 0, 1, TempActiveColumn12(1));
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="f373b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f373b-118">See also</span></span>



[<span data-ttu-id="f373b-119">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="f373b-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

