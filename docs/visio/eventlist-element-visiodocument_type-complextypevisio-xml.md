---
title: EventList 元素 （VisioDocument_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 40bb8c7c-89ef-22e1-5edf-e2423fc89660
description: 包含与对象应响应每个事件 EventItem 元素。
ms.openlocfilehash: e1033ae93ca272b8ea1d9855d08ad13a444612db
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780191"
---
# <a name="eventlist-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="0a64e-103">EventList 元素 （VisioDocument_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="0a64e-103">EventList element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="0a64e-104">包含与对象应响应每个事件**EventItem**元素。</span><span class="sxs-lookup"><span data-stu-id="0a64e-104">Contains an **EventItem** element for each event to which an object should respond.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="0a64e-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="0a64e-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0a64e-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="0a64e-106">**Element type**</span></span> <br/> |[<span data-ttu-id="0a64e-107">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="0a64e-107">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="0a64e-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0a64e-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="0a64e-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0a64e-109">**Schema file**</span></span> <br/> |<span data-ttu-id="0a64e-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="0a64e-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="0a64e-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="0a64e-111">**Document parts**</span></span> <br/> |<span data-ttu-id="0a64e-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="0a64e-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0a64e-113">定义</span><span class="sxs-lookup"><span data-stu-id="0a64e-113">Definition</span></span>

```XML
< xs:element name="EventList" type="EventList_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="0a64e-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0a64e-114">Elements and attributes</span></span>

<span data-ttu-id="0a64e-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0a64e-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="0a64e-116">父元素</span><span class="sxs-lookup"><span data-stu-id="0a64e-116">Parent elements</span></span>

|<span data-ttu-id="0a64e-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="0a64e-117">**Element**</span></span>|<span data-ttu-id="0a64e-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="0a64e-118">**Type**</span></span>|<span data-ttu-id="0a64e-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a64e-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0a64e-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="0a64e-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="0a64e-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="0a64e-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0a64e-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="0a64e-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="0a64e-123">子元素</span><span class="sxs-lookup"><span data-stu-id="0a64e-123">Child elements</span></span>

|<span data-ttu-id="0a64e-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="0a64e-124">**Element**</span></span>|<span data-ttu-id="0a64e-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="0a64e-125">**Type**</span></span>|<span data-ttu-id="0a64e-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a64e-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0a64e-127">EventItem</span><span class="sxs-lookup"><span data-stu-id="0a64e-127">EventItem</span></span>](eventitem-element-eventlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0a64e-128">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="0a64e-128">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0a64e-129">封装了事件代码。</span><span class="sxs-lookup"><span data-stu-id="0a64e-129">Encapsulates an event code.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="0a64e-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="0a64e-130">Attributes</span></span>

<span data-ttu-id="0a64e-131">无。</span><span class="sxs-lookup"><span data-stu-id="0a64e-131">None.</span></span>
  

