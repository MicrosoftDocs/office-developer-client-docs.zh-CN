---
title: EventItem 元素 (EventList_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6b347117-a1c1-d090-0d71-ea8528ac70c6
description: 封装事件代码。
ms.openlocfilehash: 0db88a175d3e0330cb648f870559d9d2bd4dc1d8
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541838"
---
# <a name="eventitem-element-eventlisttype-complextype-visio-xml"></a><span data-ttu-id="09451-103">EventItem 元素 (EventList_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="09451-103">EventItem element (EventList_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="09451-104">封装事件代码。</span><span class="sxs-lookup"><span data-stu-id="09451-104">Encapsulates an event code.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="09451-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="09451-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="09451-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="09451-106">**Element type**</span></span> <br/> |[<span data-ttu-id="09451-107">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="09451-107">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="09451-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="09451-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="09451-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="09451-109">**Schema file**</span></span> <br/> |<span data-ttu-id="09451-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="09451-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="09451-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="09451-111">**Document parts**</span></span> <br/> |<span data-ttu-id="09451-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="09451-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="09451-113">定义</span><span class="sxs-lookup"><span data-stu-id="09451-113">Definition</span></span>

```XML
< xs:element name="EventItem" type="EventItem_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="09451-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="09451-114">Elements and attributes</span></span>

<span data-ttu-id="09451-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="09451-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="09451-116">父元素</span><span class="sxs-lookup"><span data-stu-id="09451-116">Parent elements</span></span>

|<span data-ttu-id="09451-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="09451-117">**Element**</span></span>|<span data-ttu-id="09451-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="09451-118">**Type**</span></span>|<span data-ttu-id="09451-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="09451-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="09451-120">EventList</span><span class="sxs-lookup"><span data-stu-id="09451-120">EventList</span></span>](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="09451-121">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="09451-121">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="09451-122">包含对象应响应的每个事件的**EventItem**元素。</span><span class="sxs-lookup"><span data-stu-id="09451-122">Contains an **EventItem** element for each event to which an object should respond.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="09451-123">子元素</span><span class="sxs-lookup"><span data-stu-id="09451-123">Child elements</span></span>

<span data-ttu-id="09451-124">无。</span><span class="sxs-lookup"><span data-stu-id="09451-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="09451-125">属性</span><span class="sxs-lookup"><span data-stu-id="09451-125">Attributes</span></span>

|<span data-ttu-id="09451-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="09451-126">**Attribute**</span></span>|<span data-ttu-id="09451-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="09451-127">**Type**</span></span>|<span data-ttu-id="09451-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="09451-128">**Required**</span></span>|<span data-ttu-id="09451-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="09451-129">**Description**</span></span>|<span data-ttu-id="09451-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="09451-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09451-131">操作</span><span class="sxs-lookup"><span data-stu-id="09451-131">Action</span></span>  <br/> |<span data-ttu-id="09451-132">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="09451-132">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="09451-133">必需</span><span class="sxs-lookup"><span data-stu-id="09451-133">required</span></span>  <br/> |<span data-ttu-id="09451-134">指定父**EventItem**元素的操作代码。</span><span class="sxs-lookup"><span data-stu-id="09451-134">Specifies the action code of the parent **EventItem** element.</span></span>  <br/> |<span data-ttu-id="09451-135">Xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="09451-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="09451-136">已启用</span><span class="sxs-lookup"><span data-stu-id="09451-136">Enabled</span></span>  <br/> |<span data-ttu-id="09451-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="09451-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="09451-138">可选</span><span class="sxs-lookup"><span data-stu-id="09451-138">optional</span></span>  <br/> |<span data-ttu-id="09451-139">表示一个标志, 该标志指示事件是否已启用或已禁用。</span><span class="sxs-lookup"><span data-stu-id="09451-139">Represents a flag indicating if the event is enabled or disabled.</span></span>  <br/> |<span data-ttu-id="09451-140">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="09451-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="09451-141">EventCode</span><span class="sxs-lookup"><span data-stu-id="09451-141">EventCode</span></span>  <br/> |<span data-ttu-id="09451-142">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="09451-142">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="09451-143">必需</span><span class="sxs-lookup"><span data-stu-id="09451-143">required</span></span>  <br/> |<span data-ttu-id="09451-144">指示触发加载项的事件的代码。</span><span class="sxs-lookup"><span data-stu-id="09451-144">A code indicating the event that triggers the add-on.</span></span>  <br/> |<span data-ttu-id="09451-145">Xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="09451-145">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="09451-146">ID</span><span class="sxs-lookup"><span data-stu-id="09451-146">ID</span></span>  <br/> |<span data-ttu-id="09451-147">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="09451-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="09451-148">必需</span><span class="sxs-lookup"><span data-stu-id="09451-148">required</span></span>  <br/> |<span data-ttu-id="09451-149">事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="09451-149">The ID of the event.</span></span>  <br/> |<span data-ttu-id="09451-150">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="09451-150">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="09451-151">Target</span><span class="sxs-lookup"><span data-stu-id="09451-151">Target</span></span>  <br/> |<span data-ttu-id="09451-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="09451-152">xsd:string</span></span>  <br/> |<span data-ttu-id="09451-153">必需</span><span class="sxs-lookup"><span data-stu-id="09451-153">required</span></span>  <br/> |<span data-ttu-id="09451-154">指定事件的目标。</span><span class="sxs-lookup"><span data-stu-id="09451-154">Specifies the target of an event.</span></span>  <br/> |<span data-ttu-id="09451-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="09451-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="09451-156">TargetArgs</span><span class="sxs-lookup"><span data-stu-id="09451-156">TargetArgs</span></span>  <br/> |<span data-ttu-id="09451-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="09451-157">xsd:string</span></span>  <br/> |<span data-ttu-id="09451-158">必需</span><span class="sxs-lookup"><span data-stu-id="09451-158">required</span></span>  <br/> |<span data-ttu-id="09451-159">指定一个字符串, 其中包含要发送到事件目标的参数。</span><span class="sxs-lookup"><span data-stu-id="09451-159">Specifies a string containing arguments to be sent to the target of an event.</span></span>  <br/> |<span data-ttu-id="09451-160">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="09451-160">Values of the xsd:string type.</span></span>  <br/> |
   

