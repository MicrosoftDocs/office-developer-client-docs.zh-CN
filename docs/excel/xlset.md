---
title: xlSet
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSet
keywords:
- xlset 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 121e6212-0692-4430-97be-4792b53719bf
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0912c1d40882933778d0df927ceb9de773063444
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404601"
---
# <a name="xlset"></a><span data-ttu-id="be319-104">xlSet</span><span class="sxs-lookup"><span data-stu-id="be319-104">xlSet</span></span>

<span data-ttu-id="be319-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="be319-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="be319-106">非常快速地将常量值放入单元格或区域。</span><span class="sxs-lookup"><span data-stu-id="be319-106">Puts constant values into cells or ranges very quickly.</span></span> <span data-ttu-id="be319-107">有关详细信息，请参阅 Excel XLL 开发中的已知问题中的"xlSet 和包含数组公式的[工作簿"。](known-issues-in-excel-xll-development.md)</span><span class="sxs-lookup"><span data-stu-id="be319-107">For more information, see "xlSet and Workbooks with Array Formulas" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel12(xlSet, LPXLOPER12 pxRes, 2, LPXLOPER12 pxReference, LPXLOPER pxValue);
```

## <a name="parameters"></a><span data-ttu-id="be319-108">参数</span><span class="sxs-lookup"><span data-stu-id="be319-108">Parameters</span></span>

<span data-ttu-id="be319-109">_pxReference_ (**xltypeRef** 或 **xltypeSRef**) </span><span class="sxs-lookup"><span data-stu-id="be319-109">_pxReference_ (**xltypeRef** or **xltypeSRef**)</span></span>
  
<span data-ttu-id="be319-110">描述目标单元格的矩形引用。</span><span class="sxs-lookup"><span data-stu-id="be319-110">A rectangular reference describing the target cell or cells.</span></span> <span data-ttu-id="be319-111">引用必须描述相邻的单元格，以便 **xltypeRef** `val.mref.lpmref->count` 中必须设置为 1。</span><span class="sxs-lookup"><span data-stu-id="be319-111">The reference must describe adjacent cells, so that in an **xltypeRef** `val.mref.lpmref->count` must be set to 1.</span></span> 
  
<span data-ttu-id="be319-112">_pxValue_</span><span class="sxs-lookup"><span data-stu-id="be319-112">_pxValue_</span></span>
  
<span data-ttu-id="be319-113">要放入单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="be319-113">The value or values to be placed into the cell or cells.</span></span> <span data-ttu-id="be319-114">有关详细信息，请参阅“注解”部分。</span><span class="sxs-lookup"><span data-stu-id="be319-114">For more information, see the "Remarks" section.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="be319-115">备注</span><span class="sxs-lookup"><span data-stu-id="be319-115">Remarks</span></span>

### <a name="pxvalue-argument"></a><span data-ttu-id="be319-116">pxValue 参数</span><span class="sxs-lookup"><span data-stu-id="be319-116">pxValue argument</span></span>

<span data-ttu-id="be319-117">_pxValue_ 可以是值，也可以为数组。</span><span class="sxs-lookup"><span data-stu-id="be319-117">_pxValue_ can either be a value or an array.</span></span> <span data-ttu-id="be319-118">如果是值，则使用该值填充整个目标区域。</span><span class="sxs-lookup"><span data-stu-id="be319-118">If it is a value, the entire destination range is filled with that value.</span></span> <span data-ttu-id="be319-119">如果它是 **xltypeMulti** (数组，) 元素将放入矩形中的相应位置。</span><span class="sxs-lookup"><span data-stu-id="be319-119">If it is an array (**xltypeMulti**), the elements of the array are put into the corresponding locations in the rectangle.</span></span>
  
<span data-ttu-id="be319-120">如果将水平数组用于第二个参数，则向下复制该数组以填充整个矩形。</span><span class="sxs-lookup"><span data-stu-id="be319-120">If you use a horizontal array for the second argument, it is duplicated down to fill the entire rectangle.</span></span> <span data-ttu-id="be319-121">如果使用垂直数组，则向右复制该数组以填充整个矩形。</span><span class="sxs-lookup"><span data-stu-id="be319-121">If you use a vertical array, it is duplicated right to fill the entire rectangle.</span></span> <span data-ttu-id="be319-122">如果使用矩形数组，并且对于要放入的矩形区域来说太小，则使用 **#N/A** 填充该区域。</span><span class="sxs-lookup"><span data-stu-id="be319-122">If you use a rectangular array, and it is too small for the rectangular range you want to put it in, that range is padded with **#N/A** s.</span></span>
  
<span data-ttu-id="be319-123">如果目标区域小于源数组，则最多复制目标区域限制的值，并忽略额外的数据。</span><span class="sxs-lookup"><span data-stu-id="be319-123">If the target range is smaller than the source array, the values are copied in up to the limits of the target range and the extra data are ignored.</span></span>
  
<span data-ttu-id="be319-124">若要清除目标矩形的元素，请使用源数组中的 **xltypeNil** 类型数组元素。</span><span class="sxs-lookup"><span data-stu-id="be319-124">To clear an element of the destination rectangle, use an **xltypeNil** type array element in the source array.</span></span> <span data-ttu-id="be319-125">若要清除整个目标矩形，请省略第二个参数。</span><span class="sxs-lookup"><span data-stu-id="be319-125">To clear the entire destination rectangle, omit the second argument.</span></span> 
  
### <a name="restrictions"></a><span data-ttu-id="be319-126">限制</span><span class="sxs-lookup"><span data-stu-id="be319-126">Restrictions</span></span>

<span data-ttu-id="be319-127">**xlSet** 无法撤消。</span><span class="sxs-lookup"><span data-stu-id="be319-127">**xlSet** cannot be undone.</span></span> <span data-ttu-id="be319-128">此外，它销毁之前可能提供的任何撤消信息。</span><span class="sxs-lookup"><span data-stu-id="be319-128">In addition, it destroys any undo information that may have been available before.</span></span> 
  
<span data-ttu-id="be319-129">**xlSet** 只能将常量而不是公式放入单元格中。</span><span class="sxs-lookup"><span data-stu-id="be319-129">**xlSet** can put only constants, not formulas, into cells.</span></span> 
  
<span data-ttu-id="be319-130">**xlSet** 的行为与 Class 3 命令等效函数;也就是说，从从 Excel 2007 开始从功能区上的"视图"选项卡访问的"宏"对话框 (中的"运行"按钮和早期版本的) 中的"工具"菜单调用 DLL 时，仅在 DLL 内可用。 </span><span class="sxs-lookup"><span data-stu-id="be319-130">**xlSet** behaves as a Class 3 command-equivalent function; that is, it is available only inside a DLL when the DLL is called from an object, macro, menu, toolbar, shortcut key, or the **Run** button in the **Macro** dialog box (accessed from **View** tab on the ribbon starting in Excel 2007, and the **Tools** menu in earlier versions).</span></span> 
  
## <a name="example"></a><span data-ttu-id="be319-131">示例</span><span class="sxs-lookup"><span data-stu-id="be319-131">Example</span></span>

<span data-ttu-id="be319-132">下面的示例使用从宏传入的值填充 B205：B206。</span><span class="sxs-lookup"><span data-stu-id="be319-132">The following example fills B205:B206 with the value that was passed in from a macro.</span></span> <span data-ttu-id="be319-133">此命令函数示例需要参数，因此仅在从 XLM 宏工作表或使用 **Application.Run** 方法的 VBA 模块调用时适用。</span><span class="sxs-lookup"><span data-stu-id="be319-133">This command function example requires an argument, and so will only work if called from an XLM macro sheet, or from a VBA module using the **Application.Run** method.</span></span> 
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlSetExample(short int iVal)
{
   XLOPER12 xRef, xValue;
   xRef.xltype = xltypeSRef;
   xRef.val.sref.count = 1;
   xRef.val.sref.ref.rwFirst = 204;
   xRef.val.sref.ref.rwLast = 205;
   xRef.val.sref.ref.colFirst = 1;
   xRef.val.sref.ref.colLast = 1;
   xValue.xltype = xltypeInt;
   xValue.val.w = iVal;
   Excel12(xlSet, 0, 2, (LPXLOPER12)&xRef, (LPXLOPER12)&xValue);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="be319-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be319-134">See also</span></span>

- [<span data-ttu-id="be319-135">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="be319-135">xlCoerce</span></span>](xlcoerce.md)
- [<span data-ttu-id="be319-136">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="be319-136">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

