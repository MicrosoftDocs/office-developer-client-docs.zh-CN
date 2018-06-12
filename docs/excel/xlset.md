---
title: xlset，则
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSet
keywords:
- xlset，则函数 [excel 2007]
localization_priority: Normal
ms.assetid: 121e6212-0692-4430-97be-4792b53719bf
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 63f50e441f5d851677f36754a17bcd6403705239
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773870"
---
# <a name="xlset"></a><span data-ttu-id="e05ba-104">xlset，则</span><span class="sxs-lookup"><span data-stu-id="e05ba-104">xlSet</span></span>

<span data-ttu-id="e05ba-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e05ba-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e05ba-106">很快将常量值放入单元格或区域。</span><span class="sxs-lookup"><span data-stu-id="e05ba-106">Puts constant values into cells or ranges very quickly.</span></span> <span data-ttu-id="e05ba-107">有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中的"xlset，则和带数组公式的工作簿"。</span><span class="sxs-lookup"><span data-stu-id="e05ba-107">For more information, see "xlSet and Workbooks with Array Formulas" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel12(xlSet, LPXLOPER12 pxRes, 2, LPXLOPER12 pxReference, LPXLOPER pxValue);
```

## <a name="parameters"></a><span data-ttu-id="e05ba-108">参数</span><span class="sxs-lookup"><span data-stu-id="e05ba-108">Parameters</span></span>

<span data-ttu-id="e05ba-109">_pxReference_（**xltypeRef**或**xltypeSRef**）</span><span class="sxs-lookup"><span data-stu-id="e05ba-109">_pxReference_ (**xltypeRef** or **xltypeSRef**)</span></span>
  
<span data-ttu-id="e05ba-110">一个描述目标单元格的矩形引用。</span><span class="sxs-lookup"><span data-stu-id="e05ba-110">A rectangular reference describing the target cell or cells.</span></span> <span data-ttu-id="e05ba-111">引用必须描述相邻单元格，因此，在**xltypeRef** `val.mref.lpmref->count`必须设置为 1。</span><span class="sxs-lookup"><span data-stu-id="e05ba-111">The reference must describe adjacent cells, so that in an **xltypeRef** `val.mref.lpmref->count` must be set to 1.</span></span> 
  
<span data-ttu-id="e05ba-112">_pxValue_</span><span class="sxs-lookup"><span data-stu-id="e05ba-112">_pxValue_</span></span>
  
<span data-ttu-id="e05ba-113">值或值放入单元格或单元格。</span><span class="sxs-lookup"><span data-stu-id="e05ba-113">The value or values to be placed into the cell or cells.</span></span> <span data-ttu-id="e05ba-114">有关详细信息，请参阅"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="e05ba-114">For more information, see the "Remarks" section.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e05ba-115">备注</span><span class="sxs-lookup"><span data-stu-id="e05ba-115">Remarks</span></span>

### <a name="pxvalue-argument"></a><span data-ttu-id="e05ba-116">pxValue 参数</span><span class="sxs-lookup"><span data-stu-id="e05ba-116">pxValue argument</span></span>

<span data-ttu-id="e05ba-117">_pxValue_可以是一个值或数组。</span><span class="sxs-lookup"><span data-stu-id="e05ba-117">_pxValue_ can either be a value or an array.</span></span> <span data-ttu-id="e05ba-118">如果它是一个值，该值与填充整个目标区域。</span><span class="sxs-lookup"><span data-stu-id="e05ba-118">If it is a value, the entire destination range is filled with that value.</span></span> <span data-ttu-id="e05ba-119">如果它是一个数组 (**xltypeMulti**)，该数组的元素放入该矩形中的相应位置。</span><span class="sxs-lookup"><span data-stu-id="e05ba-119">If it is an array (**xltypeMulti**), the elements of the array are put into the corresponding locations in the rectangle.</span></span>
  
<span data-ttu-id="e05ba-120">如果您的第二个参数中使用水平数组，它被重复下以填满整个矩形。</span><span class="sxs-lookup"><span data-stu-id="e05ba-120">If you use a horizontal array for the second argument, it is duplicated down to fill the entire rectangle.</span></span> <span data-ttu-id="e05ba-121">如果您使用垂直数组，它被重复右以填满整个矩形。</span><span class="sxs-lookup"><span data-stu-id="e05ba-121">If you use a vertical array, it is duplicated right to fill the entire rectangle.</span></span> <span data-ttu-id="e05ba-122">如果您使用的矩形的数组，并且它是要放入该矩形区域太小，则用 **# n/A**s 填充该区域。</span><span class="sxs-lookup"><span data-stu-id="e05ba-122">If you use a rectangular array, and it is too small for the rectangular range you want to put it in, that range is padded with **#N/A**s.</span></span>
  
<span data-ttu-id="e05ba-123">如果目标区域小于源数组，值将被复制中最多的目标区域的限制和额外数据将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e05ba-123">If the target range is smaller than the source array, the values are copied in up to the limits of the target range and the extra data are ignored.</span></span>
  
<span data-ttu-id="e05ba-124">若要清除的目标矩形元素，请使用源数组中的**xltypeNil**类型数组元素。</span><span class="sxs-lookup"><span data-stu-id="e05ba-124">To clear an element of the destination rectangle, use an **xltypeNil** type array element in the source array.</span></span> <span data-ttu-id="e05ba-125">若要清除整个目标矩形，省略第二个参数。</span><span class="sxs-lookup"><span data-stu-id="e05ba-125">To clear the entire destination rectangle, omit the second argument.</span></span> 
  
### <a name="restrictions"></a><span data-ttu-id="e05ba-126">限制</span><span class="sxs-lookup"><span data-stu-id="e05ba-126">Restrictions</span></span>

<span data-ttu-id="e05ba-127">**xlset，则**无法撤消。</span><span class="sxs-lookup"><span data-stu-id="e05ba-127">**xlSet** cannot be undone.</span></span> <span data-ttu-id="e05ba-128">此外，它销毁可能已前可用的任何撤消信息。</span><span class="sxs-lookup"><span data-stu-id="e05ba-128">In addition, it destroys any undo information that may have been available before.</span></span> 
  
<span data-ttu-id="e05ba-129">**xlset，则**可以将仅常量，不公式放入单元格。</span><span class="sxs-lookup"><span data-stu-id="e05ba-129">**xlSet** can put only constants, not formulas, into cells.</span></span> 
  
<span data-ttu-id="e05ba-130">作为类 3 命令等效函数; **xlset，则**行为即，它是仅在 DLL 可用，DLL 调用从对象、 宏、 菜单、 工具栏、 快捷键或在 （从开始在 Excel 2007 和**工具功能区上的**视图**选项卡访问**宏**对话框的**运行**按钮时**菜单早期版本中的)。</span><span class="sxs-lookup"><span data-stu-id="e05ba-130">**xlSet** behaves as a Class 3 command-equivalent function; that is, it is available only inside a DLL when the DLL is called from an object, macro, menu, toolbar, shortcut key, or the **Run** button in the **Macro** dialog box (accessed from **View** tab on the ribbon starting in Excel 2007, and the **Tools** menu in earlier versions).</span></span> 
  
## <a name="example"></a><span data-ttu-id="e05ba-131">示例</span><span class="sxs-lookup"><span data-stu-id="e05ba-131">Example</span></span>

<span data-ttu-id="e05ba-132">下面的示例填充 B205:B206 从宏中传递的值。</span><span class="sxs-lookup"><span data-stu-id="e05ba-132">The following example fills B205:B206 with the value that was passed in from a macro.</span></span> <span data-ttu-id="e05ba-133">此命令函数示例需要一个参数，并因此只能如果从 XLM 宏工作表，或从使用**Application.Run**方法 VBA 模块中调用。</span><span class="sxs-lookup"><span data-stu-id="e05ba-133">This command function example requires an argument, and so will only work if called from an XLM macro sheet, or from a VBA module using the **Application.Run** method.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="e05ba-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e05ba-134">See also</span></span>

- [<span data-ttu-id="e05ba-135">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="e05ba-135">xlCoerce</span></span>](xlcoerce.md)
- [<span data-ttu-id="e05ba-136">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="e05ba-136">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

