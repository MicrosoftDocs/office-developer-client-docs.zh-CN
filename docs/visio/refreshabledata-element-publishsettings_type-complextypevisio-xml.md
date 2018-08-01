---
title: RefreshableData 元素 （PublishSettings_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9a3b9d5a-fcba-eb18-3199-bd5a7f889af8
description: 指定记录集是否可刷新使用 Microsoft SharePoint Server 2013 中的 Visio Services。
ms.openlocfilehash: 47da60fb95b49084b70cfc630430879f04463553
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781028"
---
# <a name="refreshabledata-element-publishsettingstype-complextype-visio-xml"></a><span data-ttu-id="d718a-103">RefreshableData 元素 （PublishSettings_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d718a-103">RefreshableData element (PublishSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="d718a-104">指定记录集是否可刷新使用 Microsoft SharePoint Server 2013 中的 Visio Services。</span><span class="sxs-lookup"><span data-stu-id="d718a-104">Specifies whether a recordset is refreshable using Visio Services in Microsoft SharePoint Server 2013.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d718a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d718a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d718a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d718a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d718a-107">RefreshableData_Type</span><span class="sxs-lookup"><span data-stu-id="d718a-107">RefreshableData_Type</span></span>](refreshabledata_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d718a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d718a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d718a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d718a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d718a-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d718a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d718a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d718a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d718a-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="d718a-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d718a-113">定义</span><span class="sxs-lookup"><span data-stu-id="d718a-113">Definition</span></span>

```XML
<xs:element name="RefreshableData" type="RefreshableData_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >

```

## <a name="elements-and-attributes"></a><span data-ttu-id="d718a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d718a-114">Elements and attributes</span></span>

<span data-ttu-id="d718a-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d718a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d718a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d718a-116">Parent elements</span></span>

|<span data-ttu-id="d718a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d718a-117">**Element**</span></span>|<span data-ttu-id="d718a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d718a-118">**Type**</span></span>|<span data-ttu-id="d718a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d718a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d718a-120">PublishSettings</span><span class="sxs-lookup"><span data-stu-id="d718a-120">PublishSettings</span></span>](publishsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d718a-121">PublishSettings_Type</span><span class="sxs-lookup"><span data-stu-id="d718a-121">PublishSettings_Type</span></span>](publishsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d718a-122">指定使用 Visio Services 打开图表时使用的设置。</span><span class="sxs-lookup"><span data-stu-id="d718a-122">Specifies the settings that are used when the diagram is opened using Visio Services.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d718a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d718a-123">Child elements</span></span>

<span data-ttu-id="d718a-124">无。</span><span class="sxs-lookup"><span data-stu-id="d718a-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d718a-125">属性</span><span class="sxs-lookup"><span data-stu-id="d718a-125">Attributes</span></span>

|<span data-ttu-id="d718a-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="d718a-126">**Attribute**</span></span>|<span data-ttu-id="d718a-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="d718a-127">**Type**</span></span>|<span data-ttu-id="d718a-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="d718a-128">**Required**</span></span>|<span data-ttu-id="d718a-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="d718a-129">**Description**</span></span>|<span data-ttu-id="d718a-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d718a-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d718a-131">ID</span><span class="sxs-lookup"><span data-stu-id="d718a-131">ID</span></span>  <br/> |<span data-ttu-id="d718a-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d718a-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d718a-133">必需</span><span class="sxs-lookup"><span data-stu-id="d718a-133">required</span></span>  <br/> |<span data-ttu-id="d718a-134">记录集的标识符。</span><span class="sxs-lookup"><span data-stu-id="d718a-134">The identifier of a recordset.</span></span>  <br/> |<span data-ttu-id="d718a-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d718a-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

