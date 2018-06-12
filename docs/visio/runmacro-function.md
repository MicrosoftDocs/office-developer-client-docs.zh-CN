---
title: RUNMACRO 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033809
localization_priority: Normal
ms.assetid: 86b0f071-5e0b-56de-ff5b-63c114ad823a
description: 调用宏在 Microsoft Visual Basic for Applications (VBA) 项目。
ms.openlocfilehash: e3dd989956ce9c5f795ae3ef0d8535ab2776d6d7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781209"
---
# <a name="runmacro-function"></a><span data-ttu-id="774a3-103">RUNMACRO 函数</span><span class="sxs-lookup"><span data-stu-id="774a3-103">RUNMACRO Function</span></span>

<span data-ttu-id="774a3-104">调用宏在 Microsoft Visual Basic for Applications (VBA) 项目。</span><span class="sxs-lookup"><span data-stu-id="774a3-104">Calls a macro in a Microsoft Visual Basic for Applications (VBA) project.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="774a3-105">语法</span><span class="sxs-lookup"><span data-stu-id="774a3-105">Syntax</span></span>

<span data-ttu-id="774a3-106">RUNMACRO (* * *macroname* * * [，* * *projname_opt* * *])</span><span class="sxs-lookup"><span data-stu-id="774a3-106">RUNMACRO (** *macroname* ** [, ** *projname_opt* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="774a3-107">参数</span><span class="sxs-lookup"><span data-stu-id="774a3-107">Parameters</span></span>

|<span data-ttu-id="774a3-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="774a3-108">**Name**</span></span>|<span data-ttu-id="774a3-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="774a3-109">**Required/Optional**</span></span>|<span data-ttu-id="774a3-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="774a3-110">**Data Type**</span></span>|<span data-ttu-id="774a3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="774a3-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="774a3-112">_macroname_</span><span class="sxs-lookup"><span data-stu-id="774a3-112">_macroname_</span></span> <br/> |<span data-ttu-id="774a3-113">必需</span><span class="sxs-lookup"><span data-stu-id="774a3-113">Required</span></span>  <br/> |<span data-ttu-id="774a3-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="774a3-114">**String**</span></span> <br/> |<span data-ttu-id="774a3-115">要调用的宏的名称。</span><span class="sxs-lookup"><span data-stu-id="774a3-115">The name of the macro to call.</span></span>  <br/> |
| <span data-ttu-id="774a3-116">_projname_opt_</span><span class="sxs-lookup"><span data-stu-id="774a3-116">_projname_opt_</span></span> <br/> |<span data-ttu-id="774a3-117">可选</span><span class="sxs-lookup"><span data-stu-id="774a3-117">Optional</span></span>  <br/> |<span data-ttu-id="774a3-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="774a3-118">**String**</span></span> <br/> | <span data-ttu-id="774a3-119">包含宏的项目。</span><span class="sxs-lookup"><span data-stu-id="774a3-119">The project that contains the macro.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="774a3-120">注解</span><span class="sxs-lookup"><span data-stu-id="774a3-120">Remarks</span></span>

<span data-ttu-id="774a3-121">如果指定一个项目，则 Microsoft Visio 将扫描一个包含_projname_opt_和呼叫_macroname_该项目中的所有打开的文档。</span><span class="sxs-lookup"><span data-stu-id="774a3-121">If a project is specified, Microsoft Visio scans all open documents for the one containing  _projname_opt_ and calls  _macroname_ in that project.</span></span> <span data-ttu-id="774a3-122">如果_projname_opt_被省略或 null ("")，则假定_macroname_可在 VBA 项目中的文档的包含 RUNMACRO 公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="774a3-122">If  _projname_opt_ is omitted or null (""),  _macroname_ is assumed to be in the VBA project of the document that contains the RUNMACRO formula being evaluated.</span></span> 
  
<span data-ttu-id="774a3-123">RUNMACRO 函数与 CALLTHIS 函数不同，不传递到拥有对_macroname_计算的公式的形状的引用。</span><span class="sxs-lookup"><span data-stu-id="774a3-123">The RUNMACRO function differs from the CALLTHIS function in that it does not pass a reference to the shape that owns the formula being evaluated to  _macroname_.</span></span> <span data-ttu-id="774a3-124">CALLTHIS，如 RUNMACRO 函数不需要对_projname_opt_调用它的引用。</span><span class="sxs-lookup"><span data-stu-id="774a3-124">Like CALLTHIS, the RUNMACRO function doesn't require a reference to  _projname_opt_ to call into it.</span></span> 
  
 <span data-ttu-id="774a3-125">在 Visio 实例对公式中的 RUNMACRO 函数求值时所调用的 VBA 代码不应关闭包含使用该函数的单元格的文档，因为这样会导致应用程序出错，并且 Visio 将终止。</span><span class="sxs-lookup"><span data-stu-id="774a3-125">VBA code that is invoked when the Visio instance evaluates a RUNMACRO function in a formula should not close the document containing the cell using the function because an application error results and Visio terminates.</span></span> 
  
<span data-ttu-id="774a3-126">如果您需要关闭包含使用 RUNMACRO 函数的单元格的文档，则请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="774a3-126">If you need to close the document containing the cell that uses the RUNMACRO function, use one of the following techniques:</span></span>
  
- <span data-ttu-id="774a3-127">从非 VBA 的代码关闭文档。</span><span class="sxs-lookup"><span data-stu-id="774a3-127">Close the document from code that is not VBA.</span></span>
    
- <span data-ttu-id="774a3-128">从正在关闭的项目之外的其他项目关闭文档。</span><span class="sxs-lookup"><span data-stu-id="774a3-128">Close the document from a project other than the one that is closing.</span></span>
    
- <span data-ttu-id="774a3-129">将关闭窗口的窗口消息张贴到文档中，而不是关闭该文档。</span><span class="sxs-lookup"><span data-stu-id="774a3-129">Post window messages to close windows in the document rather than closing the document.</span></span>
    
<span data-ttu-id="774a3-130">有关在 Visio 中运行代码的详细信息，请参阅[关于安全设置和运行代码在 Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) ShapeSheet 参考中。</span><span class="sxs-lookup"><span data-stu-id="774a3-130">For more information about running code in Visio, see [About security settings and running code in Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) in this ShapeSheet Reference.</span></span> 
  
## <a name="example"></a><span data-ttu-id="774a3-131">示例</span><span class="sxs-lookup"><span data-stu-id="774a3-131">Example</span></span>

<span data-ttu-id="774a3-132">下面的示例调用包含 RUNMACRO 公式的 VBA 项目的 ThisDocument 类模块中名为 MyTest 的宏。</span><span class="sxs-lookup"><span data-stu-id="774a3-132">The following example invokes a macro called MyTest in the ThisDocument class module of the VBA project containing the RUNMACRO formula.</span></span> 
  
<span data-ttu-id="774a3-133">RUNMACRO ("ThisDocument.MyTest")</span><span class="sxs-lookup"><span data-stu-id="774a3-133">RUNMACRO ("ThisDocument.MyTest")</span></span> 
  

