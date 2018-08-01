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
description: 在 Microsoft Visual Basic for Applications (VBA) 项目执行加载项或宏。
ms.openlocfilehash: 31ac32c742827311d8aaee4547024ad97d2c48e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781212"
---
# <a name="runaddon-function"></a><span data-ttu-id="3baf1-103">RUNADDON 函数</span><span class="sxs-lookup"><span data-stu-id="3baf1-103">RUNADDON Function</span></span>

<span data-ttu-id="3baf1-104">在 Microsoft Visual Basic for Applications (VBA) 项目执行加载项或宏。</span><span class="sxs-lookup"><span data-stu-id="3baf1-104">Executes an add-on or a macro in a Microsoft Visual Basic for Applications (VBA) project.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="3baf1-105">语法</span><span class="sxs-lookup"><span data-stu-id="3baf1-105">Syntax</span></span>

<span data-ttu-id="3baf1-106">RUNADDON （"*字符串*"）</span><span class="sxs-lookup"><span data-stu-id="3baf1-106">RUNADDON(" *string*  ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="3baf1-107">参数</span><span class="sxs-lookup"><span data-stu-id="3baf1-107">Parameters</span></span>

|<span data-ttu-id="3baf1-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="3baf1-108">**Name**</span></span>|<span data-ttu-id="3baf1-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="3baf1-109">**Required/Optional**</span></span>|<span data-ttu-id="3baf1-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3baf1-110">**Data Type**</span></span>|<span data-ttu-id="3baf1-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="3baf1-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3baf1-112">_string_</span><span class="sxs-lookup"><span data-stu-id="3baf1-112">_string_</span></span> <br/> |<span data-ttu-id="3baf1-113">必需</span><span class="sxs-lookup"><span data-stu-id="3baf1-113">Required</span></span>  <br/> |<span data-ttu-id="3baf1-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="3baf1-114">**String**</span></span> <br/> | <span data-ttu-id="3baf1-115">**Addons** 集合中的加载项或 VBA 项目中的宏的名称。</span><span class="sxs-lookup"><span data-stu-id="3baf1-115">The name of an add-on in the **Addons** collection or a macro in a VBA project.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3baf1-116">说明</span><span class="sxs-lookup"><span data-stu-id="3baf1-116">Remarks</span></span>

<span data-ttu-id="3baf1-117">如果包含 RUNADDON 函数调用的文档项目 （或另一个项目，如果它引用） 不具有一个名为_字符串_的宏 （不带任何参数的过程），Microsoft Visio 将运行名为_字符串_的加载项。</span><span class="sxs-lookup"><span data-stu-id="3baf1-117">If the project of the document that contains the RUNADDON function call (or another project if it is referenced) does not have a macro (a procedure with no arguments) named  _string_, Microsoft Visio runs the add-on named  _string_.</span></span> <span data-ttu-id="3baf1-118">如果找不到名为_字符串_没有加载项，Visio 将不执行任何操作，并不报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="3baf1-118">If no add-on named  _string_ can be found, Visio does nothing and reports no error.</span></span> <span data-ttu-id="3baf1-119">（您可以使用**TraceFlags**属性要监视的过程和 Visio 尝试运行的加载项。）</span><span class="sxs-lookup"><span data-stu-id="3baf1-119">(You can use the **TraceFlags** property to monitor the procedures and add-ons that Visio attempts to run.)</span></span> 
  
<span data-ttu-id="3baf1-120">当标准模块中调用过程时，建议您前缀与包含 (例如， *moduleName.procName*)，该过程的模块名称的字符串，因为多个模块可以具有相同名称的过程。</span><span class="sxs-lookup"><span data-stu-id="3baf1-120">When you call a procedure in a standard module, it is recommended that you prefix the string with the module name that contains the procedure (for example,  *moduleName.procName*), because more than one module can have a procedure with the same name.</span></span> 
  
<span data-ttu-id="3baf1-121">在项目中调用过程以外的其他项目的文档的包含 RUNADDON 函数调用，使用语法*projName.modName.procName* （必须具有显式设置引用*projName* VBA 项目中）。</span><span class="sxs-lookup"><span data-stu-id="3baf1-121">To call a procedure in a project other than the project of the document that contains the RUNADDON function call, use the syntax  *projName.modName.procName*  (you must have explicitly set a reference to  *projName*  in your VBA project).</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="3baf1-p102">从 Visio 2002 开始，RUNADDON 函数无法执行含有任意 VBA 代码的字符串。对于以前传递到 RUNADDON 函数的代码，可以将这些代码移到从该 RUNADDON 函数调用的某个文档的 VBA 项目的过程中。</span><span class="sxs-lookup"><span data-stu-id="3baf1-p102">Beginning with Visio 2002, the RUNADDON function cannot execute a string containing arbitrary VBA code. Code that was formerly passed to the RUNADDON function can be moved to a procedure in a document's VBA project that is called from the RUNADDON function.</span></span> 
  
<span data-ttu-id="3baf1-124">有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。</span><span class="sxs-lookup"><span data-stu-id="3baf1-124">For more information about running code in Visio, see [About Security Settings and Running Code in Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) in this ShapeSheet Reference.</span></span> 
  
<span data-ttu-id="3baf1-p103">在 Visio 的早期版本中，此函数以 _RUNADDON 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="3baf1-p103">In earlier versions of Visio, this function appears as _RUNADDON. Visio versions 4.0 and later accept either style.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="3baf1-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="3baf1-127">Example 1</span></span>

<span data-ttu-id="3baf1-128">RUNADDON("Calendar.exe")</span><span class="sxs-lookup"><span data-stu-id="3baf1-128">RUNADDON("Calendar.exe")</span></span>
  
<span data-ttu-id="3baf1-129">启动名为 Calendar.exe 的加载项。</span><span class="sxs-lookup"><span data-stu-id="3baf1-129">Launches an add-on called Calendar.exe.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="3baf1-130">示例 2</span><span class="sxs-lookup"><span data-stu-id="3baf1-130">Example 2</span></span>

<span data-ttu-id="3baf1-131">RUNADDON("Array Shapes")</span><span class="sxs-lookup"><span data-stu-id="3baf1-131">RUNADDON("Array Shapes")</span></span>
  
<span data-ttu-id="3baf1-132">启动名为 Array Shapes 的（实现 VSL 功能的）加载项。</span><span class="sxs-lookup"><span data-stu-id="3baf1-132">Launches the (VSL-implemented) add-on whose name is Array Shapes.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="3baf1-133">示例 3</span><span class="sxs-lookup"><span data-stu-id="3baf1-133">Example 3</span></span>

<span data-ttu-id="3baf1-134">RUNADDON("ThisDocument.ReportStatistics")</span><span class="sxs-lookup"><span data-stu-id="3baf1-134">RUNADDON("ThisDocument.ReportStatistics")</span></span>
  
<span data-ttu-id="3baf1-135">在包含此函数调用的文档项目中，调用 **ThisDocument** 模块中的 ReportStatistics 宏。</span><span class="sxs-lookup"><span data-stu-id="3baf1-135">Calls the ReportStatistics macro in the **ThisDocument** module in the document project containing this function call.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="3baf1-136">若要调用 **ThisDocument** 模块中的宏，必须如示例所示，使用“ThisDocument”作为字符串的前缀。</span><span class="sxs-lookup"><span data-stu-id="3baf1-136">To invoke a macro in the **ThisDocument** module, you must preface the string with "ThisDocument" as shown.</span></span> 
  
## <a name="example-4"></a><span data-ttu-id="3baf1-137">示例 4</span><span class="sxs-lookup"><span data-stu-id="3baf1-137">Example 4</span></span>

<span data-ttu-id="3baf1-138">RUNADDON (" *ModuleName* 。ReportStatistics")</span><span class="sxs-lookup"><span data-stu-id="3baf1-138">RUNADDON(" *ModuleName*  .ReportStatistics")</span></span> 
  
<span data-ttu-id="3baf1-139">调用*ModuleName*中包含此函数调用的文档项目中的 ReportStatistics 宏。</span><span class="sxs-lookup"><span data-stu-id="3baf1-139">Calls the ReportStatistics macro in  *ModuleName*  in the document project that contains this function call.</span></span> 
  

