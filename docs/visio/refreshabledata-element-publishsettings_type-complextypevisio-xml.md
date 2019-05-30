---
title: RefreshableData 元素 (PublishSettings_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9a3b9d5a-fcba-eb18-3199-bd5a7f889af8
description: 指定是否可使用 Microsoft SharePoint Server 2013 中的 Visio Services 可刷新 recordset。
ms.openlocfilehash: 21a0a5c198998c4b230be88c6bd9f96b25265990
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542875"
---
# <a name="refreshabledata-element-publishsettingstype-complextype-visio-xml"></a><span data-ttu-id="1888b-103">RefreshableData 元素 (PublishSettings_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="1888b-103">RefreshableData element (PublishSettings_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="1888b-104">指定是否可使用 Microsoft SharePoint Server 2013 中的 Visio Services 可刷新 recordset。</span><span class="sxs-lookup"><span data-stu-id="1888b-104">Specifies whether a recordset is refreshable using Visio Services in Microsoft SharePoint Server 2013.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="1888b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="1888b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1888b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="1888b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="1888b-107">RefreshableData_Type</span><span class="sxs-lookup"><span data-stu-id="1888b-107">RefreshableData_Type</span></span>](refreshabledata_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="1888b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1888b-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="1888b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1888b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="1888b-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="1888b-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="1888b-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="1888b-111">**Document parts**</span></span> <br/> |<span data-ttu-id="1888b-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="1888b-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1888b-113">定义</span><span class="sxs-lookup"><span data-stu-id="1888b-113">Definition</span></span>

```XML
<xs:element name="RefreshableData" type="RefreshableData_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >

```

## <a name="elements-and-attributes"></a><span data-ttu-id="1888b-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1888b-114">Elements and attributes</span></span>

<span data-ttu-id="1888b-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="1888b-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="1888b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="1888b-116">Parent elements</span></span>

|<span data-ttu-id="1888b-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="1888b-117">**Element**</span></span>|<span data-ttu-id="1888b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="1888b-118">**Type**</span></span>|<span data-ttu-id="1888b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="1888b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1888b-120">PublishSettings</span><span class="sxs-lookup"><span data-stu-id="1888b-120">PublishSettings</span></span>](publishsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1888b-121">PublishSettings_Type</span><span class="sxs-lookup"><span data-stu-id="1888b-121">PublishSettings_Type</span></span>](publishsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1888b-122">指定使用 Visio Services 打开图表时使用的设置。</span><span class="sxs-lookup"><span data-stu-id="1888b-122">Specifies the settings that are used when the diagram is opened using Visio Services.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="1888b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="1888b-123">Child elements</span></span>

<span data-ttu-id="1888b-124">无。</span><span class="sxs-lookup"><span data-stu-id="1888b-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1888b-125">属性</span><span class="sxs-lookup"><span data-stu-id="1888b-125">Attributes</span></span>

|<span data-ttu-id="1888b-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="1888b-126">**Attribute**</span></span>|<span data-ttu-id="1888b-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="1888b-127">**Type**</span></span>|<span data-ttu-id="1888b-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="1888b-128">**Required**</span></span>|<span data-ttu-id="1888b-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="1888b-129">**Description**</span></span>|<span data-ttu-id="1888b-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1888b-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1888b-131">ID</span><span class="sxs-lookup"><span data-stu-id="1888b-131">ID</span></span>  <br/> |<span data-ttu-id="1888b-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1888b-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1888b-133">必需</span><span class="sxs-lookup"><span data-stu-id="1888b-133">required</span></span>  <br/> |<span data-ttu-id="1888b-134">Recordset 的标识符。</span><span class="sxs-lookup"><span data-stu-id="1888b-134">The identifier of a recordset.</span></span>  <br/> |<span data-ttu-id="1888b-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1888b-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

