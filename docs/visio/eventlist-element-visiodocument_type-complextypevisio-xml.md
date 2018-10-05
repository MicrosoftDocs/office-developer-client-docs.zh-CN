---
title: EventList 元素 （VisioDocument_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 40bb8c7c-89ef-22e1-5edf-e2423fc89660
description: 包含与对象应响应每个事件 EventItem 元素。
ms.openlocfilehash: 5331f1b4a510b05b862f8c7c6306c89c6be4d9f0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383973"
---
# <a name="eventlist-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="b7439-103">EventList 元素 （VisioDocument_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b7439-103">EventList element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="b7439-104">包含与对象应响应每个事件**EventItem**元素。</span><span class="sxs-lookup"><span data-stu-id="b7439-104">Contains an **EventItem** element for each event to which an object should respond.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="b7439-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b7439-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b7439-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b7439-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b7439-107">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="b7439-107">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b7439-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b7439-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b7439-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b7439-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b7439-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="b7439-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b7439-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b7439-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b7439-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="b7439-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b7439-113">定义</span><span class="sxs-lookup"><span data-stu-id="b7439-113">Definition</span></span>

```XML
< xs:element name="EventList" type="EventList_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b7439-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b7439-114">Elements and attributes</span></span>

<span data-ttu-id="b7439-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b7439-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b7439-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b7439-116">Parent elements</span></span>

|<span data-ttu-id="b7439-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="b7439-117">**Element**</span></span>|<span data-ttu-id="b7439-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="b7439-118">**Type**</span></span>|<span data-ttu-id="b7439-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7439-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b7439-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="b7439-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="b7439-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="b7439-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b7439-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="b7439-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="b7439-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b7439-123">Child elements</span></span>

|<span data-ttu-id="b7439-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="b7439-124">**Element**</span></span>|<span data-ttu-id="b7439-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="b7439-125">**Type**</span></span>|<span data-ttu-id="b7439-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7439-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b7439-127">EventItem</span><span class="sxs-lookup"><span data-stu-id="b7439-127">EventItem</span></span>](eventitem-element-eventlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b7439-128">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="b7439-128">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b7439-129">封装了事件代码。</span><span class="sxs-lookup"><span data-stu-id="b7439-129">Encapsulates an event code.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="b7439-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="b7439-130">Attributes</span></span>

<span data-ttu-id="b7439-131">无。</span><span class="sxs-lookup"><span data-stu-id="b7439-131">None.</span></span>
  

