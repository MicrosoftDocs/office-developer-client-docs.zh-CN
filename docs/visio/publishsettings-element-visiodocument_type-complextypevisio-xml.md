---
title: PublishSettings 元素 (VisioDocument_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d0a41494-ffad-c56c-2074-135b3d0bffb9
description: 指定在 Microsoft SharePoint Server 2013 中使用 Visio Services 打开图表时使用的设置。
ms.openlocfilehash: 611dfe477228995bca6aedff27b468a2d57e7e85
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541356"
---
# <a name="publishsettings-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="4de31-103">PublishSettings 元素 (VisioDocument_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4de31-103">PublishSettings element (VisioDocument_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="4de31-104">指定在 Microsoft SharePoint Server 2013 中使用 Visio Services 打开图表时使用的设置。</span><span class="sxs-lookup"><span data-stu-id="4de31-104">Specifies the settings that are used when the diagram is opened using Visio Services in Microsoft SharePoint Server 2013.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4de31-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4de31-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4de31-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4de31-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4de31-107">PublishSettings_Type</span><span class="sxs-lookup"><span data-stu-id="4de31-107">PublishSettings_Type</span></span>](publishsettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4de31-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4de31-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4de31-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4de31-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4de31-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="4de31-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4de31-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4de31-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4de31-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="4de31-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4de31-113">定义</span><span class="sxs-lookup"><span data-stu-id="4de31-113">Definition</span></span>

```XML
< xs:element name="PublishSettings" type="PublishSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4de31-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4de31-114">Elements and attributes</span></span>

<span data-ttu-id="4de31-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="4de31-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4de31-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4de31-116">Parent elements</span></span>

|<span data-ttu-id="4de31-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4de31-117">**Element**</span></span>|<span data-ttu-id="4de31-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4de31-118">**Type**</span></span>|<span data-ttu-id="4de31-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4de31-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4de31-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="4de31-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="4de31-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="4de31-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4de31-122">指定绘图的属性。</span><span class="sxs-lookup"><span data-stu-id="4de31-122">Specifies properties of a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4de31-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4de31-123">Child elements</span></span>

|<span data-ttu-id="4de31-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="4de31-124">**Element**</span></span>|<span data-ttu-id="4de31-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="4de31-125">**Type**</span></span>|<span data-ttu-id="4de31-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="4de31-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4de31-127">PublishedPage</span><span class="sxs-lookup"><span data-stu-id="4de31-127">PublishedPage</span></span>](publishedpage-element-publishsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4de31-128">PublishedPage_Type</span><span class="sxs-lookup"><span data-stu-id="4de31-128">PublishedPage_Type</span></span>](publishedpage_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4de31-129">指定是否可在使用 Visio Services 的浏览器中查看绘图页。</span><span class="sxs-lookup"><span data-stu-id="4de31-129">Specifies whether a drawing page is viewable in the browser using Visio Services.</span></span>  <br/> |
|[<span data-ttu-id="4de31-130">RefreshableData</span><span class="sxs-lookup"><span data-stu-id="4de31-130">RefreshableData</span></span>](refreshabledata-element-publishsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4de31-131">RefreshableData_Type</span><span class="sxs-lookup"><span data-stu-id="4de31-131">RefreshableData_Type</span></span>](refreshabledata_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4de31-132">指定是否使用 Visio Services 可刷新 recordset。</span><span class="sxs-lookup"><span data-stu-id="4de31-132">Specifies whether a recordset is refreshable using Visio Services.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="4de31-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="4de31-133">Attributes</span></span>

<span data-ttu-id="4de31-134">无。</span><span class="sxs-lookup"><span data-stu-id="4de31-134">None.</span></span>
  

