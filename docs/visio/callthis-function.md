---
title: CALLTHIS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251403
localization_priority: Normal
ms.assetid: 461abfc1-d2cc-2354-1c2f-395c9e351a78
description: 调用 Microsoft Visual Basic for Applications (VBA) 项目中的过程。
ms.openlocfilehash: 7e0f0bafa39d6c1eb1fd39535506981c937ce8a1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337238"
---
# <a name="callthis-function"></a><span data-ttu-id="91bb1-103">CALLTHIS 函数</span><span class="sxs-lookup"><span data-stu-id="91bb1-103">CALLTHIS Function</span></span>

<span data-ttu-id="91bb1-104">调用 Microsoft Visual Basic for Applications (VBA) 项目中的过程。</span><span class="sxs-lookup"><span data-stu-id="91bb1-104">Calls a procedure in a Microsoft Visual Basic for Applications (VBA) project.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="91bb1-105">语法</span><span class="sxs-lookup"><span data-stu-id="91bb1-105">Syntax</span></span>

<span data-ttu-id="91bb1-106">CALLTHIS ("\* **过程** *", ["* **项目** *"], [* \* *arg1* \* \*, \* \* *arg2* \* \*,...])</span><span class="sxs-lookup"><span data-stu-id="91bb1-106">CALLTHIS(" \*\* *procedure* \*\* ",[" \*\* *project* \*\* "],[ \*\* *arg1* \*\*, \*\* *arg2* \*\*,...])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="91bb1-107">参数</span><span class="sxs-lookup"><span data-stu-id="91bb1-107">Parameters</span></span>

|<span data-ttu-id="91bb1-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="91bb1-108">**Name**</span></span>|<span data-ttu-id="91bb1-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="91bb1-109">**Required/Optional**</span></span>|<span data-ttu-id="91bb1-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="91bb1-110">**Data Type**</span></span>|<span data-ttu-id="91bb1-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="91bb1-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="91bb1-112">_过程_</span><span class="sxs-lookup"><span data-stu-id="91bb1-112">_procedure_</span></span> <br/> |<span data-ttu-id="91bb1-113">必需</span><span class="sxs-lookup"><span data-stu-id="91bb1-113">Required</span></span>  <br/> |<span data-ttu-id="91bb1-114">**String**</span><span class="sxs-lookup"><span data-stu-id="91bb1-114">**String**</span></span> <br/> | <span data-ttu-id="91bb1-115">要调用的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="91bb1-115">The name of the procedure to call.</span></span>  <br/> |
| <span data-ttu-id="91bb1-116">_项目_</span><span class="sxs-lookup"><span data-stu-id="91bb1-116">_project_</span></span> <br/> |<span data-ttu-id="91bb1-117">可选</span><span class="sxs-lookup"><span data-stu-id="91bb1-117">Optional</span></span>  <br/> |<span data-ttu-id="91bb1-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="91bb1-118">**String**</span></span> <br/> |<span data-ttu-id="91bb1-119">包含该过程的项目。</span><span class="sxs-lookup"><span data-stu-id="91bb1-119">The project that contains the procedure.</span></span>  <br/> |
| <span data-ttu-id="91bb1-120">_参数_</span><span class="sxs-lookup"><span data-stu-id="91bb1-120">_arg_</span></span> <br/> |<span data-ttu-id="91bb1-121">可选</span><span class="sxs-lookup"><span data-stu-id="91bb1-121">Optional</span></span>  <br/> |<span data-ttu-id="91bb1-122">**Number、String、Date 或 Currency**</span><span class="sxs-lookup"><span data-stu-id="91bb1-122">**Number, String, Date, or Currency**</span></span> <br/> |<span data-ttu-id="91bb1-123">作为参数传递给过程。</span><span class="sxs-lookup"><span data-stu-id="91bb1-123">Passed as parameters to the procedure.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="91bb1-124">注解</span><span class="sxs-lookup"><span data-stu-id="91bb1-124">Remarks</span></span>

<span data-ttu-id="91bb1-125">在 VBA 项目中,*过程*定义如下:</span><span class="sxs-lookup"><span data-stu-id="91bb1-125">In the VBA project,  *procedure*  is defined as follows:</span></span> 
  
<span data-ttu-id="91bb1-126">过程 (*vsoShape*为 Visio [arg1 作为类型, arg2 作为类型 ...])</span><span class="sxs-lookup"><span data-stu-id="91bb1-126">procedure(*vsoShape*  As Visio.Shape [arg1 As type, arg2 As type...])</span></span> 
  
<span data-ttu-id="91bb1-127">其中, *vsoShape*是对**Shape**对象的引用, 该对象包含要计算的 CALLTHIS 公式, _arg1_和*arg2* .。。是在该公式中指定的参数。</span><span class="sxs-lookup"><span data-stu-id="91bb1-127">where  *vsoShape*  is a reference to the **Shape** object that contains the CALLTHIS formula being evaluated, and  _arg1_,  *arg2*  ... are the arguments specified in that formula.</span></span> 
  
<span data-ttu-id="91bb1-128">请注意, *vsoShape*与传递给 c + + 成员过程的 "this" 参数非常相似;因此, 名称为 "CALLTHIS"。</span><span class="sxs-lookup"><span data-stu-id="91bb1-128">Notice that  *vsoShape*  is very much like the "this" argument passed to a C++ member procedure; hence the name "CALLTHIS."</span></span> <span data-ttu-id="91bb1-129">实际上, 包含包含 CALLTHIS 的公式的单元格可以读取为, "调用此过程并向其传递对我的形状的引用"。</span><span class="sxs-lookup"><span data-stu-id="91bb1-129">In effect, a cell that contains a formula that includes CALLTHIS can be read as, "Call this procedure and pass it a reference to my shape."</span></span> 
  
<span data-ttu-id="91bb1-130">如果指定了_project_ , Microsoft Visio 将扫描所有打开的文档中包含_项目_的文档, 并调用该项目中的_过程_。</span><span class="sxs-lookup"><span data-stu-id="91bb1-130">If  _project_ is specified, Microsoft Visio scans all open documents for the one containing  _project_ and calls  _procedure_ in that project.</span></span> <span data-ttu-id="91bb1-131">如果_project_被省略或为空 (""), 则 Visio 假定_过程_位于包含正在计算的 CALLTHIS 公式的文档的 VBA 项目中。</span><span class="sxs-lookup"><span data-stu-id="91bb1-131">If  _project_ is omitted or null (""), Visio assumes  _procedure_ is in the VBA project of the document that contains the CALLTHIS formula that is being evaluated.</span></span> 
  
<span data-ttu-id="91bb1-132">_arg1_中的数字__ 以外部单位传入。</span><span class="sxs-lookup"><span data-stu-id="91bb1-132">Numbers in  _arg1_,  _arg2..._ are passed in external units.</span></span> <span data-ttu-id="91bb1-133">例如，如果您传递一个 3 cm 高的形状的 Height 单元格中的数值，则会传递 3。</span><span class="sxs-lookup"><span data-stu-id="91bb1-133">For example, if you pass the value of the Height cell from a shape that is 3 cm tall, 3 is passed.</span></span> <span data-ttu-id="91bb1-134">若要用不同的单位进行传递，则应使用 FORMATEX 函数或通过增加一个空的数值-单位对（例如，0 ft + Height），来明确规定单位。</span><span class="sxs-lookup"><span data-stu-id="91bb1-134">To pass different units with a number, use the FORMATEX function or explicitly coerce units by adding a null number-unit pair, for example, 0 ft + Height.</span></span> 
  
<span data-ttu-id="91bb1-135">CALLTHIS 函数中的第二个逗号是可选的。</span><span class="sxs-lookup"><span data-stu-id="91bb1-135">The second comma in the CALLTHIS function is optional.</span></span> <span data-ttu-id="91bb1-136">它对应于添加到过程中的附加参数的数值。</span><span class="sxs-lookup"><span data-stu-id="91bb1-136">It corresponds to the number of additional parameters added to your procedure.</span></span> <span data-ttu-id="91bb1-137">如果不使用任何其他参数, 除之外`(vsoShape as Visio.Shape)` , 不要添加第二个逗号;使用 CALLTHIS ("",)。</span><span class="sxs-lookup"><span data-stu-id="91bb1-137">If you do not use any additional parameters, except  `(vsoShape as Visio.Shape)` , do not add the second comma; use CALLTHIS("",).</span></span> <span data-ttu-id="91bb1-138">例如，如果要添加两个附加参数，请使用 CALLTHIS("",,,)。</span><span class="sxs-lookup"><span data-stu-id="91bb1-138">If you add two additional parameters, for example, use CALLTHIS("",,,).</span></span> 
  
<span data-ttu-id="91bb1-139">CALLTHIS 函数的计算结果始终为 0, 并且在重新计算过程完成后的空闲时间, 对_过程_的调用发生。</span><span class="sxs-lookup"><span data-stu-id="91bb1-139">The CALLTHIS function always evaluates to 0, and the call to  _procedure_ occurs during idle time after the recalculation process finishes.</span></span>  <span data-ttu-id="91bb1-140">_Procedure_ 可以返回一个数值，但 Visio 将忽略该值。</span><span class="sxs-lookup"><span data-stu-id="91bb1-140">_Procedure_ can return a value, but Visio ignores it.</span></span>  <span data-ttu-id="91bb1-141">_过程_返回一个值, Visio 可以通过在文档中设置另一个单元格 (而不是被调用_过程_的单元格) 的公式或结果来识别它, 除非您要覆盖 CALLTHIS 公式。</span><span class="sxs-lookup"><span data-stu-id="91bb1-141">_Procedure_ returns a value that Visio can recognize by setting the formula or result of another cell in the document, but not the cell that called  _procedure_, unless you want to overwrite the CALLTHIS formula.</span></span>
  
<span data-ttu-id="91bb1-142">CALLTHIS 函数不同于 RUNADDON 函数，文档的项目不需要引用另一个项目便可调用到该项目中。</span><span class="sxs-lookup"><span data-stu-id="91bb1-142">The CALLTHIS function differs from the RUNADDON function in that a document's project does not need to reference another project in order to call into that project.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="91bb1-143">在 Visio 实例对公式中的 CALLTHIS 函数求值时所调用的 VBA 代码不应关闭包含使用该函数的单元格的文档，因为这样会导致应用程序出错，并且 Visio 将终止。</span><span class="sxs-lookup"><span data-stu-id="91bb1-143">VBA code that is invoked when the Visio instance evaluates a CALLTHIS function in a formula should not close the document containing the cell using the function because an application error results and Visio terminates.</span></span> 
  
<span data-ttu-id="91bb1-144">如果您需要关闭包含使用 CALLTHIS 函数的单元格的文档，则请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="91bb1-144">If you need to close the document containing the cell that uses the CALLTHIS function, use one of the following techniques:</span></span> 
  
- <span data-ttu-id="91bb1-145">从非 VBA 的代码关闭文档。</span><span class="sxs-lookup"><span data-stu-id="91bb1-145">Close the document from code that is not VBA.</span></span>
    
- <span data-ttu-id="91bb1-146">从正在关闭的项目之外的其他项目关闭文档。</span><span class="sxs-lookup"><span data-stu-id="91bb1-146">Close the document from a project other than the one that is closing.</span></span>
    
- <span data-ttu-id="91bb1-147">将关闭窗口的窗口消息张贴到文档中，而不是关闭该文档。</span><span class="sxs-lookup"><span data-stu-id="91bb1-147">Post window messages to close windows in the document rather than closing the document.</span></span>
    
<span data-ttu-id="91bb1-148">有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。</span><span class="sxs-lookup"><span data-stu-id="91bb1-148">For more information about running code in Visio, see [About Security Settings and Running Code in Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) in this ShapeSheet Reference.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="91bb1-149">示例 1</span><span class="sxs-lookup"><span data-stu-id="91bb1-149">Example 1</span></span>

<span data-ttu-id="91bb1-150">CALLTHIS("p",,FORMATEX(Height,"#.00 u",,"cm"))</span><span class="sxs-lookup"><span data-stu-id="91bb1-150">CALLTHIS("p",,FORMATEX(Height,"#.00 u",,"cm"))</span></span>
  
<span data-ttu-id="91bb1-151">调用位于模块中的名为 p 的过程，并传递以厘米为单位的高度数值，如 7.62 cm。</span><span class="sxs-lookup"><span data-stu-id="91bb1-151">Calls the procedure named p located in a module and passes the value of Height in centimeters, such as 7.62 cm.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="91bb1-152">示例 2</span><span class="sxs-lookup"><span data-stu-id="91bb1-152">Example 2</span></span>

<span data-ttu-id="91bb1-153">CALLTHIS("q",,0 cm+Height,Width)</span><span class="sxs-lookup"><span data-stu-id="91bb1-153">CALLTHIS("q",,0 cm+Height,Width)</span></span>
  
<span data-ttu-id="91bb1-154">调用位于模块中的名为 q 的过程，并传递以厘米为单位的单元格高度和以内部单位表示的宽度。</span><span class="sxs-lookup"><span data-stu-id="91bb1-154">Calls the procedure named q located in a module and passes the cell's height in centimeters and width in internal units.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="91bb1-155">示例 3</span><span class="sxs-lookup"><span data-stu-id="91bb1-155">Example 3</span></span>

<span data-ttu-id="91bb1-156">在*ThisDocument*类模块中使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="91bb1-156">Use the following procedure in the  *ThisDocument*  class module.</span></span> 
  
<span data-ttu-id="91bb1-157">在形状的 EventDblClick 单元格中使用以下任一语法来调用前面的过程。</span><span class="sxs-lookup"><span data-stu-id="91bb1-157">Use any of the following syntax in a shape's EventDblClick cell with the preceding procedures.</span></span>
  
<span data-ttu-id="91bb1-158">CALLTHIS ("ThisDocument",)</span><span class="sxs-lookup"><span data-stu-id="91bb1-158">CALLTHIS("ThisDocument.A",)</span></span>
  
<span data-ttu-id="91bb1-159">CALLTHIS ("ThisDocument",, "单击")</span><span class="sxs-lookup"><span data-stu-id="91bb1-159">CALLTHIS("ThisDocument.B",,"Click")</span></span>
  
<span data-ttu-id="91bb1-160">CALLTHIS("ThisDocument.C",,"Click", " OK.")</span><span class="sxs-lookup"><span data-stu-id="91bb1-160">CALLTHIS("ThisDocument.C",,"Click", " OK.")</span></span>
  

