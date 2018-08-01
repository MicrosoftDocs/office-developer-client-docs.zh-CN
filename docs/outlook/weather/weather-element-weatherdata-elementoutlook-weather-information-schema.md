---
title: 天气元素 （weatherdata 元素） （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de3c35ef-84a3-b991-7c98-3eca720c9ba0
description: 指定一个位置的天气条件。
ms.openlocfilehash: c19db6657860dd35f90832aef0614f4fb88d87b4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779415"
---
# <a name="weather-element-weatherdata-element-outlook-weather-information-schema"></a><span data-ttu-id="35962-103">天气元素 （weatherdata 元素） （Outlook 天气信息架构）</span><span class="sxs-lookup"><span data-stu-id="35962-103">weather element (weatherdata element) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="35962-104">指定一个位置的天气条件。</span><span class="sxs-lookup"><span data-stu-id="35962-104">Specifies the weather conditions of a location.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="35962-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="35962-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="35962-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="35962-106">**Element type**</span></span> <br/> |[<span data-ttu-id="35962-107">weatherType</span><span class="sxs-lookup"><span data-stu-id="35962-107">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="35962-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="35962-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="35962-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="35962-109">**Schema file**</span></span> <br/> |<span data-ttu-id="35962-110">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="35962-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="35962-111">定义</span><span class="sxs-lookup"><span data-stu-id="35962-111">Definition</span></span>

```XML
<xs:element name="weather"      type="weatherType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="35962-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="35962-112">Elements and attributes</span></span>

<span data-ttu-id="35962-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="35962-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="35962-114">父元素</span><span class="sxs-lookup"><span data-stu-id="35962-114">Parent elements</span></span>

|<span data-ttu-id="35962-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="35962-115">**Element**</span></span>|<span data-ttu-id="35962-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="35962-116">**Type**</span></span>|<span data-ttu-id="35962-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="35962-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="35962-118">weatherdata</span><span class="sxs-lookup"><span data-stu-id="35962-118">weatherdata</span></span>](weatherdata-element-outlook-weather-information-schema.md) <br/> ||<span data-ttu-id="35962-119">定义的天气元素。</span><span class="sxs-lookup"><span data-stu-id="35962-119">Defines the weather element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="35962-120">子元素</span><span class="sxs-lookup"><span data-stu-id="35962-120">Child elements</span></span>

|<span data-ttu-id="35962-121">**元素**</span><span class="sxs-lookup"><span data-stu-id="35962-121">**Element**</span></span>|<span data-ttu-id="35962-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="35962-122">**Type**</span></span>|<span data-ttu-id="35962-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="35962-123">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="35962-124">当前</span><span class="sxs-lookup"><span data-stu-id="35962-124">current</span></span>](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="35962-125">currentType</span><span class="sxs-lookup"><span data-stu-id="35962-125">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="35962-126">指定当前的天气条件。</span><span class="sxs-lookup"><span data-stu-id="35962-126">Specifies the current weather conditions.</span></span>  <br/> |
|[<span data-ttu-id="35962-127">预测</span><span class="sxs-lookup"><span data-stu-id="35962-127">forecast</span></span>](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="35962-128">forecastType</span><span class="sxs-lookup"><span data-stu-id="35962-128">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="35962-129">指定至少三天提前包括今天的未来的天气条件： 今天，明天，天 after 明天。</span><span class="sxs-lookup"><span data-stu-id="35962-129">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="35962-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="35962-130">Attributes</span></span>

|<span data-ttu-id="35962-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="35962-131">**Attribute**</span></span>|<span data-ttu-id="35962-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="35962-132">**Type**</span></span>|<span data-ttu-id="35962-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="35962-133">**Required**</span></span>|<span data-ttu-id="35962-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="35962-134">**Description**</span></span>|<span data-ttu-id="35962-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="35962-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35962-136">属性</span><span class="sxs-lookup"><span data-stu-id="35962-136">attribution</span></span>  <br/> |<span data-ttu-id="35962-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="35962-137">xs:string</span></span>  <br/> |<span data-ttu-id="35962-138">必需</span><span class="sxs-lookup"><span data-stu-id="35962-138">required</span></span>  <br/> |<span data-ttu-id="35962-139">指定的天气信息的源。</span><span class="sxs-lookup"><span data-stu-id="35962-139">Specifies the source of the weather information.</span></span>  <br/> |<span data-ttu-id="35962-140">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="35962-140">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="35962-141">degreetype</span><span class="sxs-lookup"><span data-stu-id="35962-141">degreetype</span></span>  <br/> |<span data-ttu-id="35962-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="35962-142">xs:string</span></span>  <br/> |<span data-ttu-id="35962-143">必需</span><span class="sxs-lookup"><span data-stu-id="35962-143">required</span></span>  <br/> |<span data-ttu-id="35962-144">指定的位置，如摄氏度温度的单位。</span><span class="sxs-lookup"><span data-stu-id="35962-144">Specifies the unit for the temperature of the location for example, Celsius.</span></span>  <br/> |<span data-ttu-id="35962-145">C F</span><span class="sxs-lookup"><span data-stu-id="35962-145">C, F</span></span>  <br/> |
|<span data-ttu-id="35962-146">imagerelativeurl</span><span class="sxs-lookup"><span data-stu-id="35962-146">imagerelativeurl</span></span>  <br/> |<span data-ttu-id="35962-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="35962-147">xs:string</span></span>  <br/> |<span data-ttu-id="35962-148">必需</span><span class="sxs-lookup"><span data-stu-id="35962-148">required</span></span>  <br/> |<span data-ttu-id="35962-149">指定位置的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="35962-149">Specifies the URL of the image for the location.</span></span>  <br/> |<span data-ttu-id="35962-150">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="35962-150">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="35962-151">timezone</span><span class="sxs-lookup"><span data-stu-id="35962-151">timezone</span></span>  <br/> |<span data-ttu-id="35962-152">xs:integer</span><span class="sxs-lookup"><span data-stu-id="35962-152">xs:integer</span></span>  <br/> |<span data-ttu-id="35962-153">必需</span><span class="sxs-lookup"><span data-stu-id="35962-153">required</span></span>  <br/> |<span data-ttu-id="35962-154">指定格林威治标准时间偏移量。</span><span class="sxs-lookup"><span data-stu-id="35962-154">Specifies the GMT offset.</span></span>  <br/> |<span data-ttu-id="35962-155">-11 和 12 非独占之间的值</span><span class="sxs-lookup"><span data-stu-id="35962-155">A value between -11 and 12 inclusive</span></span>  <br/> |
|<span data-ttu-id="35962-156">url</span><span class="sxs-lookup"><span data-stu-id="35962-156">url</span></span>  <br/> |<span data-ttu-id="35962-157">xs:string</span><span class="sxs-lookup"><span data-stu-id="35962-157">xs:string</span></span>  <br/> |<span data-ttu-id="35962-158">必需</span><span class="sxs-lookup"><span data-stu-id="35962-158">required</span></span>  <br/> |<span data-ttu-id="35962-159">指定包含指定的位置的天气信息的天气服务网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="35962-159">Specifies the URL for the web page of the weather service that contains weather information for the specified location.</span></span>  <br/> |<span data-ttu-id="35962-160">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="35962-160">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="35962-161">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="35962-161">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="35962-162">xs:string</span><span class="sxs-lookup"><span data-stu-id="35962-162">xs:string</span></span>  <br/> |<span data-ttu-id="35962-163">必需</span><span class="sxs-lookup"><span data-stu-id="35962-163">required</span></span>  <br/> |<span data-ttu-id="35962-164">指定与用于区分具有相同名称的多个位置的位置相关联的代码。</span><span class="sxs-lookup"><span data-stu-id="35962-164">Specifies the code that is associated with the location used to distinguish multiple location that have the same name.</span></span>  <br/> |<span data-ttu-id="35962-165">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="35962-165">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="35962-166">weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="35962-166">weatherlocationname</span></span>  <br/> |<span data-ttu-id="35962-167">xs:string</span><span class="sxs-lookup"><span data-stu-id="35962-167">xs:string</span></span>  <br/> |<span data-ttu-id="35962-168">必需</span><span class="sxs-lookup"><span data-stu-id="35962-168">required</span></span>  <br/> |<span data-ttu-id="35962-169">在下拉列表控件中指定的位置的显示名称。</span><span class="sxs-lookup"><span data-stu-id="35962-169">Specifies the name of the location that appears in the drop-down control.</span></span>  <br/> |<span data-ttu-id="35962-170">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="35962-170">A value of the type xs:string</span></span>  <br/> |
   

