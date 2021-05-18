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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fb788375504cefab75fde9513147c1d54acdaa07
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405728"
---
# <a name="xlfcaller"></a><span data-ttu-id="ccb14-104">xlfCaller</span><span class="sxs-lookup"><span data-stu-id="ccb14-104">xlfCaller</span></span>

 <span data-ttu-id="ccb14-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ccb14-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="ccb14-106">返回有关单元格、单元格区域、菜单上的命令、工具栏上的工具或调用 DLL 命令或当前正在运行的函数的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="ccb14-106">Returns information about the cell, range of cells, command on a menu, tool on a toolbar, or object that called the DLL command or function that is currently running.</span></span>
  
|<span data-ttu-id="ccb14-107">**从 中调用的代码**</span><span class="sxs-lookup"><span data-stu-id="ccb14-107">**Code called from**</span></span>|<span data-ttu-id="ccb14-108">**返回**</span><span class="sxs-lookup"><span data-stu-id="ccb14-108">**Returns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ccb14-109">DLL</span><span class="sxs-lookup"><span data-stu-id="ccb14-109">DLL</span></span>  <br/> |<span data-ttu-id="ccb14-110">注册 ID。</span><span class="sxs-lookup"><span data-stu-id="ccb14-110">The Register ID.</span></span>  <br/> |
|<span data-ttu-id="ccb14-111">单个单元格</span><span class="sxs-lookup"><span data-stu-id="ccb14-111">A single cell</span></span>  <br/> |<span data-ttu-id="ccb14-112">单单元格引用。</span><span class="sxs-lookup"><span data-stu-id="ccb14-112">A single-cell reference.</span></span>  <br/> |
|<span data-ttu-id="ccb14-113">多单元格数组公式</span><span class="sxs-lookup"><span data-stu-id="ccb14-113">A multi-cell array formula</span></span>  <br/> |<span data-ttu-id="ccb14-114">多单元格引用。</span><span class="sxs-lookup"><span data-stu-id="ccb14-114">A multi-cell reference.</span></span>  <br/> |
|<span data-ttu-id="ccb14-115">条件格式表达式</span><span class="sxs-lookup"><span data-stu-id="ccb14-115">A conditional formatting expression</span></span>  <br/> |<span data-ttu-id="ccb14-116">对应用格式条件的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="ccb14-116">A reference to the cell to which the formatting condition is applied.</span></span>  <br/> |
|<span data-ttu-id="ccb14-117">菜单</span><span class="sxs-lookup"><span data-stu-id="ccb14-117">A menu</span></span>  <br/> | <span data-ttu-id="ccb14-118">四元素单行数组：</span><span class="sxs-lookup"><span data-stu-id="ccb14-118">A four-element single-row array:</span></span>  <br/>  <span data-ttu-id="ccb14-119">条形图 ID。</span><span class="sxs-lookup"><span data-stu-id="ccb14-119">The bar ID.</span></span>  <br/>  <span data-ttu-id="ccb14-120">菜单位置。</span><span class="sxs-lookup"><span data-stu-id="ccb14-120">The menu position.</span></span>  <br/>  <span data-ttu-id="ccb14-121">子menu 位置。</span><span class="sxs-lookup"><span data-stu-id="ccb14-121">The submenu position.</span></span>  <br/>  <span data-ttu-id="ccb14-122">命令位置。</span><span class="sxs-lookup"><span data-stu-id="ccb14-122">The command position.</span></span>  <br/> |
|<span data-ttu-id="ccb14-123">工具栏</span><span class="sxs-lookup"><span data-stu-id="ccb14-123">A toolbar</span></span>  <br/> | <span data-ttu-id="ccb14-124">双元素单行数组：</span><span class="sxs-lookup"><span data-stu-id="ccb14-124">A two-element single-row array:</span></span>  <br/>  <span data-ttu-id="ccb14-125">内置工具栏的工具栏编号或自定义工具栏的工具栏名称。</span><span class="sxs-lookup"><span data-stu-id="ccb14-125">The toolbar number for built-in toolbars or the toolbar name for custom toolbars.</span></span>  <br/>  <span data-ttu-id="ccb14-126">工具栏上的位置。</span><span class="sxs-lookup"><span data-stu-id="ccb14-126">The position on the toolbar.</span></span>  <br/> |
|<span data-ttu-id="ccb14-127">图形对象</span><span class="sxs-lookup"><span data-stu-id="ccb14-127">A graphic object</span></span>  <br/> |<span data-ttu-id="ccb14-128">对象标识符 (对象名称) 。</span><span class="sxs-lookup"><span data-stu-id="ccb14-128">The object identifier (object name).</span></span>  <br/> |
|<span data-ttu-id="ccb14-129">与 xlcOnEnter 相关联的命令 ON。ENTER、事件捕获</span><span class="sxs-lookup"><span data-stu-id="ccb14-129">A command associated with an xlcOnEnter, ON.ENTER, event trap</span></span>  <br/> |<span data-ttu-id="ccb14-130">对要输入的一个或多个单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="ccb14-130">A reference to the cell or cells being entered.</span></span>  <br/> |
|<span data-ttu-id="ccb14-131">与 xlcOnDoubleclick 相关联的命令 ON。DOUBLECLICK，事件陷阱。</span><span class="sxs-lookup"><span data-stu-id="ccb14-131">A command associated with an xlcOnDoubleclick, ON.DOUBLECLICK, event trap.</span></span>  <br/> |<span data-ttu-id="ccb14-132">双击的单元格不一 (活动单元格) 。</span><span class="sxs-lookup"><span data-stu-id="ccb14-132">The cell that was double-clicked (not necessarily the active cell).</span></span>  <br/> |
|<span data-ttu-id="ccb14-133">Auto_Open、AutoClose、Auto_Activate 或 Auto_Deactivate 宏</span><span class="sxs-lookup"><span data-stu-id="ccb14-133">Auto_Open, AutoClose, Auto_Activate or Auto_Deactivate macro</span></span>  <br/> |<span data-ttu-id="ccb14-134">调用工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="ccb14-134">The name of the calling sheet.</span></span>  <br/> |
|<span data-ttu-id="ccb14-135">未列出的其他方法</span><span class="sxs-lookup"><span data-stu-id="ccb14-135">Other methods not listed</span></span>  <br/> |<span data-ttu-id="ccb14-136">#REF!</span><span class="sxs-lookup"><span data-stu-id="ccb14-136">#REF!</span></span> <span data-ttu-id="ccb14-137">错误。</span><span class="sxs-lookup"><span data-stu-id="ccb14-137">Error.</span></span>  <br/> |
   
```cs
Excel12(xlfCaller, (LPXLOPER12) pxRes,0);
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="ccb14-138">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="ccb14-138">Property value/Return value</span></span>

<span data-ttu-id="ccb14-139">返回值是以下 /  **XLOPER XLOPER12** 数据类型之一：xltypeRef、xltypeSRef、xltypeNum、xltypeStr、xltypeErr 或 **xltypeMulti。**    </span><span class="sxs-lookup"><span data-stu-id="ccb14-139">The return value is one of the following **XLOPER**/ **XLOPER12** data types: **xltypeRef**, **xltypeSRef**, **xltypeNum**, **xltypeStr**, **xltypeErr**, or **xltypeMulti**.</span></span> <span data-ttu-id="ccb14-140">由于其中三种类型指向已分配的内存，因此当不再需要 [xlFree](xlfree.md)函数时，应始终在调用 xlFree 函数时释放 **xlfCaller** 的返回值。</span><span class="sxs-lookup"><span data-stu-id="ccb14-140">Since three of these types point to allocated memory, the return value of **xlfCaller** should always be freed in a call to the [xlFree function](xlfree.md) when it is no longer needed.</span></span> 
  
<span data-ttu-id="ccb14-141">有关 **XLOPERs** /  **XLOPER12s** 的信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="ccb14-141">For more information about **XLOPERs**/ **XLOPER12s** see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ccb14-142">备注</span><span class="sxs-lookup"><span data-stu-id="ccb14-142">Remarks</span></span>

<span data-ttu-id="ccb14-143">此函数是唯一可以从 DLL/XLL 工作表函数调用的非工作表函数。</span><span class="sxs-lookup"><span data-stu-id="ccb14-143">This function is the only non-worksheet function that can be called from a DLL/XLL worksheet function.</span></span> <span data-ttu-id="ccb14-144">其他 XLM 信息函数只能从命令或宏表等效函数调用。</span><span class="sxs-lookup"><span data-stu-id="ccb14-144">Other XLM information functions can only be called from commands or macro-sheet equivalent functions.</span></span>
  
## <a name="example"></a><span data-ttu-id="ccb14-145">示例</span><span class="sxs-lookup"><span data-stu-id="ccb14-145">Example</span></span>

 <span data-ttu-id="ccb14-146">`\SAMPLES\EXAMPLE\EXAMPLE.C`.</span><span class="sxs-lookup"><span data-stu-id="ccb14-146">`\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span> <span data-ttu-id="ccb14-147">此函数在 xlcSelect (调用命令宏) 并且仅在从宏表调用时才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="ccb14-147">This function calls a command macro (xlcSelect) and will work correctly only when called from a macro sheet.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="ccb14-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccb14-148">See also</span></span>



[<span data-ttu-id="ccb14-149">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="ccb14-149">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

