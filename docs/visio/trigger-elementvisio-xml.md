---
title: Trigger 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d897d2d1-25ba-48d7-b87e-d3c533d88c15
description: 提供对 Microsoft Visio 重新计算 Visio 文件中的文档部件之间的关系的说明。
ms.openlocfilehash: 909fff3ccec176cd3ce327fc208c176a68764fe3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781567"
---
# <a name="trigger-element-visio-xml"></a><span data-ttu-id="001b7-103">Trigger 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="001b7-103">Trigger element ('Visio XML')</span></span>

<span data-ttu-id="001b7-104">提供对 Microsoft Visio 重新计算 Visio 文件中的文档部件之间的关系的说明。</span><span class="sxs-lookup"><span data-stu-id="001b7-104">Provides instructions to Microsoft Visio to recalculate a relationship between document parts in a Visio file.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="001b7-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="001b7-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="001b7-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="001b7-106">**Element type**</span></span> <br/> |[<span data-ttu-id="001b7-107">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="001b7-107">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="001b7-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="001b7-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="001b7-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="001b7-109">**Schema file**</span></span> <br/> |<span data-ttu-id="001b7-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="001b7-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="001b7-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="001b7-111">**Document parts**</span></span> <br/> |<span data-ttu-id="001b7-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="001b7-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="001b7-113">定义</span><span class="sxs-lookup"><span data-stu-id="001b7-113">Definition</span></span>

```XML
<xs:element name="Trigger" type="Trigger_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="001b7-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="001b7-114">Elements and attributes</span></span>

<span data-ttu-id="001b7-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="001b7-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="001b7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="001b7-116">Parent elements</span></span>

|<span data-ttu-id="001b7-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="001b7-117">**Element**</span></span>|<span data-ttu-id="001b7-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="001b7-118">**Type**</span></span>|<span data-ttu-id="001b7-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="001b7-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="001b7-120">Shape</span><span class="sxs-lookup"><span data-stu-id="001b7-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="001b7-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="001b7-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-122">指定单元格元素能够提供程序的形状定义的信息。</span><span class="sxs-lookup"><span data-stu-id="001b7-122">Specifies cell elements that provide information for the definition of a shape.</span></span>  <br/> |
|[<span data-ttu-id="001b7-123">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="001b7-123">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="001b7-124">DocumentSheet_Type</span><span class="sxs-lookup"><span data-stu-id="001b7-124">DocumentSheet_Type</span></span>](documentsheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-125">定义的 DocumentSheet 结构。</span><span class="sxs-lookup"><span data-stu-id="001b7-125">Defines the DocumentSheet structure.</span></span>  <br/> |
|[<span data-ttu-id="001b7-126">样式表</span><span class="sxs-lookup"><span data-stu-id="001b7-126">StyleSheet</span></span>](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="001b7-127">StyleSheet_Type</span><span class="sxs-lookup"><span data-stu-id="001b7-127">StyleSheet_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-128">表示在文档中定义的样式。</span><span class="sxs-lookup"><span data-stu-id="001b7-128">Represents a style defined in a document.</span></span>  <br/> |
|[<span data-ttu-id="001b7-129">PageSheet （Master_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-129">PageSheet (Master_Type complexType)</span></span>](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="001b7-130">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="001b7-130">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-131">指定绘图页主控形状相关联的属性。</span><span class="sxs-lookup"><span data-stu-id="001b7-131">Specifies the properties of the drawing page associated with the master.</span></span>  <br/> |
|[<span data-ttu-id="001b7-132">PageSheet （Page_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-132">PageSheet (Page_Type complexType)</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="001b7-133">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="001b7-133">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-134">指定绘图页在绘图页相关联的属性。</span><span class="sxs-lookup"><span data-stu-id="001b7-134">Specifies the properties of the drawing page associated with the drawing page.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="001b7-135">子元素</span><span class="sxs-lookup"><span data-stu-id="001b7-135">Child elements</span></span>

|<span data-ttu-id="001b7-136">**元素**</span><span class="sxs-lookup"><span data-stu-id="001b7-136">**Element**</span></span>|<span data-ttu-id="001b7-137">**类型**</span><span class="sxs-lookup"><span data-stu-id="001b7-137">**Type**</span></span>|<span data-ttu-id="001b7-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="001b7-138">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="001b7-139">RefBy</span><span class="sxs-lookup"><span data-stu-id="001b7-139">RefBy</span></span>](refby-element-trigger_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="001b7-140">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="001b7-140">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-141">指定绘图中的参考 toa 页。</span><span class="sxs-lookup"><span data-stu-id="001b7-141">Specifies a reference toa page in the drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="001b7-142">属性</span><span class="sxs-lookup"><span data-stu-id="001b7-142">Attributes</span></span>

|<span data-ttu-id="001b7-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="001b7-143">**Attribute**</span></span>|<span data-ttu-id="001b7-144">**类型**</span><span class="sxs-lookup"><span data-stu-id="001b7-144">**Type**</span></span>|<span data-ttu-id="001b7-145">**必需**</span><span class="sxs-lookup"><span data-stu-id="001b7-145">**Required**</span></span>|<span data-ttu-id="001b7-146">**说明**</span><span class="sxs-lookup"><span data-stu-id="001b7-146">**Description**</span></span>|<span data-ttu-id="001b7-147">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="001b7-147">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="001b7-148">N</span><span class="sxs-lookup"><span data-stu-id="001b7-148">N</span></span>  <br/> |<span data-ttu-id="001b7-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="001b7-149">xsd:string</span></span>  <br/> |<span data-ttu-id="001b7-150">必需</span><span class="sxs-lookup"><span data-stu-id="001b7-150">required</span></span>  <br/> |<span data-ttu-id="001b7-151">公式中要触发激活时调用的名称。</span><span class="sxs-lookup"><span data-stu-id="001b7-151">The name of the formula to be called when the trigger is activated.</span></span>  <br/> <span data-ttu-id="001b7-152">请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="001b7-152">See the Remarks section.</span></span>  <br/> |<span data-ttu-id="001b7-153">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="001b7-153">Values of the xsd:string type.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="001b7-154">备注</span><span class="sxs-lookup"><span data-stu-id="001b7-154">Remarks</span></span>

<span data-ttu-id="001b7-155">此**Trigger**元素的**N**属性必须为一组有限的对应于触发器说明的值之一。</span><span class="sxs-lookup"><span data-stu-id="001b7-155">The **N** attribute of this **Trigger** element must be one of a limited set of values that correspond to trigger instructions.</span></span> <span data-ttu-id="001b7-156">请参阅下表为确定允许此**触发器**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="001b7-156">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Trigger** element.</span></span> 
  
|<span data-ttu-id="001b7-157">**值**</span><span class="sxs-lookup"><span data-stu-id="001b7-157">**Value**</span></span>|<span data-ttu-id="001b7-158">**父元素**</span><span class="sxs-lookup"><span data-stu-id="001b7-158">**Parent element**</span></span>|<span data-ttu-id="001b7-159">**说明**</span><span class="sxs-lookup"><span data-stu-id="001b7-159">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="001b7-160">CategoryChanged</span><span class="sxs-lookup"><span data-stu-id="001b7-160">CategoryChanged</span></span>  <br/> |[<span data-ttu-id="001b7-161">PageSheet （Page_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-161">PageSheet (Page_Type complexType)</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-162">将出现在形状使用**HASCATEGORIES**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-162">A trigger that appears on a shape when a cross-part reference using a **HASCATEGORIES** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-163">RecalcBkgPageName</span><span class="sxs-lookup"><span data-stu-id="001b7-163">RecalcBkgPageName</span></span>  <br/> |[<span data-ttu-id="001b7-164">PageSheet （Page_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-164">PageSheet (Page_Type complexType)</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-165">当存在使用**BKGPAGENAME**函数的跨部件引用页面上出现触发器</span><span class="sxs-lookup"><span data-stu-id="001b7-165">A trigger that appears on a page when a cross-part reference using a **BKGPAGENAME** function exists</span></span>  <br/> |
|<span data-ttu-id="001b7-166">RecalcColor</span><span class="sxs-lookup"><span data-stu-id="001b7-166">RecalcColor</span></span>  <br/> |[<span data-ttu-id="001b7-167">PageSheet （Page_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-167">PageSheet (Page_Type complexType)</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-168">页面显示的页面或任何及其包含的形状使用**RGB**函数时触发。</span><span class="sxs-lookup"><span data-stu-id="001b7-168">A trigger that appears on a page whenever the page or any of its contained shapes uses a **RGB** function.</span></span>  <br/> |
|<span data-ttu-id="001b7-169">RecalcCreateDT</span><span class="sxs-lookup"><span data-stu-id="001b7-169">RecalcCreateDT</span></span>  <br/> |[<span data-ttu-id="001b7-170">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="001b7-170">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-171">显示文档时使用**DOCCREATION**函数的跨部件引用触发器存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-171">A trigger that appears on a document when a cross-part reference using a **DOCCREATION** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-172">RecalcData1</span><span class="sxs-lookup"><span data-stu-id="001b7-172">RecalcData1</span></span>  <br/> |[<span data-ttu-id="001b7-173">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-173">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-174">将出现在形状使用**DATA1**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-174">A trigger that appears on a shape when a cross-part reference using a **DATA1** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-175">RecalcData2</span><span class="sxs-lookup"><span data-stu-id="001b7-175">RecalcData2</span></span>  <br/> |[<span data-ttu-id="001b7-176">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-176">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-177">将出现在形状使用**DATA2**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-177">A trigger that appears on a shape when a cross-part reference using a **DATA2** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-178">RecalcData3</span><span class="sxs-lookup"><span data-stu-id="001b7-178">RecalcData3</span></span>  <br/> |[<span data-ttu-id="001b7-179">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-179">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-180">将出现在形状使用**DATA3**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-180">A trigger that appears on a shape when a cross-part reference using a **DATA3** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-181">RecalcEditDT</span><span class="sxs-lookup"><span data-stu-id="001b7-181">RecalcEditDT</span></span>  <br/> |[<span data-ttu-id="001b7-182">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="001b7-182">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-183">显示文档时使用**DOCLASTEDIT**函数的跨部件引用触发器存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-183">A trigger that appears on a document when a cross-part reference using a **DOCLASTEDIT** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-184">RecalcID</span><span class="sxs-lookup"><span data-stu-id="001b7-184">RecalcID</span></span>  <br/> |[<span data-ttu-id="001b7-185">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-185">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-186">将出现在形状**ID**函数使用的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-186">A trigger that appears on a shape when a cross-part reference using a **ID** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-187">RecalcMasterName</span><span class="sxs-lookup"><span data-stu-id="001b7-187">RecalcMasterName</span></span>  <br/> |[<span data-ttu-id="001b7-188">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-188">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-189">将出现在形状使用**MASTERNAME**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-189">A trigger that appears on a shape when a cross-part reference using a **MASTERNAME** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-190">RecalcName</span><span class="sxs-lookup"><span data-stu-id="001b7-190">RecalcName</span></span>  <br/> |[<span data-ttu-id="001b7-191">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-191">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-192">使用**NAME**函数的跨部件引用存在时将出现在形状触发。</span><span class="sxs-lookup"><span data-stu-id="001b7-192">A trigger that appears on a shape when a cross-part reference using a **NAME** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-193">RecalcNowAndRand</span><span class="sxs-lookup"><span data-stu-id="001b7-193">RecalcNowAndRand</span></span>  <br/> |[<span data-ttu-id="001b7-194">PageSheet （Page_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-194">PageSheet (Page_Type complexType)</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-195">如果的页面或任何及其包含的形状有**现在**或**RAND**函数显示在页面触发。</span><span class="sxs-lookup"><span data-stu-id="001b7-195">A trigger that appears on a page if either the page or any of its containing shapes have a **NOW** or a **RAND** function.</span></span>  <br/> |
|<span data-ttu-id="001b7-196">RecalcPageCount</span><span class="sxs-lookup"><span data-stu-id="001b7-196">RecalcPageCount</span></span>  <br/> |[<span data-ttu-id="001b7-197">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="001b7-197">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-198">显示文档时使用**PAGECOUNT**函数的跨部件引用触发器存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-198">A trigger that appears on a document when a cross-part reference using a **PAGECOUNT** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-199">RecalcPageName</span><span class="sxs-lookup"><span data-stu-id="001b7-199">RecalcPageName</span></span>  <br/> |[<span data-ttu-id="001b7-200">PageSheet （Page_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-200">PageSheet (Page_Type complexType)</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> [<span data-ttu-id="001b7-201">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-201">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-202">将出现在形状使用**PAGENAME**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-202">A trigger that appears on a shape when a cross-part reference using a **PAGENAME** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-203">RecalcPageNum</span><span class="sxs-lookup"><span data-stu-id="001b7-203">RecalcPageNum</span></span>  <br/> |[<span data-ttu-id="001b7-204">PageSheet （Page_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-204">PageSheet (Page_Type complexType)</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-205">显示在页，使用**PAGENUMBER**函数的跨部件引用存在时触发。</span><span class="sxs-lookup"><span data-stu-id="001b7-205">A trigger that appears on a page when a cross-part reference using a **PAGENUMBER** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-206">RecalcPath</span><span class="sxs-lookup"><span data-stu-id="001b7-206">RecalcPath</span></span>  <br/> |[<span data-ttu-id="001b7-207">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="001b7-207">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-208">将出现在形状使用**POINTALONGPATH**、 **PATHLENGTH**或**PATHSEGMENT**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-208">A trigger that appears on a shape when a cross-part reference using a **POINTALONGPATH**, **PATHLENGTH**, or **PATHSEGMENT** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-209">RecalcPrintDT</span><span class="sxs-lookup"><span data-stu-id="001b7-209">RecalcPrintDT</span></span>  <br/> |[<span data-ttu-id="001b7-210">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="001b7-210">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-211">显示文档时使用**DOCLASTPRINT**函数的跨部件引用触发器存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-211">A trigger that appears on a document when a cross-part reference using a **DOCLASTPRINT** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-212">RecalcSaveDT</span><span class="sxs-lookup"><span data-stu-id="001b7-212">RecalcSaveDT</span></span>  <br/> |[<span data-ttu-id="001b7-213">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="001b7-213">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-214">显示文档时使用**DOCLASTSAVE**函数的跨部件引用触发器存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-214">A trigger that appears on a document when a cross-part reference using a **DOCLASTSAVE** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-215">RecalcSummary</span><span class="sxs-lookup"><span data-stu-id="001b7-215">RecalcSummary</span></span>  <br/> |[<span data-ttu-id="001b7-216">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="001b7-216">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-217">显示文档时使用的**类别**、 **CREATOR**、**说明**、**关键字**、**主题**或**标题**函数的跨部件引用触发器存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-217">A trigger that appears on a document when a cross-part reference using a **CATEGORY**, **CREATOR**, **DESCRIPTION**, **KEYWORDS**, **SUBJECT**, or **TITLE** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-218">RecalcType</span><span class="sxs-lookup"><span data-stu-id="001b7-218">RecalcType</span></span>  <br/> |[<span data-ttu-id="001b7-219">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-219">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-220">使用**类型**函数的跨部件引用存在时将出现在形状触发。</span><span class="sxs-lookup"><span data-stu-id="001b7-220">A trigger that appears on a shape when a cross-part reference using a **TYPE** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-221">RelChanged</span><span class="sxs-lookup"><span data-stu-id="001b7-221">RelChanged</span></span>  <br/> |[<span data-ttu-id="001b7-222">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-222">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-223">将出现在形状使用**CONTAINERMEMBERCOUNT**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-223">A trigger that appears on a shape when a cross-part reference using a **CONTAINERMEMBERCOUNT** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-224">ZOrderChanged</span><span class="sxs-lookup"><span data-stu-id="001b7-224">ZOrderChanged</span></span>  <br/> |[<span data-ttu-id="001b7-225">PageSheet （Page_Type 复杂类型）</span><span class="sxs-lookup"><span data-stu-id="001b7-225">PageSheet (Page_Type complexType)</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-226">显示在页，使用**CONTAINERSHEETREF**函数的跨部件引用存在时触发。</span><span class="sxs-lookup"><span data-stu-id="001b7-226">A trigger that appears on a page when a cross-part reference using a **CONTAINERSHEETREF** function exists.</span></span>  <br/> |
|<span data-ttu-id="001b7-227">路径</span><span class="sxs-lookup"><span data-stu-id="001b7-227">Path</span></span>  <br/> |[<span data-ttu-id="001b7-228">形状</span><span class="sxs-lookup"><span data-stu-id="001b7-228">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="001b7-229">出现在页上，使用**POINTALONGPATH**、 **PATHLENGTH**或**PATHSEGMENT**函数的跨部件引用时触发存在。</span><span class="sxs-lookup"><span data-stu-id="001b7-229">A trigger that appears on a page when a cross-part reference using a **POINTALONGPATH**, **PATHLENGTH**, or **PATHSEGMENT** function exists.</span></span>  <br/> |
   
