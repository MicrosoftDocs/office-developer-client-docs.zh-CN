---
title: 'weather 元素 (weatherdata 元素)  (Outlook Weather Location Schema) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1127956a-37aa-c39e-60b4-343dcc4ead82
description: 指定要报告天气的位置。
ms.openlocfilehash: a907fb9df02d88d317a73e409ea8738273eb2cb1
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539010"
---
# <a name="weather-element-weatherdata-element-outlook-weather-location-schema"></a><span data-ttu-id="1bb45-103">weather 元素 (weatherdata 元素)  (Outlook Weather Location Schema) </span><span class="sxs-lookup"><span data-stu-id="1bb45-103">weather element (weatherdata element) (Outlook Weather Location Schema)</span></span>

<span data-ttu-id="1bb45-104">指定要报告天气的位置。</span><span class="sxs-lookup"><span data-stu-id="1bb45-104">Specifies the location to report weather on.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="1bb45-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="1bb45-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1bb45-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="1bb45-106">**Element type**</span></span> <br/> |[<span data-ttu-id="1bb45-107">weatherType</span><span class="sxs-lookup"><span data-stu-id="1bb45-107">weatherType</span></span>](weathertype-complextype-outlook-weather-location-schema.md) <br/> |
|<span data-ttu-id="1bb45-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1bb45-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|<span data-ttu-id="1bb45-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1bb45-109">**Schema file**</span></span> <br/> |<span data-ttu-id="1bb45-110">getweatherlocation.xsd</span><span class="sxs-lookup"><span data-stu-id="1bb45-110">getweatherlocation.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1bb45-111">定义</span><span class="sxs-lookup"><span data-stu-id="1bb45-111">Definition</span></span>

```XML
<xs:element name="weather"      type="weatherType" maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="1bb45-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1bb45-112">Elements and attributes</span></span>

<span data-ttu-id="1bb45-113">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1bb45-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="1bb45-114">父元素</span><span class="sxs-lookup"><span data-stu-id="1bb45-114">Parent elements</span></span>

|<span data-ttu-id="1bb45-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="1bb45-115">**Element**</span></span>|<span data-ttu-id="1bb45-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="1bb45-116">**Type**</span></span>|<span data-ttu-id="1bb45-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="1bb45-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1bb45-118">weatherdata</span><span class="sxs-lookup"><span data-stu-id="1bb45-118">weatherdata</span></span>](weatherdata-element-outlook-weather-location-schema.md) <br/> ||<span data-ttu-id="1bb45-119">定义 weather 元素。</span><span class="sxs-lookup"><span data-stu-id="1bb45-119">Defines the weather element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="1bb45-120">子元素</span><span class="sxs-lookup"><span data-stu-id="1bb45-120">Child elements</span></span>

<span data-ttu-id="1bb45-121">无。</span><span class="sxs-lookup"><span data-stu-id="1bb45-121">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1bb45-122">属性</span><span class="sxs-lookup"><span data-stu-id="1bb45-122">Attributes</span></span>

|<span data-ttu-id="1bb45-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="1bb45-123">**Attribute**</span></span>|<span data-ttu-id="1bb45-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="1bb45-124">**Type**</span></span>|<span data-ttu-id="1bb45-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="1bb45-125">**Required**</span></span>|<span data-ttu-id="1bb45-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="1bb45-126">**Description**</span></span>|<span data-ttu-id="1bb45-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1bb45-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1bb45-128">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="1bb45-128">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="1bb45-129">xs：string</span><span class="sxs-lookup"><span data-stu-id="1bb45-129">xs:string</span></span>  <br/> |<span data-ttu-id="1bb45-130">必需</span><span class="sxs-lookup"><span data-stu-id="1bb45-130">required</span></span>  <br/> |<span data-ttu-id="1bb45-131">指定与位置相关联的代码，以使用相同的名称区分多个位置。</span><span class="sxs-lookup"><span data-stu-id="1bb45-131">Specifies a code that is associated with the location to distinguish multiple locations with the same name.</span></span>  <br/> |<span data-ttu-id="1bb45-132">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="1bb45-132">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="1bb45-133">weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="1bb45-133">weatherlocationname</span></span>  <br/> |<span data-ttu-id="1bb45-134">xs：string</span><span class="sxs-lookup"><span data-stu-id="1bb45-134">xs:string</span></span>  <br/> |<span data-ttu-id="1bb45-135">必需</span><span class="sxs-lookup"><span data-stu-id="1bb45-135">required</span></span>  <br/> |<span data-ttu-id="1bb45-136">指定位置的名称。</span><span class="sxs-lookup"><span data-stu-id="1bb45-136">Specifies the name of the location.</span></span>  <br/> |<span data-ttu-id="1bb45-137">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="1bb45-137">A value of the type xs:string</span></span>  <br/> |
   

