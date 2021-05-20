---
title: 'weather 元素 (weatherdata 元素)  (Outlook Weather Information Schema) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de3c35ef-84a3-b991-7c98-3eca720c9ba0
description: 指定位置的天气状况。
ms.openlocfilehash: 18669dfc4636c28e03a582bc0c8df512aa38a4e4
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541265"
---
# <a name="weather-element-weatherdata-element-outlook-weather-information-schema"></a><span data-ttu-id="76d8f-103">weather 元素 (weatherdata 元素)  (Outlook Weather Information Schema) </span><span class="sxs-lookup"><span data-stu-id="76d8f-103">weather element (weatherdata element) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="76d8f-104">指定位置的天气状况。</span><span class="sxs-lookup"><span data-stu-id="76d8f-104">Specifies the weather conditions of a location.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="76d8f-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="76d8f-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="76d8f-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="76d8f-106">**Element type**</span></span> <br/> |[<span data-ttu-id="76d8f-107">weatherType</span><span class="sxs-lookup"><span data-stu-id="76d8f-107">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="76d8f-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="76d8f-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="76d8f-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="76d8f-109">**Schema file**</span></span> <br/> |<span data-ttu-id="76d8f-110">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="76d8f-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="76d8f-111">定义</span><span class="sxs-lookup"><span data-stu-id="76d8f-111">Definition</span></span>

```XML
<xs:element name="weather"      type="weatherType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="76d8f-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="76d8f-112">Elements and attributes</span></span>

<span data-ttu-id="76d8f-113">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="76d8f-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="76d8f-114">父元素</span><span class="sxs-lookup"><span data-stu-id="76d8f-114">Parent elements</span></span>

|<span data-ttu-id="76d8f-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="76d8f-115">**Element**</span></span>|<span data-ttu-id="76d8f-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="76d8f-116">**Type**</span></span>|<span data-ttu-id="76d8f-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="76d8f-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="76d8f-118">weatherdata</span><span class="sxs-lookup"><span data-stu-id="76d8f-118">weatherdata</span></span>](weatherdata-element-outlook-weather-information-schema.md) <br/> ||<span data-ttu-id="76d8f-119">定义 weather 元素。</span><span class="sxs-lookup"><span data-stu-id="76d8f-119">Defines the weather element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="76d8f-120">子元素</span><span class="sxs-lookup"><span data-stu-id="76d8f-120">Child elements</span></span>

|<span data-ttu-id="76d8f-121">**元素**</span><span class="sxs-lookup"><span data-stu-id="76d8f-121">**Element**</span></span>|<span data-ttu-id="76d8f-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="76d8f-122">**Type**</span></span>|<span data-ttu-id="76d8f-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="76d8f-123">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="76d8f-124">current</span><span class="sxs-lookup"><span data-stu-id="76d8f-124">current</span></span>](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="76d8f-125">currentType</span><span class="sxs-lookup"><span data-stu-id="76d8f-125">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="76d8f-126">指定当前天气状况。</span><span class="sxs-lookup"><span data-stu-id="76d8f-126">Specifies the current weather conditions.</span></span>  <br/> |
|[<span data-ttu-id="76d8f-127">forecast</span><span class="sxs-lookup"><span data-stu-id="76d8f-127">forecast</span></span>](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="76d8f-128">forecastType</span><span class="sxs-lookup"><span data-stu-id="76d8f-128">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="76d8f-129">指定至少提前三天的未来天气条件，包括今天、明天、明天后一天。</span><span class="sxs-lookup"><span data-stu-id="76d8f-129">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="76d8f-130">属性</span><span class="sxs-lookup"><span data-stu-id="76d8f-130">Attributes</span></span>

|<span data-ttu-id="76d8f-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="76d8f-131">**Attribute**</span></span>|<span data-ttu-id="76d8f-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="76d8f-132">**Type**</span></span>|<span data-ttu-id="76d8f-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="76d8f-133">**Required**</span></span>|<span data-ttu-id="76d8f-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="76d8f-134">**Description**</span></span>|<span data-ttu-id="76d8f-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="76d8f-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76d8f-136">attribution</span><span class="sxs-lookup"><span data-stu-id="76d8f-136">attribution</span></span>  <br/> |<span data-ttu-id="76d8f-137">xs：string</span><span class="sxs-lookup"><span data-stu-id="76d8f-137">xs:string</span></span>  <br/> |<span data-ttu-id="76d8f-138">必需</span><span class="sxs-lookup"><span data-stu-id="76d8f-138">required</span></span>  <br/> |<span data-ttu-id="76d8f-139">指定天气信息的来源。</span><span class="sxs-lookup"><span data-stu-id="76d8f-139">Specifies the source of the weather information.</span></span>  <br/> |<span data-ttu-id="76d8f-140">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="76d8f-140">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="76d8f-141">degreetype</span><span class="sxs-lookup"><span data-stu-id="76d8f-141">degreetype</span></span>  <br/> |<span data-ttu-id="76d8f-142">xs：string</span><span class="sxs-lookup"><span data-stu-id="76d8f-142">xs:string</span></span>  <br/> |<span data-ttu-id="76d8f-143">必需</span><span class="sxs-lookup"><span data-stu-id="76d8f-143">required</span></span>  <br/> |<span data-ttu-id="76d8f-144">指定位置温度的单位，例如，摄氏度。</span><span class="sxs-lookup"><span data-stu-id="76d8f-144">Specifies the unit for the temperature of the location for example, Celsius.</span></span>  <br/> |<span data-ttu-id="76d8f-145">C、F</span><span class="sxs-lookup"><span data-stu-id="76d8f-145">C, F</span></span>  <br/> |
|<span data-ttu-id="76d8f-146">imagerelativeurl</span><span class="sxs-lookup"><span data-stu-id="76d8f-146">imagerelativeurl</span></span>  <br/> |<span data-ttu-id="76d8f-147">xs：string</span><span class="sxs-lookup"><span data-stu-id="76d8f-147">xs:string</span></span>  <br/> |<span data-ttu-id="76d8f-148">必需</span><span class="sxs-lookup"><span data-stu-id="76d8f-148">required</span></span>  <br/> |<span data-ttu-id="76d8f-149">指定位置的图像 URL。</span><span class="sxs-lookup"><span data-stu-id="76d8f-149">Specifies the URL of the image for the location.</span></span>  <br/> |<span data-ttu-id="76d8f-150">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="76d8f-150">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="76d8f-151">timezone</span><span class="sxs-lookup"><span data-stu-id="76d8f-151">timezone</span></span>  <br/> |<span data-ttu-id="76d8f-152">xs：integer</span><span class="sxs-lookup"><span data-stu-id="76d8f-152">xs:integer</span></span>  <br/> |<span data-ttu-id="76d8f-153">必需</span><span class="sxs-lookup"><span data-stu-id="76d8f-153">required</span></span>  <br/> |<span data-ttu-id="76d8f-154">指定 GMT 偏移量。</span><span class="sxs-lookup"><span data-stu-id="76d8f-154">Specifies the GMT offset.</span></span>  <br/> |<span data-ttu-id="76d8f-155">介于 -11 和 12（含这两个值）之间的值</span><span class="sxs-lookup"><span data-stu-id="76d8f-155">A value between -11 and 12 inclusive</span></span>  <br/> |
|<span data-ttu-id="76d8f-156">url</span><span class="sxs-lookup"><span data-stu-id="76d8f-156">url</span></span>  <br/> |<span data-ttu-id="76d8f-157">xs：string</span><span class="sxs-lookup"><span data-stu-id="76d8f-157">xs:string</span></span>  <br/> |<span data-ttu-id="76d8f-158">必需</span><span class="sxs-lookup"><span data-stu-id="76d8f-158">required</span></span>  <br/> |<span data-ttu-id="76d8f-159">指定包含指定位置的天气信息的天气服务网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="76d8f-159">Specifies the URL for the web page of the weather service that contains weather information for the specified location.</span></span>  <br/> |<span data-ttu-id="76d8f-160">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="76d8f-160">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="76d8f-161">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="76d8f-161">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="76d8f-162">xs：string</span><span class="sxs-lookup"><span data-stu-id="76d8f-162">xs:string</span></span>  <br/> |<span data-ttu-id="76d8f-163">必需</span><span class="sxs-lookup"><span data-stu-id="76d8f-163">required</span></span>  <br/> |<span data-ttu-id="76d8f-164">指定与用于区分多个同名位置的位置关联的代码。</span><span class="sxs-lookup"><span data-stu-id="76d8f-164">Specifies the code that is associated with the location used to distinguish multiple location that have the same name.</span></span>  <br/> |<span data-ttu-id="76d8f-165">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="76d8f-165">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="76d8f-166">weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="76d8f-166">weatherlocationname</span></span>  <br/> |<span data-ttu-id="76d8f-167">xs：string</span><span class="sxs-lookup"><span data-stu-id="76d8f-167">xs:string</span></span>  <br/> |<span data-ttu-id="76d8f-168">必需</span><span class="sxs-lookup"><span data-stu-id="76d8f-168">required</span></span>  <br/> |<span data-ttu-id="76d8f-169">指定下拉列表控件中显示的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="76d8f-169">Specifies the name of the location that appears in the drop-down control.</span></span>  <br/> |<span data-ttu-id="76d8f-170">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="76d8f-170">A value of the type xs:string</span></span>  <br/> |
   

