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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0912c1d40882933778d0df927ceb9de773063444
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303855"
---
# <a name="xlset"></a><span data-ttu-id="0e1de-104">xlSet</span><span class="sxs-lookup"><span data-stu-id="0e1de-104">xlSet</span></span>

<span data-ttu-id="0e1de-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0e1de-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="0e1de-106">快速将常量值放入单元格或区域。</span><span class="sxs-lookup"><span data-stu-id="0e1de-106">Puts constant values into cells or ranges very quickly.</span></span> <span data-ttu-id="0e1de-107">有关详细信息, 请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中的 "xlSet 和包含数组公式的工作簿"。</span><span class="sxs-lookup"><span data-stu-id="0e1de-107">For more information, see "xlSet and Workbooks with Array Formulas" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel12(xlSet, LPXLOPER12 pxRes, 2, LPXLOPER12 pxReference, LPXLOPER pxValue);
```

## <a name="parameters"></a><span data-ttu-id="0e1de-108">参数</span><span class="sxs-lookup"><span data-stu-id="0e1de-108">Parameters</span></span>

<span data-ttu-id="0e1de-109">_pxReference_(**xltypeRef**或**xltypeSRef**)</span><span class="sxs-lookup"><span data-stu-id="0e1de-109">_pxReference_ (**xltypeRef** or **xltypeSRef**)</span></span>
  
<span data-ttu-id="0e1de-110">描述目标单元格或单元格的矩形引用。</span><span class="sxs-lookup"><span data-stu-id="0e1de-110">A rectangular reference describing the target cell or cells.</span></span> <span data-ttu-id="0e1de-111">该引用必须描述相邻单元格, 因此在**xltypeRef** `val.mref.lpmref->count`中必须设置为1。</span><span class="sxs-lookup"><span data-stu-id="0e1de-111">The reference must describe adjacent cells, so that in an **xltypeRef** `val.mref.lpmref->count` must be set to 1.</span></span> 
  
<span data-ttu-id="0e1de-112">_pxValue_</span><span class="sxs-lookup"><span data-stu-id="0e1de-112">_pxValue_</span></span>
  
<span data-ttu-id="0e1de-113">要放入一个或多个单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="0e1de-113">The value or values to be placed into the cell or cells.</span></span> <span data-ttu-id="0e1de-114">有关详细信息，请参阅“注解”部分。</span><span class="sxs-lookup"><span data-stu-id="0e1de-114">For more information, see the "Remarks" section.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0e1de-115">注解</span><span class="sxs-lookup"><span data-stu-id="0e1de-115">Remarks</span></span>

### <a name="pxvalue-argument"></a><span data-ttu-id="0e1de-116">pxValue 参数</span><span class="sxs-lookup"><span data-stu-id="0e1de-116">pxValue argument</span></span>

<span data-ttu-id="0e1de-117">_pxValue_可以是一个值, 也可以是一个数组。</span><span class="sxs-lookup"><span data-stu-id="0e1de-117">_pxValue_ can either be a value or an array.</span></span> <span data-ttu-id="0e1de-118">如果是一个值, 则使用该值填充整个目标区域。</span><span class="sxs-lookup"><span data-stu-id="0e1de-118">If it is a value, the entire destination range is filled with that value.</span></span> <span data-ttu-id="0e1de-119">如果是数组 (**xltypeMulti**), 则将数组的元素放在矩形中的相应位置。</span><span class="sxs-lookup"><span data-stu-id="0e1de-119">If it is an array (**xltypeMulti**), the elements of the array are put into the corresponding locations in the rectangle.</span></span>
  
<span data-ttu-id="0e1de-120">如果对第二个参数使用水平数组, 则将其向下复制以填充整个矩形。</span><span class="sxs-lookup"><span data-stu-id="0e1de-120">If you use a horizontal array for the second argument, it is duplicated down to fill the entire rectangle.</span></span> <span data-ttu-id="0e1de-121">如果使用垂直数组, 则填充整个矩形的权限是重复的。</span><span class="sxs-lookup"><span data-stu-id="0e1de-121">If you use a vertical array, it is duplicated right to fill the entire rectangle.</span></span> <span data-ttu-id="0e1de-122">如果使用的是矩形数组, 并且对于要将其放入的矩形区域而言太小, 该范围将填充 **#N/a**s。</span><span class="sxs-lookup"><span data-stu-id="0e1de-122">If you use a rectangular array, and it is too small for the rectangular range you want to put it in, that range is padded with **#N/A**s.</span></span>
  
<span data-ttu-id="0e1de-123">如果目标区域小于源数组, 则会将这些值复制到目标区域的限制中, 并忽略额外的数据。</span><span class="sxs-lookup"><span data-stu-id="0e1de-123">If the target range is smaller than the source array, the values are copied in up to the limits of the target range and the extra data are ignored.</span></span>
  
<span data-ttu-id="0e1de-124">若要清除目标矩形的元素, 请在源数组中使用**xltypeNil**类型数组元素。</span><span class="sxs-lookup"><span data-stu-id="0e1de-124">To clear an element of the destination rectangle, use an **xltypeNil** type array element in the source array.</span></span> <span data-ttu-id="0e1de-125">若要清除整个目标矩形, 请省略第二个参数。</span><span class="sxs-lookup"><span data-stu-id="0e1de-125">To clear the entire destination rectangle, omit the second argument.</span></span> 
  
### <a name="restrictions"></a><span data-ttu-id="0e1de-126">条件</span><span class="sxs-lookup"><span data-stu-id="0e1de-126">Restrictions</span></span>

<span data-ttu-id="0e1de-127">**xlSet**无法撤消。</span><span class="sxs-lookup"><span data-stu-id="0e1de-127">**xlSet** cannot be undone.</span></span> <span data-ttu-id="0e1de-128">此外, 它还会销毁可能以前可用的任何撤消信息。</span><span class="sxs-lookup"><span data-stu-id="0e1de-128">In addition, it destroys any undo information that may have been available before.</span></span> 
  
<span data-ttu-id="0e1de-129">**xlSet**只能将常量 (而不是公式) 放入单元格。</span><span class="sxs-lookup"><span data-stu-id="0e1de-129">**xlSet** can put only constants, not formulas, into cells.</span></span> 
  
<span data-ttu-id="0e1de-130">**xlSet**的行为与 Class 3 命令等效的函数;也就是说, 在 dll 中的对象、宏、菜单、工具栏、快捷键或 "**运行**" 按钮 (从 Excel 2007 启动的功能区上的 "**视图**" 选项\*\*\*\* 卡中访问该对话框) 中调用 dll 时, 它将仅在 dll 内可用, 并且这些**工具**早期版本中的菜单)。</span><span class="sxs-lookup"><span data-stu-id="0e1de-130">**xlSet** behaves as a Class 3 command-equivalent function; that is, it is available only inside a DLL when the DLL is called from an object, macro, menu, toolbar, shortcut key, or the **Run** button in the **Macro** dialog box (accessed from **View** tab on the ribbon starting in Excel 2007, and the **Tools** menu in earlier versions).</span></span> 
  
## <a name="example"></a><span data-ttu-id="0e1de-131">示例</span><span class="sxs-lookup"><span data-stu-id="0e1de-131">Example</span></span>

<span data-ttu-id="0e1de-132">下面的示例使用从宏传入的值填充 B205: B206。</span><span class="sxs-lookup"><span data-stu-id="0e1de-132">The following example fills B205:B206 with the value that was passed in from a macro.</span></span> <span data-ttu-id="0e1de-133">此命令函数示例需要一个参数, 因此仅当从 XLM 宏工作表调用, 或使用**Application. Run**方法从 VBA 模块中调用时, 才会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0e1de-133">This command function example requires an argument, and so will only work if called from an XLM macro sheet, or from a VBA module using the **Application.Run** method.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="0e1de-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e1de-134">See also</span></span>

- [<span data-ttu-id="0e1de-135">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="0e1de-135">xlCoerce</span></span>](xlcoerce.md)
- [<span data-ttu-id="0e1de-136">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="0e1de-136">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

