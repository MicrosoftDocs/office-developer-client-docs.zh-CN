---
title: RUNADDON 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251492
localization_priority: Normal
ms.assetid: 122c1d30-3cb9-7e7d-b4cc-e93ab8e4da4f
description: 在 Microsoft Visual Basic for Applications (VBA) 项目中执行加载项或宏。
ms.openlocfilehash: 280f6eaf1e5db045d8c1d22965df00960d188112
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319059"
---
# <a name="runaddon-function"></a><span data-ttu-id="8ee35-103">RUNADDON 函数</span><span class="sxs-lookup"><span data-stu-id="8ee35-103">RUNADDON Function</span></span>

<span data-ttu-id="8ee35-104">在 Microsoft Visual Basic for Applications (VBA) 项目中执行加载项或宏。</span><span class="sxs-lookup"><span data-stu-id="8ee35-104">Executes an add-on or a macro in a Microsoft Visual Basic for Applications (VBA) project.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="8ee35-105">语法</span><span class="sxs-lookup"><span data-stu-id="8ee35-105">Syntax</span></span>

<span data-ttu-id="8ee35-106">RUNADDON (" *string* ")</span><span class="sxs-lookup"><span data-stu-id="8ee35-106">RUNADDON(" *string*  ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8ee35-107">参数</span><span class="sxs-lookup"><span data-stu-id="8ee35-107">Parameters</span></span>

|<span data-ttu-id="8ee35-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8ee35-108">**Name**</span></span>|<span data-ttu-id="8ee35-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8ee35-109">**Required/Optional**</span></span>|<span data-ttu-id="8ee35-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8ee35-110">**Data Type**</span></span>|<span data-ttu-id="8ee35-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ee35-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8ee35-112">_string_</span><span class="sxs-lookup"><span data-stu-id="8ee35-112">_string_</span></span> <br/> |<span data-ttu-id="8ee35-113">必需</span><span class="sxs-lookup"><span data-stu-id="8ee35-113">Required</span></span>  <br/> |<span data-ttu-id="8ee35-114">**String**</span><span class="sxs-lookup"><span data-stu-id="8ee35-114">**String**</span></span> <br/> | <span data-ttu-id="8ee35-115">**Addons** 集合中的加载项或 VBA 项目中的宏的名称。</span><span class="sxs-lookup"><span data-stu-id="8ee35-115">The name of an add-on in the **Addons** collection or a macro in a VBA project.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8ee35-116">注解</span><span class="sxs-lookup"><span data-stu-id="8ee35-116">Remarks</span></span>

<span data-ttu-id="8ee35-117">如果包含 RUNADDON 函数调用的文档项目 (或引用的其他项目) 没有名为_string_的宏 (没有参数的过程), Microsoft Visio 将运行加载项的名为_string_。</span><span class="sxs-lookup"><span data-stu-id="8ee35-117">If the project of the document that contains the RUNADDON function call (or another project if it is referenced) does not have a macro (a procedure with no arguments) named  _string_, Microsoft Visio runs the add-on named  _string_.</span></span> <span data-ttu-id="8ee35-118">如果找不到任何附加的命名_字符串_, Visio 不会执行任何操作, 并且报告不会出错。</span><span class="sxs-lookup"><span data-stu-id="8ee35-118">If no add-on named  _string_ can be found, Visio does nothing and reports no error.</span></span> <span data-ttu-id="8ee35-119">(可以使用**TraceFlags**属性监视 Visio 尝试运行的过程和加载项。)</span><span class="sxs-lookup"><span data-stu-id="8ee35-119">(You can use the **TraceFlags** property to monitor the procedures and add-ons that Visio attempts to run.)</span></span> 
  
<span data-ttu-id="8ee35-120">在标准模块中调用过程时, 建议使用包含过程的模块名称为字符串加上前缀 (例如, *procName*), 因为不止一个模块可以有同名的过程。</span><span class="sxs-lookup"><span data-stu-id="8ee35-120">When you call a procedure in a standard module, it is recommended that you prefix the string with the module name that contains the procedure (for example,  *moduleName.procName*), because more than one module can have a procedure with the same name.</span></span> 
  
<span data-ttu-id="8ee35-121">若要调用包含 RUNADDON 函数调用的文档项目之外的项目中的过程, 请使用语法*projName* (您必须显式设置对 VBA 项目中的*projName*的引用)。</span><span class="sxs-lookup"><span data-stu-id="8ee35-121">To call a procedure in a project other than the project of the document that contains the RUNADDON function call, use the syntax  *projName.modName.procName*  (you must have explicitly set a reference to  *projName*  in your VBA project).</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="8ee35-p102">从 Visio 2002 开始，RUNADDON 函数无法执行含有任意 VBA 代码的字符串。对于以前传递到 RUNADDON 函数的代码，可以将这些代码移到从该 RUNADDON 函数调用的某个文档的 VBA 项目的过程中。</span><span class="sxs-lookup"><span data-stu-id="8ee35-p102">Beginning with Visio 2002, the RUNADDON function cannot execute a string containing arbitrary VBA code. Code that was formerly passed to the RUNADDON function can be moved to a procedure in a document's VBA project that is called from the RUNADDON function.</span></span> 
  
<span data-ttu-id="8ee35-124">有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。</span><span class="sxs-lookup"><span data-stu-id="8ee35-124">For more information about running code in Visio, see [About Security Settings and Running Code in Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) in this ShapeSheet Reference.</span></span> 
  
<span data-ttu-id="8ee35-p103">在 Visio 的早期版本中，此函数以 _RUNADDON 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="8ee35-p103">In earlier versions of Visio, this function appears as _RUNADDON. Visio versions 4.0 and later accept either style.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="8ee35-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="8ee35-127">Example 1</span></span>

<span data-ttu-id="8ee35-128">RUNADDON ("Calendar")</span><span class="sxs-lookup"><span data-stu-id="8ee35-128">RUNADDON("Calendar.exe")</span></span>
  
<span data-ttu-id="8ee35-129">启动名为 "share.exe" 的加载项。</span><span class="sxs-lookup"><span data-stu-id="8ee35-129">Launches an add-on called Calendar.exe.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="8ee35-130">示例 2</span><span class="sxs-lookup"><span data-stu-id="8ee35-130">Example 2</span></span>

<span data-ttu-id="8ee35-131">RUNADDON("Array Shapes")</span><span class="sxs-lookup"><span data-stu-id="8ee35-131">RUNADDON("Array Shapes")</span></span>
  
<span data-ttu-id="8ee35-132">启动名为 Array Shapes 的（实现 VSL 功能的）加载项。</span><span class="sxs-lookup"><span data-stu-id="8ee35-132">Launches the (VSL-implemented) add-on whose name is Array Shapes.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="8ee35-133">示例 3</span><span class="sxs-lookup"><span data-stu-id="8ee35-133">Example 3</span></span>

<span data-ttu-id="8ee35-134">RUNADDON ("ThisDocument")</span><span class="sxs-lookup"><span data-stu-id="8ee35-134">RUNADDON("ThisDocument.ReportStatistics")</span></span>
  
<span data-ttu-id="8ee35-135">在包含此函数调用的文档项目中，调用 **ThisDocument** 模块中的 ReportStatistics 宏。</span><span class="sxs-lookup"><span data-stu-id="8ee35-135">Calls the ReportStatistics macro in the **ThisDocument** module in the document project containing this function call.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="8ee35-136">若要调用 **ThisDocument** 模块中的宏，必须如示例所示，使用“ThisDocument”作为字符串的前缀。</span><span class="sxs-lookup"><span data-stu-id="8ee35-136">To invoke a macro in the **ThisDocument** module, you must preface the string with "ThisDocument" as shown.</span></span> 
  
## <a name="example-4"></a><span data-ttu-id="8ee35-137">示例 4</span><span class="sxs-lookup"><span data-stu-id="8ee35-137">Example 4</span></span>

<span data-ttu-id="8ee35-138">RUNADDON (" *ModuleName* 。ReportStatistics ")</span><span class="sxs-lookup"><span data-stu-id="8ee35-138">RUNADDON(" *ModuleName*  .ReportStatistics")</span></span> 
  
<span data-ttu-id="8ee35-139">在包含此函数调用的 document 项目中调用*ModuleName*中的 ReportStatistics 宏。</span><span class="sxs-lookup"><span data-stu-id="8ee35-139">Calls the ReportStatistics macro in  *ModuleName*  in the document project that contains this function call.</span></span> 
  

