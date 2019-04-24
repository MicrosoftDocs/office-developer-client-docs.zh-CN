---
title: EventList 元素 (VisioDocument_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 40bb8c7c-89ef-22e1-5edf-e2423fc89660
description: 包含对象应响应的每个事件的 EventItem 元素。
ms.openlocfilehash: 5331f1b4a510b05b862f8c7c6306c89c6be4d9f0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351049"
---
# <a name="eventlist-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="83320-103">EventList 元素 (VisioDocument_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="83320-103">EventList element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="83320-104">包含对象应响应的每个事件的**EventItem**元素。</span><span class="sxs-lookup"><span data-stu-id="83320-104">Contains an **EventItem** element for each event to which an object should respond.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="83320-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="83320-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="83320-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="83320-106">**Element type**</span></span> <br/> |[<span data-ttu-id="83320-107">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="83320-107">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="83320-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="83320-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="83320-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="83320-109">**Schema file**</span></span> <br/> |<span data-ttu-id="83320-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="83320-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="83320-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="83320-111">**Document parts**</span></span> <br/> |<span data-ttu-id="83320-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="83320-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="83320-113">定义</span><span class="sxs-lookup"><span data-stu-id="83320-113">Definition</span></span>

```XML
< xs:element name="EventList" type="EventList_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="83320-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="83320-114">Elements and attributes</span></span>

<span data-ttu-id="83320-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="83320-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="83320-116">父元素</span><span class="sxs-lookup"><span data-stu-id="83320-116">Parent elements</span></span>

|<span data-ttu-id="83320-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="83320-117">**Element**</span></span>|<span data-ttu-id="83320-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="83320-118">**Type**</span></span>|<span data-ttu-id="83320-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="83320-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="83320-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="83320-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="83320-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="83320-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="83320-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="83320-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="83320-123">子元素</span><span class="sxs-lookup"><span data-stu-id="83320-123">Child elements</span></span>

|<span data-ttu-id="83320-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="83320-124">**Element**</span></span>|<span data-ttu-id="83320-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="83320-125">**Type**</span></span>|<span data-ttu-id="83320-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="83320-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="83320-127">EventItem</span><span class="sxs-lookup"><span data-stu-id="83320-127">EventItem</span></span>](eventitem-element-eventlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="83320-128">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="83320-128">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="83320-129">封装事件代码。</span><span class="sxs-lookup"><span data-stu-id="83320-129">Encapsulates an event code.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="83320-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="83320-130">Attributes</span></span>

<span data-ttu-id="83320-131">无。</span><span class="sxs-lookup"><span data-stu-id="83320-131">None.</span></span>
  

