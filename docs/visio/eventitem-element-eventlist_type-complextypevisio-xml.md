---
title: EventItem 元素 （EventList_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6b347117-a1c1-d090-0d71-ea8528ac70c6
description: 封装了事件代码。
ms.openlocfilehash: dcdd3aa264e8ddfb1aa6f2e908f1c43a0d470872
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780195"
---
# <a name="eventitem-element-eventlisttype-complextype-visio-xml"></a><span data-ttu-id="c2068-103">EventItem 元素 （EventList_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c2068-103">EventItem element (EventList_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="c2068-104">封装了事件代码。</span><span class="sxs-lookup"><span data-stu-id="c2068-104">Encapsulates an event code.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c2068-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c2068-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c2068-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c2068-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c2068-107">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="c2068-107">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c2068-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c2068-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c2068-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c2068-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c2068-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="c2068-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c2068-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c2068-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c2068-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="c2068-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c2068-113">定义</span><span class="sxs-lookup"><span data-stu-id="c2068-113">Definition</span></span>

```XML
< xs:element name="EventItem" type="EventItem_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c2068-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c2068-114">Elements and attributes</span></span>

<span data-ttu-id="c2068-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c2068-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c2068-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c2068-116">Parent elements</span></span>

|<span data-ttu-id="c2068-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c2068-117">**Element**</span></span>|<span data-ttu-id="c2068-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c2068-118">**Type**</span></span>|<span data-ttu-id="c2068-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c2068-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c2068-120">EventList</span><span class="sxs-lookup"><span data-stu-id="c2068-120">EventList</span></span>](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c2068-121">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="c2068-121">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c2068-122">包含与对象应响应每个事件**EventItem**元素。</span><span class="sxs-lookup"><span data-stu-id="c2068-122">Contains an **EventItem** element for each event to which an object should respond.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c2068-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c2068-123">Child elements</span></span>

<span data-ttu-id="c2068-124">无。</span><span class="sxs-lookup"><span data-stu-id="c2068-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c2068-125">属性</span><span class="sxs-lookup"><span data-stu-id="c2068-125">Attributes</span></span>

|<span data-ttu-id="c2068-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="c2068-126">**Attribute**</span></span>|<span data-ttu-id="c2068-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="c2068-127">**Type**</span></span>|<span data-ttu-id="c2068-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="c2068-128">**Required**</span></span>|<span data-ttu-id="c2068-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="c2068-129">**Description**</span></span>|<span data-ttu-id="c2068-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c2068-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2068-131">操作</span><span class="sxs-lookup"><span data-stu-id="c2068-131">Action</span></span>  <br/> |<span data-ttu-id="c2068-132">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c2068-132">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="c2068-133">必需</span><span class="sxs-lookup"><span data-stu-id="c2068-133">required</span></span>  <br/> |<span data-ttu-id="c2068-134">指定父**EventItem**元素的动作代码。</span><span class="sxs-lookup"><span data-stu-id="c2068-134">Specifies the action code of the parent **EventItem** element.</span></span>  <br/> |<span data-ttu-id="c2068-135">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2068-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="c2068-136">已启用</span><span class="sxs-lookup"><span data-stu-id="c2068-136">Enabled</span></span>  <br/> |<span data-ttu-id="c2068-137">化</span><span class="sxs-lookup"><span data-stu-id="c2068-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c2068-138">可选</span><span class="sxs-lookup"><span data-stu-id="c2068-138">optional</span></span>  <br/> |<span data-ttu-id="c2068-139">代表一个标志，指示是否启用或禁用事件。</span><span class="sxs-lookup"><span data-stu-id="c2068-139">Represents a flag indicating if the event is enabled or disabled.</span></span>  <br/> |<span data-ttu-id="c2068-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2068-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c2068-141">EventCode</span><span class="sxs-lookup"><span data-stu-id="c2068-141">EventCode</span></span>  <br/> |<span data-ttu-id="c2068-142">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c2068-142">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="c2068-143">必需</span><span class="sxs-lookup"><span data-stu-id="c2068-143">required</span></span>  <br/> |<span data-ttu-id="c2068-144">指示的事件的触发该加载项的代码。</span><span class="sxs-lookup"><span data-stu-id="c2068-144">A code indicating the event that triggers the add-on.</span></span>  <br/> |<span data-ttu-id="c2068-145">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2068-145">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="c2068-146">ID</span><span class="sxs-lookup"><span data-stu-id="c2068-146">ID</span></span>  <br/> |<span data-ttu-id="c2068-147">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="c2068-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="c2068-148">必需</span><span class="sxs-lookup"><span data-stu-id="c2068-148">required</span></span>  <br/> |<span data-ttu-id="c2068-149">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="c2068-149">The ID of the event.</span></span>  <br/> |<span data-ttu-id="c2068-150">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2068-150">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="c2068-151">目标</span><span class="sxs-lookup"><span data-stu-id="c2068-151">Target</span></span>  <br/> |<span data-ttu-id="c2068-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c2068-152">xsd:string</span></span>  <br/> |<span data-ttu-id="c2068-153">必需</span><span class="sxs-lookup"><span data-stu-id="c2068-153">required</span></span>  <br/> |<span data-ttu-id="c2068-154">指定事件的目标。</span><span class="sxs-lookup"><span data-stu-id="c2068-154">Specifies the target of an event.</span></span>  <br/> |<span data-ttu-id="c2068-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2068-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c2068-156">TargetArgs</span><span class="sxs-lookup"><span data-stu-id="c2068-156">TargetArgs</span></span>  <br/> |<span data-ttu-id="c2068-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c2068-157">xsd:string</span></span>  <br/> |<span data-ttu-id="c2068-158">必需</span><span class="sxs-lookup"><span data-stu-id="c2068-158">required</span></span>  <br/> |<span data-ttu-id="c2068-159">指定包含要发送到目标事件的参数字符串。</span><span class="sxs-lookup"><span data-stu-id="c2068-159">Specifies a string containing arguments to be sent to the target of an event.</span></span>  <br/> |<span data-ttu-id="c2068-160">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2068-160">Values of the xsd:string type.</span></span>  <br/> |
   

