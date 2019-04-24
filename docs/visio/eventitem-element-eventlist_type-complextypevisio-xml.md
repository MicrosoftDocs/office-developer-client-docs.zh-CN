---
title: EventItem 元素 (EventList_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6b347117-a1c1-d090-0d71-ea8528ac70c6
description: 封装事件代码。
ms.openlocfilehash: 6ed539bd6cb4524b2498b636295442bed917c72a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337196"
---
# <a name="eventitem-element-eventlisttype-complextype-visio-xml"></a><span data-ttu-id="b9b19-103">EventItem 元素 (EventList_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="b9b19-103">EventItem element (EventList_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="b9b19-104">封装事件代码。</span><span class="sxs-lookup"><span data-stu-id="b9b19-104">Encapsulates an event code.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b9b19-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b9b19-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b9b19-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b9b19-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b9b19-107">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="b9b19-107">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b9b19-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b9b19-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b9b19-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b9b19-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b9b19-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="b9b19-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b9b19-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b9b19-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b9b19-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="b9b19-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b9b19-113">定义</span><span class="sxs-lookup"><span data-stu-id="b9b19-113">Definition</span></span>

```XML
< xs:element name="EventItem" type="EventItem_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b9b19-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b9b19-114">Elements and attributes</span></span>

<span data-ttu-id="b9b19-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b9b19-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b9b19-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b9b19-116">Parent elements</span></span>

|<span data-ttu-id="b9b19-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="b9b19-117">**Element**</span></span>|<span data-ttu-id="b9b19-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="b9b19-118">**Type**</span></span>|<span data-ttu-id="b9b19-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b9b19-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b9b19-120">EventList</span><span class="sxs-lookup"><span data-stu-id="b9b19-120">EventList</span></span>](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b9b19-121">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="b9b19-121">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b9b19-122">包含对象应响应的每个事件的**EventItem**元素。</span><span class="sxs-lookup"><span data-stu-id="b9b19-122">Contains an **EventItem** element for each event to which an object should respond.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="b9b19-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b9b19-123">Child elements</span></span>

<span data-ttu-id="b9b19-124">无。</span><span class="sxs-lookup"><span data-stu-id="b9b19-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b9b19-125">属性</span><span class="sxs-lookup"><span data-stu-id="b9b19-125">Attributes</span></span>

|<span data-ttu-id="b9b19-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="b9b19-126">**Attribute**</span></span>|<span data-ttu-id="b9b19-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="b9b19-127">**Type**</span></span>|<span data-ttu-id="b9b19-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="b9b19-128">**Required**</span></span>|<span data-ttu-id="b9b19-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="b9b19-129">**Description**</span></span>|<span data-ttu-id="b9b19-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b9b19-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9b19-131">操作</span><span class="sxs-lookup"><span data-stu-id="b9b19-131">Action</span></span>  <br/> |<span data-ttu-id="b9b19-132">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="b9b19-132">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="b9b19-133">必需</span><span class="sxs-lookup"><span data-stu-id="b9b19-133">required</span></span>  <br/> |<span data-ttu-id="b9b19-134">指定父**EventItem**元素的操作代码。</span><span class="sxs-lookup"><span data-stu-id="b9b19-134">Specifies the action code of the parent **EventItem** element.</span></span>  <br/> |<span data-ttu-id="b9b19-135">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b9b19-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="b9b19-136">已启用</span><span class="sxs-lookup"><span data-stu-id="b9b19-136">Enabled</span></span>  <br/> |<span data-ttu-id="b9b19-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="b9b19-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="b9b19-138">可选</span><span class="sxs-lookup"><span data-stu-id="b9b19-138">optional</span></span>  <br/> |<span data-ttu-id="b9b19-139">表示一个标志, 该标志指示事件是否已启用或已禁用。</span><span class="sxs-lookup"><span data-stu-id="b9b19-139">Represents a flag indicating if the event is enabled or disabled.</span></span>  <br/> |<span data-ttu-id="b9b19-140">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b9b19-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="b9b19-141">EventCode</span><span class="sxs-lookup"><span data-stu-id="b9b19-141">EventCode</span></span>  <br/> |<span data-ttu-id="b9b19-142">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="b9b19-142">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="b9b19-143">必需</span><span class="sxs-lookup"><span data-stu-id="b9b19-143">required</span></span>  <br/> |<span data-ttu-id="b9b19-144">指示触发加载项的事件的代码。</span><span class="sxs-lookup"><span data-stu-id="b9b19-144">A code indicating the event that triggers the add-on.</span></span>  <br/> |<span data-ttu-id="b9b19-145">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b9b19-145">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="b9b19-146">ID</span><span class="sxs-lookup"><span data-stu-id="b9b19-146">ID</span></span>  <br/> |<span data-ttu-id="b9b19-147">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b9b19-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b9b19-148">必需</span><span class="sxs-lookup"><span data-stu-id="b9b19-148">required</span></span>  <br/> |<span data-ttu-id="b9b19-149">事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="b9b19-149">The ID of the event.</span></span>  <br/> |<span data-ttu-id="b9b19-150">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b9b19-150">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b9b19-151">Target</span><span class="sxs-lookup"><span data-stu-id="b9b19-151">Target</span></span>  <br/> |<span data-ttu-id="b9b19-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b9b19-152">xsd:string</span></span>  <br/> |<span data-ttu-id="b9b19-153">必需</span><span class="sxs-lookup"><span data-stu-id="b9b19-153">required</span></span>  <br/> |<span data-ttu-id="b9b19-154">指定事件的目标。</span><span class="sxs-lookup"><span data-stu-id="b9b19-154">Specifies the target of an event.</span></span>  <br/> |<span data-ttu-id="b9b19-155">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b9b19-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b9b19-156">TargetArgs</span><span class="sxs-lookup"><span data-stu-id="b9b19-156">TargetArgs</span></span>  <br/> |<span data-ttu-id="b9b19-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b9b19-157">xsd:string</span></span>  <br/> |<span data-ttu-id="b9b19-158">必需</span><span class="sxs-lookup"><span data-stu-id="b9b19-158">required</span></span>  <br/> |<span data-ttu-id="b9b19-159">指定一个字符串, 其中包含要发送到事件目标的参数。</span><span class="sxs-lookup"><span data-stu-id="b9b19-159">Specifies a string containing arguments to be sent to the target of an event.</span></span>  <br/> |<span data-ttu-id="b9b19-160">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b9b19-160">Values of the xsd:string type.</span></span>  <br/> |
   

