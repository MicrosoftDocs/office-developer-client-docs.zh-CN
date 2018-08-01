---
title: PublishSettings 元素 （VisioDocument_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d0a41494-ffad-c56c-2074-135b3d0bffb9
description: 指定在 Microsoft SharePoint Server 2013 中使用 Visio Services 打开图表时使用的设置。
ms.openlocfilehash: f2554facc47de23104f65b26ae19cfc71821bd37
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781000"
---
# <a name="publishsettings-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="4e871-103">PublishSettings 元素 （VisioDocument_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4e871-103">PublishSettings element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="4e871-104">指定在 Microsoft SharePoint Server 2013 中使用 Visio Services 打开图表时使用的设置。</span><span class="sxs-lookup"><span data-stu-id="4e871-104">Specifies the settings that are used when the diagram is opened using Visio Services in Microsoft SharePoint Server 2013.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4e871-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4e871-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4e871-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4e871-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4e871-107">PublishSettings_Type</span><span class="sxs-lookup"><span data-stu-id="4e871-107">PublishSettings_Type</span></span>](publishsettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4e871-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4e871-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4e871-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4e871-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4e871-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="4e871-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4e871-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4e871-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4e871-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="4e871-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4e871-113">定义</span><span class="sxs-lookup"><span data-stu-id="4e871-113">Definition</span></span>

```XML
< xs:element name="PublishSettings" type="PublishSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4e871-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4e871-114">Elements and attributes</span></span>

<span data-ttu-id="4e871-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4e871-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4e871-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4e871-116">Parent elements</span></span>

|<span data-ttu-id="4e871-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4e871-117">**Element**</span></span>|<span data-ttu-id="4e871-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4e871-118">**Type**</span></span>|<span data-ttu-id="4e871-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4e871-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4e871-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="4e871-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="4e871-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="4e871-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4e871-122">指定绘图的属性。</span><span class="sxs-lookup"><span data-stu-id="4e871-122">Specifies properties of a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4e871-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4e871-123">Child elements</span></span>

|<span data-ttu-id="4e871-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="4e871-124">**Element**</span></span>|<span data-ttu-id="4e871-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="4e871-125">**Type**</span></span>|<span data-ttu-id="4e871-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="4e871-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4e871-127">PublishedPage</span><span class="sxs-lookup"><span data-stu-id="4e871-127">PublishedPage</span></span>](publishedpage-element-publishsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4e871-128">PublishedPage_Type</span><span class="sxs-lookup"><span data-stu-id="4e871-128">PublishedPage_Type</span></span>](publishedpage_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4e871-129">指定绘图页是否在使用 Visio Services 在浏览器中查看。</span><span class="sxs-lookup"><span data-stu-id="4e871-129">Specifies whether a drawing page is viewable in the browser using Visio Services.</span></span>  <br/> |
|[<span data-ttu-id="4e871-130">RefreshableData</span><span class="sxs-lookup"><span data-stu-id="4e871-130">RefreshableData</span></span>](refreshabledata-element-publishsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4e871-131">RefreshableData_Type</span><span class="sxs-lookup"><span data-stu-id="4e871-131">RefreshableData_Type</span></span>](refreshabledata_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4e871-132">指定记录集是否可刷新使用 Visio Services。</span><span class="sxs-lookup"><span data-stu-id="4e871-132">Specifies whether a recordset is refreshable using Visio Services.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="4e871-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="4e871-133">Attributes</span></span>

<span data-ttu-id="4e871-134">无。</span><span class="sxs-lookup"><span data-stu-id="4e871-134">None.</span></span>
  

