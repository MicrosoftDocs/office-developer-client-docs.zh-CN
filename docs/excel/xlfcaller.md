---
title: xlfCaller
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfCaller
keywords:
- xlfcaller 函数 [excel 2007]
localization_priority: Normal
ms.assetid: de4b119c-ae2e-4207-9783-8d5692a4d052
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 92d2d1877d7b315d178ef1fa36b47bd5f9f8e661
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773838"
---
# <a name="xlfcaller"></a><span data-ttu-id="c3dce-104">xlfCaller</span><span class="sxs-lookup"><span data-stu-id="c3dce-104">xlfCaller</span></span>

 <span data-ttu-id="c3dce-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c3dce-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c3dce-106">返回有关单元格、 单元格、 命令范围在菜单上，在工具栏上或调用 DLL 命令或函数当前正在运行的对象上的工具的信息。</span><span class="sxs-lookup"><span data-stu-id="c3dce-106">Returns information about the cell, range of cells, command on a menu, tool on a toolbar, or object that called the DLL command or function that is currently running.</span></span>
  
|<span data-ttu-id="c3dce-107">**从代码调用**</span><span class="sxs-lookup"><span data-stu-id="c3dce-107">**Code called from**</span></span>|<span data-ttu-id="c3dce-108">**返回**</span><span class="sxs-lookup"><span data-stu-id="c3dce-108">**Returns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c3dce-109">DLL</span><span class="sxs-lookup"><span data-stu-id="c3dce-109">DLL</span></span>  <br/> |<span data-ttu-id="c3dce-110">注册 id。</span><span class="sxs-lookup"><span data-stu-id="c3dce-110">The Register ID.</span></span>  <br/> |
|<span data-ttu-id="c3dce-111">单个单元格</span><span class="sxs-lookup"><span data-stu-id="c3dce-111">A single cell</span></span>  <br/> |<span data-ttu-id="c3dce-112">单个单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c3dce-112">A single-cell reference.</span></span>  <br/> |
|<span data-ttu-id="c3dce-113">多单元格的数组公式</span><span class="sxs-lookup"><span data-stu-id="c3dce-113">A multi-cell array formula</span></span>  <br/> |<span data-ttu-id="c3dce-114">一个多单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c3dce-114">A multi-cell reference.</span></span>  <br/> |
|<span data-ttu-id="c3dce-115">条件格式表达式</span><span class="sxs-lookup"><span data-stu-id="c3dce-115">A conditional formatting expression</span></span>  <br/> |<span data-ttu-id="c3dce-116">对条件格式应用于的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c3dce-116">A reference to the cell to which the formatting condition is applied.</span></span>  <br/> |
|<span data-ttu-id="c3dce-117">菜单</span><span class="sxs-lookup"><span data-stu-id="c3dce-117">A menu</span></span>  <br/> | <span data-ttu-id="c3dce-118">四个元素单行数组：</span><span class="sxs-lookup"><span data-stu-id="c3dce-118">A four-element single-row array:</span></span>  <br/>  <span data-ttu-id="c3dce-119">条形图的 id。</span><span class="sxs-lookup"><span data-stu-id="c3dce-119">The bar ID.</span></span>  <br/>  <span data-ttu-id="c3dce-120">菜单位置。</span><span class="sxs-lookup"><span data-stu-id="c3dce-120">The menu position.</span></span>  <br/>  <span data-ttu-id="c3dce-121">子菜单位置。</span><span class="sxs-lookup"><span data-stu-id="c3dce-121">The submenu position.</span></span>  <br/>  <span data-ttu-id="c3dce-122">命令位置。</span><span class="sxs-lookup"><span data-stu-id="c3dce-122">The command position.</span></span>  <br/> |
|<span data-ttu-id="c3dce-123">工具栏</span><span class="sxs-lookup"><span data-stu-id="c3dce-123">A toolbar</span></span>  <br/> | <span data-ttu-id="c3dce-124">两个元素的单行数组：</span><span class="sxs-lookup"><span data-stu-id="c3dce-124">A two-element single-row array:</span></span>  <br/>  <span data-ttu-id="c3dce-125">内置工具栏或自定义工具栏的工具栏名称工具栏数。</span><span class="sxs-lookup"><span data-stu-id="c3dce-125">The toolbar number for built-in toolbars or the toolbar name for custom toolbars.</span></span>  <br/>  <span data-ttu-id="c3dce-126">在工具栏上的位置。</span><span class="sxs-lookup"><span data-stu-id="c3dce-126">The position on the toolbar.</span></span>  <br/> |
|<span data-ttu-id="c3dce-127">Graphic 对象</span><span class="sxs-lookup"><span data-stu-id="c3dce-127">A graphic object</span></span>  <br/> |<span data-ttu-id="c3dce-128">对象标识符 （对象名称） 中。</span><span class="sxs-lookup"><span data-stu-id="c3dce-128">The object identifier (object name).</span></span>  <br/> |
|<span data-ttu-id="c3dce-129">在与 xlcOnEnter，关联的命令。输入，事件陷阱</span><span class="sxs-lookup"><span data-stu-id="c3dce-129">A command associated with an xlcOnEnter, ON.ENTER, event trap</span></span>  <br/> |<span data-ttu-id="c3dce-130">对正在输入的单元格的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c3dce-130">A reference to the cell or cells being entered.</span></span>  <br/> |
|<span data-ttu-id="c3dce-131">在与 xlcOnDoubleclick，关联的命令。DOUBLECLICK，事件陷阱。</span><span class="sxs-lookup"><span data-stu-id="c3dce-131">A command associated with an xlcOnDoubleclick, ON.DOUBLECLICK, event trap.</span></span>  <br/> |<span data-ttu-id="c3dce-132">单元格，双击 （不一定是活动单元格）。</span><span class="sxs-lookup"><span data-stu-id="c3dce-132">The cell that was double-clicked (not necessarily the active cell).</span></span>  <br/> |
|<span data-ttu-id="c3dce-133">Auto_Open、 AutoClose、 Auto_Activate 或 Auto_Deactivate 宏</span><span class="sxs-lookup"><span data-stu-id="c3dce-133">Auto_Open, AutoClose, Auto_Activate or Auto_Deactivate macro</span></span>  <br/> |<span data-ttu-id="c3dce-134">调用的工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="c3dce-134">The name of the calling sheet.</span></span>  <br/> |
|<span data-ttu-id="c3dce-135">未列出的其他方法</span><span class="sxs-lookup"><span data-stu-id="c3dce-135">Other methods not listed</span></span>  <br/> |<span data-ttu-id="c3dce-136">#REF!</span><span class="sxs-lookup"><span data-stu-id="c3dce-136">#REF!</span></span> <span data-ttu-id="c3dce-137">错误。</span><span class="sxs-lookup"><span data-stu-id="c3dce-137">Error.</span></span>  <br/> |
   
```cs
Excel12(xlfCaller, (LPXLOPER12) pxRes,0);
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="c3dce-138">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="c3dce-138">Property value/Return value</span></span>

<span data-ttu-id="c3dce-139">返回值是以下**XLOPER**之一/ **XLOPER12**数据类型： **xltypeRef**、 **xltypeSRef**、 **xltypeNum**、 **xltypeStr**、 **xltypeErr**或**xltypeMulti**。</span><span class="sxs-lookup"><span data-stu-id="c3dce-139">The return value is one of the following **XLOPER**/ **XLOPER12** data types: **xltypeRef**, **xltypeSRef**, **xltypeNum**, **xltypeStr**, **xltypeErr**, or **xltypeMulti**.</span></span> <span data-ttu-id="c3dce-140">由于这些类型的三个指向分配的内存， **xlfCaller**的返回值应总是释放[xlFree 函数](xlfree.md)调用中，当不再需要时。</span><span class="sxs-lookup"><span data-stu-id="c3dce-140">Since three of these types point to allocated memory, the return value of **xlfCaller** should always be freed in a call to the [xlFree function](xlfree.md) when it is no longer needed.</span></span> 
  
<span data-ttu-id="c3dce-141">有关**XLOPERs**/ **XLOPER12s** ，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="c3dce-141">For more information about **XLOPERs**/ **XLOPER12s** see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c3dce-142">说明</span><span class="sxs-lookup"><span data-stu-id="c3dce-142">Remarks</span></span>

<span data-ttu-id="c3dce-143">此函数是可从 DLL/XLL 工作表函数调用仅非-工作表函数。</span><span class="sxs-lookup"><span data-stu-id="c3dce-143">This function is the only non-worksheet function that can be called from a DLL/XLL worksheet function.</span></span> <span data-ttu-id="c3dce-144">只能从命令或宏表等效调用其他 XLM 信息函数函数。</span><span class="sxs-lookup"><span data-stu-id="c3dce-144">Other XLM information functions can only be called from commands or macro-sheet equivalent functions.</span></span>
  
## <a name="example"></a><span data-ttu-id="c3dce-145">示例</span><span class="sxs-lookup"><span data-stu-id="c3dce-145">Example</span></span>

 <span data-ttu-id="c3dce-146">`\SAMPLES\EXAMPLE\EXAMPLE.C`.</span><span class="sxs-lookup"><span data-stu-id="c3dce-146"></span></span> <span data-ttu-id="c3dce-147">此函数调用命令宏 (xlcSelect)，并将正常工作，仅当调用从宏表。</span><span class="sxs-lookup"><span data-stu-id="c3dce-147">This function calls a command macro (xlcSelect) and will work correctly only when called from a macro sheet.</span></span>
  
```cs
short WINAPI CallerExample(void)
{
   XLOPER12 xRes;
   Excel12(xlfCaller, &xRes, 0);
   Excel12(xlcSelect, 0, 1, (LPXLOPER12)&xRes);
   Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="c3dce-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3dce-148">See also</span></span>



[<span data-ttu-id="c3dce-149">基本的有用 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="c3dce-149">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

