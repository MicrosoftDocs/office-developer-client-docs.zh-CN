---
title: 'EventItem 元素 (EventList_Type COMPLEXType)  (Visio XML) '
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
# <a name="eventitem-element-eventlist_type-complextype-visio-xml"></a><span data-ttu-id="fdc27-103">EventItem 元素 (EventList_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="fdc27-103">EventItem element (EventList_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="fdc27-104">封装事件代码。</span><span class="sxs-lookup"><span data-stu-id="fdc27-104">Encapsulates an event code.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="fdc27-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="fdc27-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fdc27-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="fdc27-106">**Element type**</span></span> <br/> |[<span data-ttu-id="fdc27-107">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="fdc27-107">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="fdc27-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fdc27-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="fdc27-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fdc27-109">**Schema file**</span></span> <br/> |<span data-ttu-id="fdc27-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="fdc27-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="fdc27-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="fdc27-111">**Document parts**</span></span> <br/> |<span data-ttu-id="fdc27-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="fdc27-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fdc27-113">定义</span><span class="sxs-lookup"><span data-stu-id="fdc27-113">Definition</span></span>

```XML
< xs:element name="EventItem" type="EventItem_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="fdc27-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fdc27-114">Elements and attributes</span></span>

<span data-ttu-id="fdc27-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="fdc27-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="fdc27-116">父元素</span><span class="sxs-lookup"><span data-stu-id="fdc27-116">Parent elements</span></span>

|<span data-ttu-id="fdc27-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="fdc27-117">**Element**</span></span>|<span data-ttu-id="fdc27-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="fdc27-118">**Type**</span></span>|<span data-ttu-id="fdc27-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="fdc27-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fdc27-120">EventList</span><span class="sxs-lookup"><span data-stu-id="fdc27-120">EventList</span></span>](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fdc27-121">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="fdc27-121">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fdc27-122">包含对象应响应的每个事件的 **EventItem** 元素。</span><span class="sxs-lookup"><span data-stu-id="fdc27-122">Contains an **EventItem** element for each event to which an object should respond.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="fdc27-123">子元素</span><span class="sxs-lookup"><span data-stu-id="fdc27-123">Child elements</span></span>

<span data-ttu-id="fdc27-124">无。</span><span class="sxs-lookup"><span data-stu-id="fdc27-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="fdc27-125">属性</span><span class="sxs-lookup"><span data-stu-id="fdc27-125">Attributes</span></span>

|<span data-ttu-id="fdc27-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="fdc27-126">**Attribute**</span></span>|<span data-ttu-id="fdc27-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="fdc27-127">**Type**</span></span>|<span data-ttu-id="fdc27-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="fdc27-128">**Required**</span></span>|<span data-ttu-id="fdc27-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="fdc27-129">**Description**</span></span>|<span data-ttu-id="fdc27-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fdc27-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fdc27-131">Action</span><span class="sxs-lookup"><span data-stu-id="fdc27-131">Action</span></span>  <br/> |<span data-ttu-id="fdc27-132">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="fdc27-132">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="fdc27-133">必需</span><span class="sxs-lookup"><span data-stu-id="fdc27-133">required</span></span>  <br/> |<span data-ttu-id="fdc27-134">指定父 **EventItem** 元素的操作代码。</span><span class="sxs-lookup"><span data-stu-id="fdc27-134">Specifies the action code of the parent **EventItem** element.</span></span>  <br/> |<span data-ttu-id="fdc27-135">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fdc27-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="fdc27-136">已启用</span><span class="sxs-lookup"><span data-stu-id="fdc27-136">Enabled</span></span>  <br/> |<span data-ttu-id="fdc27-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="fdc27-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="fdc27-138">可选</span><span class="sxs-lookup"><span data-stu-id="fdc27-138">optional</span></span>  <br/> |<span data-ttu-id="fdc27-139">表示一个标志，指示是启用还是禁用该事件。</span><span class="sxs-lookup"><span data-stu-id="fdc27-139">Represents a flag indicating if the event is enabled or disabled.</span></span>  <br/> |<span data-ttu-id="fdc27-140">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fdc27-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="fdc27-141">EventCode</span><span class="sxs-lookup"><span data-stu-id="fdc27-141">EventCode</span></span>  <br/> |<span data-ttu-id="fdc27-142">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="fdc27-142">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="fdc27-143">必需</span><span class="sxs-lookup"><span data-stu-id="fdc27-143">required</span></span>  <br/> |<span data-ttu-id="fdc27-144">指示触发加载项的事件的代码。</span><span class="sxs-lookup"><span data-stu-id="fdc27-144">A code indicating the event that triggers the add-on.</span></span>  <br/> |<span data-ttu-id="fdc27-145">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fdc27-145">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="fdc27-146">ID</span><span class="sxs-lookup"><span data-stu-id="fdc27-146">ID</span></span>  <br/> |<span data-ttu-id="fdc27-147">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fdc27-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fdc27-148">必需</span><span class="sxs-lookup"><span data-stu-id="fdc27-148">required</span></span>  <br/> |<span data-ttu-id="fdc27-149">事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="fdc27-149">The ID of the event.</span></span>  <br/> |<span data-ttu-id="fdc27-150">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fdc27-150">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="fdc27-151">Target</span><span class="sxs-lookup"><span data-stu-id="fdc27-151">Target</span></span>  <br/> |<span data-ttu-id="fdc27-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fdc27-152">xsd:string</span></span>  <br/> |<span data-ttu-id="fdc27-153">必需</span><span class="sxs-lookup"><span data-stu-id="fdc27-153">required</span></span>  <br/> |<span data-ttu-id="fdc27-154">指定事件的目标。</span><span class="sxs-lookup"><span data-stu-id="fdc27-154">Specifies the target of an event.</span></span>  <br/> |<span data-ttu-id="fdc27-155">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fdc27-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="fdc27-156">TargetArgs</span><span class="sxs-lookup"><span data-stu-id="fdc27-156">TargetArgs</span></span>  <br/> |<span data-ttu-id="fdc27-157">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fdc27-157">xsd:string</span></span>  <br/> |<span data-ttu-id="fdc27-158">必需</span><span class="sxs-lookup"><span data-stu-id="fdc27-158">required</span></span>  <br/> |<span data-ttu-id="fdc27-159">指定包含要发送到事件目标的参数的字符串。</span><span class="sxs-lookup"><span data-stu-id="fdc27-159">Specifies a string containing arguments to be sent to the target of an event.</span></span>  <br/> |<span data-ttu-id="fdc27-160">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fdc27-160">Values of the xsd:string type.</span></span>  <br/> |
   

