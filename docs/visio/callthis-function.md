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
description: 调用 Microsoft Visual Basic for Applications (VBA) 中的过程。
ms.openlocfilehash: 7e0f0bafa39d6c1eb1fd39535506981c937ce8a1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413813"
---
# <a name="callthis-function"></a><span data-ttu-id="3d54d-103">CALLTHIS 函数</span><span class="sxs-lookup"><span data-stu-id="3d54d-103">CALLTHIS Function</span></span>

<span data-ttu-id="3d54d-104">调用 Microsoft Visual Basic for Applications (VBA) 中的过程。</span><span class="sxs-lookup"><span data-stu-id="3d54d-104">Calls a procedure in a Microsoft Visual Basic for Applications (VBA) project.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3d54d-105">语法</span><span class="sxs-lookup"><span data-stu-id="3d54d-105">Syntax</span></span>

<span data-ttu-id="3d54d-106">CALLTHIS (" \*\* *procedure* \*\* "，[" \*\* *project* \*\* "]，[ \*\* *arg1* \*\*， \*\* *arg2* \*\*,...]) </span><span class="sxs-lookup"><span data-stu-id="3d54d-106">CALLTHIS(" \*\* *procedure* \*\* ",[" \*\* *project* \*\* "],[ \*\* *arg1* \*\*, \*\* *arg2* \*\*,...])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="3d54d-107">参数</span><span class="sxs-lookup"><span data-stu-id="3d54d-107">Parameters</span></span>

|<span data-ttu-id="3d54d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="3d54d-108">**Name**</span></span>|<span data-ttu-id="3d54d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="3d54d-109">**Required/Optional**</span></span>|<span data-ttu-id="3d54d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3d54d-110">**Data Type**</span></span>|<span data-ttu-id="3d54d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="3d54d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3d54d-112">_procedure_</span><span class="sxs-lookup"><span data-stu-id="3d54d-112">_procedure_</span></span> <br/> |<span data-ttu-id="3d54d-113">必需</span><span class="sxs-lookup"><span data-stu-id="3d54d-113">Required</span></span>  <br/> |<span data-ttu-id="3d54d-114">**String**</span><span class="sxs-lookup"><span data-stu-id="3d54d-114">**String**</span></span> <br/> | <span data-ttu-id="3d54d-115">要调用的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="3d54d-115">The name of the procedure to call.</span></span>  <br/> |
| <span data-ttu-id="3d54d-116">_project_</span><span class="sxs-lookup"><span data-stu-id="3d54d-116">_project_</span></span> <br/> |<span data-ttu-id="3d54d-117">可选</span><span class="sxs-lookup"><span data-stu-id="3d54d-117">Optional</span></span>  <br/> |<span data-ttu-id="3d54d-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="3d54d-118">**String**</span></span> <br/> |<span data-ttu-id="3d54d-119">包含该过程的项目。</span><span class="sxs-lookup"><span data-stu-id="3d54d-119">The project that contains the procedure.</span></span>  <br/> |
| <span data-ttu-id="3d54d-120">_arg_</span><span class="sxs-lookup"><span data-stu-id="3d54d-120">_arg_</span></span> <br/> |<span data-ttu-id="3d54d-121">可选</span><span class="sxs-lookup"><span data-stu-id="3d54d-121">Optional</span></span>  <br/> |<span data-ttu-id="3d54d-122">**Number、String、Date 或 Currency**</span><span class="sxs-lookup"><span data-stu-id="3d54d-122">**Number, String, Date, or Currency**</span></span> <br/> |<span data-ttu-id="3d54d-123">作为参数传递给过程。</span><span class="sxs-lookup"><span data-stu-id="3d54d-123">Passed as parameters to the procedure.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3d54d-124">备注</span><span class="sxs-lookup"><span data-stu-id="3d54d-124">Remarks</span></span>

<span data-ttu-id="3d54d-125">在 VBA 项目中  *，过程*  定义如下：</span><span class="sxs-lookup"><span data-stu-id="3d54d-125">In the VBA project,  *procedure*  is defined as follows:</span></span> 
  
<span data-ttu-id="3d54d-126">过程 (*vsoShape* As Visio。形状 [arg1 As type， arg2 As type...]) </span><span class="sxs-lookup"><span data-stu-id="3d54d-126">procedure(*vsoShape*  As Visio.Shape [arg1 As type, arg2 As type...])</span></span> 
  
<span data-ttu-id="3d54d-127">其中  *vsoShape*  是包含要求值 CALLTHIS 公式的 **Shape** 对象的引用  _，arg1_、  *arg2*  ...是该公式中指定的参数。</span><span class="sxs-lookup"><span data-stu-id="3d54d-127">where  *vsoShape*  is a reference to the **Shape** object that contains the CALLTHIS formula being evaluated, and  _arg1_,  *arg2*  ... are the arguments specified in that formula.</span></span> 
  
<span data-ttu-id="3d54d-128">请注意  *，vsoShape*  与传递给 C++ 成员过程的"this"参数非常类似;因此，名称为"CALLTHIS"。</span><span class="sxs-lookup"><span data-stu-id="3d54d-128">Notice that  *vsoShape*  is very much like the "this" argument passed to a C++ member procedure; hence the name "CALLTHIS."</span></span> <span data-ttu-id="3d54d-129">实际上，包含包含 CALLTHIS 的公式的单元格可以读取为"调用此过程，并传递对形状的引用"。</span><span class="sxs-lookup"><span data-stu-id="3d54d-129">In effect, a cell that contains a formula that includes CALLTHIS can be read as, "Call this procedure and pass it a reference to my shape."</span></span> 
  
<span data-ttu-id="3d54d-130">如果 _指定了 project，Microsoft_ Visio所有打开的文档中扫描包含项目的文档 _，并_ 调用该项目中的过程。</span><span class="sxs-lookup"><span data-stu-id="3d54d-130">If  _project_ is specified, Microsoft Visio scans all open documents for the one containing  _project_ and calls  _procedure_ in that project.</span></span> <span data-ttu-id="3d54d-131">如果 _省略 project_ 或空 ("") ，Visio假定 _过程_ 位于包含正在求值 CALLTHIS 公式的文档的 VBA 项目中。</span><span class="sxs-lookup"><span data-stu-id="3d54d-131">If  _project_ is omitted or null (""), Visio assumes  _procedure_ is in the VBA project of the document that contains the CALLTHIS formula that is being evaluated.</span></span> 
  
<span data-ttu-id="3d54d-132">_arg1 、_ _arg2..._ 中的数字以外部单位传递。</span><span class="sxs-lookup"><span data-stu-id="3d54d-132">Numbers in  _arg1_,  _arg2..._ are passed in external units.</span></span> <span data-ttu-id="3d54d-133">例如，如果您传递一个 3 cm 高的形状的 Height 单元格中的数值，则会传递 3。</span><span class="sxs-lookup"><span data-stu-id="3d54d-133">For example, if you pass the value of the Height cell from a shape that is 3 cm tall, 3 is passed.</span></span> <span data-ttu-id="3d54d-134">若要用不同的单位进行传递，则应使用 FORMATEX 函数或通过增加一个空的数值-单位对（例如，0 ft + Height），来明确规定单位。</span><span class="sxs-lookup"><span data-stu-id="3d54d-134">To pass different units with a number, use the FORMATEX function or explicitly coerce units by adding a null number-unit pair, for example, 0 ft + Height.</span></span> 
  
<span data-ttu-id="3d54d-135">CALLTHIS 函数中的第二个逗号是可选的。</span><span class="sxs-lookup"><span data-stu-id="3d54d-135">The second comma in the CALLTHIS function is optional.</span></span> <span data-ttu-id="3d54d-136">它对应于添加到过程中的附加参数的数值。</span><span class="sxs-lookup"><span data-stu-id="3d54d-136">It corresponds to the number of additional parameters added to your procedure.</span></span> <span data-ttu-id="3d54d-137">如果不使用任何其他参数，但不要添加第二个逗号;使用  `(vsoShape as Visio.Shape)` CALLTHIS ("，) 。</span><span class="sxs-lookup"><span data-stu-id="3d54d-137">If you do not use any additional parameters, except  `(vsoShape as Visio.Shape)` , do not add the second comma; use CALLTHIS("",).</span></span> <span data-ttu-id="3d54d-138">例如，如果要添加两个附加参数，请使用 CALLTHIS("",,,)。</span><span class="sxs-lookup"><span data-stu-id="3d54d-138">If you add two additional parameters, for example, use CALLTHIS("",,,).</span></span> 
  
<span data-ttu-id="3d54d-139">CALLTHIS 函数始终计算为 0，并且对  _过程的_ 调用在重新计算过程完成后的空闲时间内发生。</span><span class="sxs-lookup"><span data-stu-id="3d54d-139">The CALLTHIS function always evaluates to 0, and the call to  _procedure_ occurs during idle time after the recalculation process finishes.</span></span>  <span data-ttu-id="3d54d-140">_Procedure_ 可以返回一个数值，但 Visio 将忽略该值。</span><span class="sxs-lookup"><span data-stu-id="3d54d-140">_Procedure_ can return a value, but Visio ignores it.</span></span>  <span data-ttu-id="3d54d-141">_Procedure_ 返回一个值，Visio通过设置文档中其他单元格（而不是调用 _procedure_ 的单元格）的公式或结果来识别该值，除非您要覆盖 CALLTHIS 公式。</span><span class="sxs-lookup"><span data-stu-id="3d54d-141">_Procedure_ returns a value that Visio can recognize by setting the formula or result of another cell in the document, but not the cell that called  _procedure_, unless you want to overwrite the CALLTHIS formula.</span></span>
  
<span data-ttu-id="3d54d-142">CALLTHIS 函数不同于 RUNADDON 函数，文档的项目不需要引用另一个项目便可调用到该项目中。</span><span class="sxs-lookup"><span data-stu-id="3d54d-142">The CALLTHIS function differs from the RUNADDON function in that a document's project does not need to reference another project in order to call into that project.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="3d54d-143">在 Visio 实例对公式中的 CALLTHIS 函数求值时所调用的 VBA 代码不应关闭包含使用该函数的单元格的文档，因为这样会导致应用程序出错，并且 Visio 将终止。</span><span class="sxs-lookup"><span data-stu-id="3d54d-143">VBA code that is invoked when the Visio instance evaluates a CALLTHIS function in a formula should not close the document containing the cell using the function because an application error results and Visio terminates.</span></span> 
  
<span data-ttu-id="3d54d-144">如果您需要关闭包含使用 CALLTHIS 函数的单元格的文档，则请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="3d54d-144">If you need to close the document containing the cell that uses the CALLTHIS function, use one of the following techniques:</span></span> 
  
- <span data-ttu-id="3d54d-145">从非 VBA 的代码关闭文档。</span><span class="sxs-lookup"><span data-stu-id="3d54d-145">Close the document from code that is not VBA.</span></span>
    
- <span data-ttu-id="3d54d-146">从正在关闭的项目之外的其他项目关闭文档。</span><span class="sxs-lookup"><span data-stu-id="3d54d-146">Close the document from a project other than the one that is closing.</span></span>
    
- <span data-ttu-id="3d54d-147">将关闭窗口的窗口消息张贴到文档中，而不是关闭该文档。</span><span class="sxs-lookup"><span data-stu-id="3d54d-147">Post window messages to close windows in the document rather than closing the document.</span></span>
    
<span data-ttu-id="3d54d-148">有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。</span><span class="sxs-lookup"><span data-stu-id="3d54d-148">For more information about running code in Visio, see [About Security Settings and Running Code in Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) in this ShapeSheet Reference.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="3d54d-149">示例 1</span><span class="sxs-lookup"><span data-stu-id="3d54d-149">Example 1</span></span>

<span data-ttu-id="3d54d-150">CALLTHIS("p",,FORMATEX(Height,"#.00 u",,"cm"))</span><span class="sxs-lookup"><span data-stu-id="3d54d-150">CALLTHIS("p",,FORMATEX(Height,"#.00 u",,"cm"))</span></span>
  
<span data-ttu-id="3d54d-151">调用位于模块中的名为 p 的过程，并传递以厘米为单位的高度数值，如 7.62 cm。</span><span class="sxs-lookup"><span data-stu-id="3d54d-151">Calls the procedure named p located in a module and passes the value of Height in centimeters, such as 7.62 cm.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="3d54d-152">示例 2</span><span class="sxs-lookup"><span data-stu-id="3d54d-152">Example 2</span></span>

<span data-ttu-id="3d54d-153">CALLTHIS("q",,0 cm+Height,Width)</span><span class="sxs-lookup"><span data-stu-id="3d54d-153">CALLTHIS("q",,0 cm+Height,Width)</span></span>
  
<span data-ttu-id="3d54d-154">调用位于模块中的名为 q 的过程，并传递以厘米为单位的单元格高度和以内部单位表示的宽度。</span><span class="sxs-lookup"><span data-stu-id="3d54d-154">Calls the procedure named q located in a module and passes the cell's height in centimeters and width in internal units.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="3d54d-155">示例 3</span><span class="sxs-lookup"><span data-stu-id="3d54d-155">Example 3</span></span>

<span data-ttu-id="3d54d-156">请使用  *ThisDocument*  类模块中的以下过程。</span><span class="sxs-lookup"><span data-stu-id="3d54d-156">Use the following procedure in the  *ThisDocument*  class module.</span></span> 
  
<span data-ttu-id="3d54d-157">在形状的 EventDblClick 单元格中使用以下任一语法来调用前面的过程。</span><span class="sxs-lookup"><span data-stu-id="3d54d-157">Use any of the following syntax in a shape's EventDblClick cell with the preceding procedures.</span></span>
  
<span data-ttu-id="3d54d-158">CALLTHIS ("ThisDocument.A"，) </span><span class="sxs-lookup"><span data-stu-id="3d54d-158">CALLTHIS("ThisDocument.A",)</span></span>
  
<span data-ttu-id="3d54d-159">CALLTHIS ("ThisDocument.B"，"Click") </span><span class="sxs-lookup"><span data-stu-id="3d54d-159">CALLTHIS("ThisDocument.B",,"Click")</span></span>
  
<span data-ttu-id="3d54d-160">CALLTHIS("ThisDocument.C",,"Click", " OK.")</span><span class="sxs-lookup"><span data-stu-id="3d54d-160">CALLTHIS("ThisDocument.C",,"Click", " OK.")</span></span>
  

