---
title: 天气元素 （weatherdata 元素） （Outlook 天气位置架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1127956a-37aa-c39e-60b4-343dcc4ead82
description: 指定报告天气位置上。
ms.openlocfilehash: a95e207845a9e54f5cac58b64ce85ec17b59fa22
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779418"
---
# <a name="weather-element-weatherdata-element-outlook-weather-location-schema"></a><span data-ttu-id="cf4d1-103">天气元素 （weatherdata 元素） （Outlook 天气位置架构）</span><span class="sxs-lookup"><span data-stu-id="cf4d1-103">weather element (weatherdata element) (Outlook Weather Location Schema)</span></span>

<span data-ttu-id="cf4d1-104">指定报告天气位置上。</span><span class="sxs-lookup"><span data-stu-id="cf4d1-104">Specifies the location to report weather on.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="cf4d1-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="cf4d1-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="cf4d1-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-106">**Element type**</span></span> <br/> |[<span data-ttu-id="cf4d1-107">weatherType</span><span class="sxs-lookup"><span data-stu-id="cf4d1-107">weatherType</span></span>](weathertype-complextype-outlook-weather-location-schema.md) <br/> |
|<span data-ttu-id="cf4d1-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|<span data-ttu-id="cf4d1-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-109">**Schema file**</span></span> <br/> |<span data-ttu-id="cf4d1-110">getweatherlocation.xsd</span><span class="sxs-lookup"><span data-stu-id="cf4d1-110">getweatherlocation.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="cf4d1-111">定义</span><span class="sxs-lookup"><span data-stu-id="cf4d1-111">Definition</span></span>

```XML
<xs:element name="weather"      type="weatherType" maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="cf4d1-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="cf4d1-112">Elements and attributes</span></span>

<span data-ttu-id="cf4d1-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="cf4d1-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="cf4d1-114">父元素</span><span class="sxs-lookup"><span data-stu-id="cf4d1-114">Parent elements</span></span>

|<span data-ttu-id="cf4d1-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-115">**Element**</span></span>|<span data-ttu-id="cf4d1-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-116">**Type**</span></span>|<span data-ttu-id="cf4d1-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="cf4d1-118">weatherdata</span><span class="sxs-lookup"><span data-stu-id="cf4d1-118">weatherdata</span></span>](weatherdata-element-outlook-weather-location-schema.md) <br/> ||<span data-ttu-id="cf4d1-119">定义的天气元素。</span><span class="sxs-lookup"><span data-stu-id="cf4d1-119">Defines the weather element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="cf4d1-120">子元素</span><span class="sxs-lookup"><span data-stu-id="cf4d1-120">Child elements</span></span>

<span data-ttu-id="cf4d1-121">无。</span><span class="sxs-lookup"><span data-stu-id="cf4d1-121">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="cf4d1-122">属性</span><span class="sxs-lookup"><span data-stu-id="cf4d1-122">Attributes</span></span>

|<span data-ttu-id="cf4d1-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-123">**Attribute**</span></span>|<span data-ttu-id="cf4d1-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-124">**Type**</span></span>|<span data-ttu-id="cf4d1-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-125">**Required**</span></span>|<span data-ttu-id="cf4d1-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-126">**Description**</span></span>|<span data-ttu-id="cf4d1-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="cf4d1-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf4d1-128">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="cf4d1-128">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="cf4d1-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="cf4d1-129">xs:string</span></span>  <br/> |<span data-ttu-id="cf4d1-130">必需</span><span class="sxs-lookup"><span data-stu-id="cf4d1-130">required</span></span>  <br/> |<span data-ttu-id="cf4d1-131">指定与要区分具有相同名称的多个位置的位置相关联的代码。</span><span class="sxs-lookup"><span data-stu-id="cf4d1-131">Specifies a code that is associated with the location to distinguish multiple locations with the same name.</span></span>  <br/> |<span data-ttu-id="cf4d1-132">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="cf4d1-132">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="cf4d1-133">weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="cf4d1-133">weatherlocationname</span></span>  <br/> |<span data-ttu-id="cf4d1-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="cf4d1-134">xs:string</span></span>  <br/> |<span data-ttu-id="cf4d1-135">必需</span><span class="sxs-lookup"><span data-stu-id="cf4d1-135">required</span></span>  <br/> |<span data-ttu-id="cf4d1-136">指定的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="cf4d1-136">Specifies the name of the location.</span></span>  <br/> |<span data-ttu-id="cf4d1-137">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="cf4d1-137">A value of the type xs:string</span></span>  <br/> |
   

