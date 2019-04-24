---
title: 气象元素 (weatherdata 元素) (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de3c35ef-84a3-b991-7c98-3eca720c9ba0
description: 指定位置的天气情况。
ms.openlocfilehash: 19e6669d51aa38d10587c6334aef0409f31baf58
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355144"
---
# <a name="weather-element-weatherdata-element-outlook-weather-information-schema"></a><span data-ttu-id="2c788-103">气象元素 (weatherdata 元素) (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="2c788-103">weather element (weatherdata element) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="2c788-104">指定位置的天气情况。</span><span class="sxs-lookup"><span data-stu-id="2c788-104">Specifies the weather conditions of a location.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2c788-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="2c788-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2c788-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2c788-106">**Element type**</span></span> <br/> |[<span data-ttu-id="2c788-107">weatherType</span><span class="sxs-lookup"><span data-stu-id="2c788-107">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="2c788-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2c788-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="2c788-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2c788-109">**Schema file**</span></span> <br/> |<span data-ttu-id="2c788-110">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="2c788-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2c788-111">定义</span><span class="sxs-lookup"><span data-stu-id="2c788-111">Definition</span></span>

```XML
<xs:element name="weather"      type="weatherType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="2c788-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2c788-112">Elements and attributes</span></span>

<span data-ttu-id="2c788-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="2c788-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="2c788-114">父元素</span><span class="sxs-lookup"><span data-stu-id="2c788-114">Parent elements</span></span>

|<span data-ttu-id="2c788-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="2c788-115">**Element**</span></span>|<span data-ttu-id="2c788-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="2c788-116">**Type**</span></span>|<span data-ttu-id="2c788-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c788-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2c788-118">weatherdata</span><span class="sxs-lookup"><span data-stu-id="2c788-118">weatherdata</span></span>](weatherdata-element-outlook-weather-information-schema.md) <br/> ||<span data-ttu-id="2c788-119">定义气象元素。</span><span class="sxs-lookup"><span data-stu-id="2c788-119">Defines the weather element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="2c788-120">子元素</span><span class="sxs-lookup"><span data-stu-id="2c788-120">Child elements</span></span>

|<span data-ttu-id="2c788-121">**元素**</span><span class="sxs-lookup"><span data-stu-id="2c788-121">**Element**</span></span>|<span data-ttu-id="2c788-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="2c788-122">**Type**</span></span>|<span data-ttu-id="2c788-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c788-123">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2c788-124">目前</span><span class="sxs-lookup"><span data-stu-id="2c788-124">current</span></span>](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="2c788-125">currentType</span><span class="sxs-lookup"><span data-stu-id="2c788-125">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="2c788-126">指定当前天气情况。</span><span class="sxs-lookup"><span data-stu-id="2c788-126">Specifies the current weather conditions.</span></span>  <br/> |
|[<span data-ttu-id="2c788-127">预测</span><span class="sxs-lookup"><span data-stu-id="2c788-127">forecast</span></span>](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="2c788-128">forecastType</span><span class="sxs-lookup"><span data-stu-id="2c788-128">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="2c788-129">指定至少三天前的后续天气条件, 包括今天: 今天、明天、一天后。</span><span class="sxs-lookup"><span data-stu-id="2c788-129">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="2c788-130">属性</span><span class="sxs-lookup"><span data-stu-id="2c788-130">Attributes</span></span>

|<span data-ttu-id="2c788-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="2c788-131">**Attribute**</span></span>|<span data-ttu-id="2c788-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="2c788-132">**Type**</span></span>|<span data-ttu-id="2c788-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="2c788-133">**Required**</span></span>|<span data-ttu-id="2c788-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="2c788-134">**Description**</span></span>|<span data-ttu-id="2c788-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2c788-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c788-136">attribution</span><span class="sxs-lookup"><span data-stu-id="2c788-136">attribution</span></span>  <br/> |<span data-ttu-id="2c788-137">xs: string</span><span class="sxs-lookup"><span data-stu-id="2c788-137">xs:string</span></span>  <br/> |<span data-ttu-id="2c788-138">必需</span><span class="sxs-lookup"><span data-stu-id="2c788-138">required</span></span>  <br/> |<span data-ttu-id="2c788-139">指定天气信息的来源。</span><span class="sxs-lookup"><span data-stu-id="2c788-139">Specifies the source of the weather information.</span></span>  <br/> |<span data-ttu-id="2c788-140">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="2c788-140">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c788-141">degreetype</span><span class="sxs-lookup"><span data-stu-id="2c788-141">degreetype</span></span>  <br/> |<span data-ttu-id="2c788-142">xs: string</span><span class="sxs-lookup"><span data-stu-id="2c788-142">xs:string</span></span>  <br/> |<span data-ttu-id="2c788-143">必需</span><span class="sxs-lookup"><span data-stu-id="2c788-143">required</span></span>  <br/> |<span data-ttu-id="2c788-144">指定位置温度的单位 (例如, 摄氏温度)。</span><span class="sxs-lookup"><span data-stu-id="2c788-144">Specifies the unit for the temperature of the location for example, Celsius.</span></span>  <br/> |<span data-ttu-id="2c788-145">C、F</span><span class="sxs-lookup"><span data-stu-id="2c788-145">C, F</span></span>  <br/> |
|<span data-ttu-id="2c788-146">imagerelativeurl</span><span class="sxs-lookup"><span data-stu-id="2c788-146">imagerelativeurl</span></span>  <br/> |<span data-ttu-id="2c788-147">xs: string</span><span class="sxs-lookup"><span data-stu-id="2c788-147">xs:string</span></span>  <br/> |<span data-ttu-id="2c788-148">必需</span><span class="sxs-lookup"><span data-stu-id="2c788-148">required</span></span>  <br/> |<span data-ttu-id="2c788-149">指定位置的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="2c788-149">Specifies the URL of the image for the location.</span></span>  <br/> |<span data-ttu-id="2c788-150">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="2c788-150">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c788-151">时区</span><span class="sxs-lookup"><span data-stu-id="2c788-151">timezone</span></span>  <br/> |<span data-ttu-id="2c788-152">xs: integer</span><span class="sxs-lookup"><span data-stu-id="2c788-152">xs:integer</span></span>  <br/> |<span data-ttu-id="2c788-153">必需</span><span class="sxs-lookup"><span data-stu-id="2c788-153">required</span></span>  <br/> |<span data-ttu-id="2c788-154">指定 GMT 偏移量。</span><span class="sxs-lookup"><span data-stu-id="2c788-154">Specifies the GMT offset.</span></span>  <br/> |<span data-ttu-id="2c788-155">介于-11 和12之间的值 (含)</span><span class="sxs-lookup"><span data-stu-id="2c788-155">A value between -11 and 12 inclusive</span></span>  <br/> |
|<span data-ttu-id="2c788-156">url</span><span class="sxs-lookup"><span data-stu-id="2c788-156">url</span></span>  <br/> |<span data-ttu-id="2c788-157">xs: string</span><span class="sxs-lookup"><span data-stu-id="2c788-157">xs:string</span></span>  <br/> |<span data-ttu-id="2c788-158">必需</span><span class="sxs-lookup"><span data-stu-id="2c788-158">required</span></span>  <br/> |<span data-ttu-id="2c788-159">指定包含指定位置的天气信息的天气服务网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="2c788-159">Specifies the URL for the web page of the weather service that contains weather information for the specified location.</span></span>  <br/> |<span data-ttu-id="2c788-160">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="2c788-160">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c788-161">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="2c788-161">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="2c788-162">xs: string</span><span class="sxs-lookup"><span data-stu-id="2c788-162">xs:string</span></span>  <br/> |<span data-ttu-id="2c788-163">必需</span><span class="sxs-lookup"><span data-stu-id="2c788-163">required</span></span>  <br/> |<span data-ttu-id="2c788-164">指定与用于区分具有相同名称的多个位置的位置相关联的代码。</span><span class="sxs-lookup"><span data-stu-id="2c788-164">Specifies the code that is associated with the location used to distinguish multiple location that have the same name.</span></span>  <br/> |<span data-ttu-id="2c788-165">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="2c788-165">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c788-166">表示 weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="2c788-166">weatherlocationname</span></span>  <br/> |<span data-ttu-id="2c788-167">xs: string</span><span class="sxs-lookup"><span data-stu-id="2c788-167">xs:string</span></span>  <br/> |<span data-ttu-id="2c788-168">必需</span><span class="sxs-lookup"><span data-stu-id="2c788-168">required</span></span>  <br/> |<span data-ttu-id="2c788-169">指定在下拉控件中显示的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="2c788-169">Specifies the name of the location that appears in the drop-down control.</span></span>  <br/> |<span data-ttu-id="2c788-170">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="2c788-170">A value of the type xs:string</span></span>  <br/> |
   

