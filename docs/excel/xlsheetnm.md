---
title: xlSheetNm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSheetNm
keywords:
- xlsheetnm 函数 [excel 2007]
localization_priority: Normal
ms.assetid: bcb16207-5499-4474-b006-51ccde1002d7
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5d62be7ebef71547de3a903db4c1a030984b8640
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303869"
---
# <a name="xlsheetnm"></a><span data-ttu-id="c190e-104">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="c190e-104">xlSheetNm</span></span>

<span data-ttu-id="c190e-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c190e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c190e-106">返回包含在外部引用中的工作表或宏表的内部表 ID 中的名称, 或当前工作表的名称 (如果传递了内部引用)。</span><span class="sxs-lookup"><span data-stu-id="c190e-106">Returns the name of a worksheet or macro sheet from its internal sheet ID contained within an external reference, or the name of the current sheet if passed an internal reference.</span></span>
  
```cs
Excel12(xlSheetNm, LPXLOPER12 pxRes, 1, LPXLOPER12 pxExtref);
```

## <a name="parameters"></a><span data-ttu-id="c190e-107">参数</span><span class="sxs-lookup"><span data-stu-id="c190e-107">Parameters</span></span>

<span data-ttu-id="c190e-108">_pxExtref_(**xltypeRef**或**xltypeSRef**)</span><span class="sxs-lookup"><span data-stu-id="c190e-108">_pxExtref_ (**xltypeRef** or **xltypeSRef**)</span></span>
  
<span data-ttu-id="c190e-109">对需要其名称的工作表的引用。</span><span class="sxs-lookup"><span data-stu-id="c190e-109">A reference to the sheet whose name you want.</span></span>
  
<span data-ttu-id="c190e-110">如果要传递外部引用 (**xltypeRef**), 它只需要包含工作表的 ID。</span><span class="sxs-lookup"><span data-stu-id="c190e-110">If you are passing an external reference (**xltypeRef**) it need only contain the ID of the sheet.</span></span> <span data-ttu-id="c190e-111">对工作表上的单元格进行描述的数据结构将被忽略且无需提供。</span><span class="sxs-lookup"><span data-stu-id="c190e-111">The data structures that describe the cells on the worksheet are ignored and do not need to be provided.</span></span> <span data-ttu-id="c190e-112">如果将 ID 设置为零, **xlSheetNm**将返回当前工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="c190e-112">If the ID is set to zero, **xlSheetNm** returns the name of the current sheet.</span></span> 
  
<span data-ttu-id="c190e-113">如果传递的是内部引用 (**xltypeSef**), 则**xlSheetNm**将返回当前工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="c190e-113">If you are passing an internal reference (**xltypeSef**), **xlSheetNm** returns the name of the current sheet.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c190e-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="c190e-114">Property value/Return value</span></span>

<span data-ttu-id="c190e-115">返回窗体`[Book1]Sheet1`中的工作表名称 (**xltypeStr**)。</span><span class="sxs-lookup"><span data-stu-id="c190e-115">Returns the name of the sheet (**xltypeStr**) in the form  `[Book1]Sheet1`.</span></span>
  
## <a name="example"></a><span data-ttu-id="c190e-116">示例</span><span class="sxs-lookup"><span data-stu-id="c190e-116">Example</span></span>

<span data-ttu-id="c190e-117">下面的示例显示从中调用函数的工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="c190e-117">The following example displays the name of the sheet from which the function was called.</span></span> <span data-ttu-id="c190e-118">只有在执行 XLM 命令宏时从宏表中调用时, 函数才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="c190e-118">The function works correctly only if called from a macro sheet while executing an XLM command macro.</span></span> <span data-ttu-id="c190e-119">这是因为它调用**xlcAlert**, 这只是命令可以执行的操作, 而需要从工作表 (而不是对话框、菜单或命令栏) 中调用, 以便**xlfCaller**返回引用。</span><span class="sxs-lookup"><span data-stu-id="c190e-119">This is because it calls **xlcAlert**, which only commands can do, and it needs to be called from a sheet rather than a dialog box, menu, or command bar in order for **xlfCaller** to return a reference.</span></span> 
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlSheetNmExample(void)
{
   XLOPER12 xRes, xSheetName;
   Excel12(xlfCaller, &xRes, 0);
   Excel12(xlSheetNm, &xSheetName, 1, (LPXLOPER12)&xRes);
   Excel12(xlcAlert, 0, 1, (LPXLOPER12)&xSheetName);
   Excel12(xlFree, 0, 1, (LPXLOPER12)&xSheetName);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="c190e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c190e-120">See also</span></span>

- [<span data-ttu-id="c190e-121">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="c190e-121">xlSheetId</span></span>](xlsheetid.md)
- [<span data-ttu-id="c190e-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="c190e-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

