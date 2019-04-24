---
title: 气象元素 (weatherdata 元素) (Outlook 天气位置架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1127956a-37aa-c39e-60b4-343dcc4ead82
description: 指定要在其上报告天气的位置。
ms.openlocfilehash: f6642b3f477b9fe45ed0e6a43efcd40e21559b7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355207"
---
# <a name="weather-element-weatherdata-element-outlook-weather-location-schema"></a><span data-ttu-id="6b21d-103">气象元素 (weatherdata 元素) (Outlook 天气位置架构)</span><span class="sxs-lookup"><span data-stu-id="6b21d-103">weather element (weatherdata element) (Outlook Weather Location Schema)</span></span>

<span data-ttu-id="6b21d-104">指定要在其上报告天气的位置。</span><span class="sxs-lookup"><span data-stu-id="6b21d-104">Specifies the location to report weather on.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="6b21d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="6b21d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6b21d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="6b21d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="6b21d-107">weatherType</span><span class="sxs-lookup"><span data-stu-id="6b21d-107">weatherType</span></span>](weathertype-complextype-outlook-weather-location-schema.md) <br/> |
|<span data-ttu-id="6b21d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6b21d-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|<span data-ttu-id="6b21d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6b21d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="6b21d-110">getweatherlocation</span><span class="sxs-lookup"><span data-stu-id="6b21d-110">getweatherlocation.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6b21d-111">定义</span><span class="sxs-lookup"><span data-stu-id="6b21d-111">Definition</span></span>

```XML
<xs:element name="weather"      type="weatherType" maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="6b21d-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6b21d-112">Elements and attributes</span></span>

<span data-ttu-id="6b21d-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="6b21d-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="6b21d-114">父元素</span><span class="sxs-lookup"><span data-stu-id="6b21d-114">Parent elements</span></span>

|<span data-ttu-id="6b21d-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="6b21d-115">**Element**</span></span>|<span data-ttu-id="6b21d-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="6b21d-116">**Type**</span></span>|<span data-ttu-id="6b21d-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b21d-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6b21d-118">weatherdata</span><span class="sxs-lookup"><span data-stu-id="6b21d-118">weatherdata</span></span>](weatherdata-element-outlook-weather-location-schema.md) <br/> ||<span data-ttu-id="6b21d-119">定义气象元素。</span><span class="sxs-lookup"><span data-stu-id="6b21d-119">Defines the weather element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="6b21d-120">子元素</span><span class="sxs-lookup"><span data-stu-id="6b21d-120">Child elements</span></span>

<span data-ttu-id="6b21d-121">无。</span><span class="sxs-lookup"><span data-stu-id="6b21d-121">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6b21d-122">属性</span><span class="sxs-lookup"><span data-stu-id="6b21d-122">Attributes</span></span>

|<span data-ttu-id="6b21d-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="6b21d-123">**Attribute**</span></span>|<span data-ttu-id="6b21d-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="6b21d-124">**Type**</span></span>|<span data-ttu-id="6b21d-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="6b21d-125">**Required**</span></span>|<span data-ttu-id="6b21d-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="6b21d-126">**Description**</span></span>|<span data-ttu-id="6b21d-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6b21d-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b21d-128">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="6b21d-128">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="6b21d-129">xs: string</span><span class="sxs-lookup"><span data-stu-id="6b21d-129">xs:string</span></span>  <br/> |<span data-ttu-id="6b21d-130">必需</span><span class="sxs-lookup"><span data-stu-id="6b21d-130">required</span></span>  <br/> |<span data-ttu-id="6b21d-131">指定与位置相关联的代码, 以区分具有相同名称的多个位置。</span><span class="sxs-lookup"><span data-stu-id="6b21d-131">Specifies a code that is associated with the location to distinguish multiple locations with the same name.</span></span>  <br/> |<span data-ttu-id="6b21d-132">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="6b21d-132">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="6b21d-133">表示 weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="6b21d-133">weatherlocationname</span></span>  <br/> |<span data-ttu-id="6b21d-134">xs: string</span><span class="sxs-lookup"><span data-stu-id="6b21d-134">xs:string</span></span>  <br/> |<span data-ttu-id="6b21d-135">必需</span><span class="sxs-lookup"><span data-stu-id="6b21d-135">required</span></span>  <br/> |<span data-ttu-id="6b21d-136">指定位置的名称。</span><span class="sxs-lookup"><span data-stu-id="6b21d-136">Specifies the name of the location.</span></span>  <br/> |<span data-ttu-id="6b21d-137">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="6b21d-137">A value of the type xs:string</span></span>  <br/> |
   

