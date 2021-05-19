---
title: 'weatherType complexType (Outlook Weather Information Schema) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b94d848e-868a-5d5e-ad82-39ed9bd5b357
description: 指定位置的天气状况。
ms.openlocfilehash: ac7b8f37e71da203db0f6aefc8e20b29e810c3cf
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542945"
---
# <a name="weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="034e1-103">weatherType complexType (Outlook Weather Information Schema) </span><span class="sxs-lookup"><span data-stu-id="034e1-103">weatherType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="034e1-104">指定位置的天气状况。</span><span class="sxs-lookup"><span data-stu-id="034e1-104">Specifies the weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="034e1-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="034e1-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="034e1-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="034e1-106">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="034e1-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="034e1-107">**Schema file**</span></span> <br/> |<span data-ttu-id="034e1-108">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="034e1-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="034e1-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="034e1-109">**Extension base**</span></span> <br/> |<span data-ttu-id="034e1-110">无</span><span class="sxs-lookup"><span data-stu-id="034e1-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="034e1-111">定义</span><span class="sxs-lookup"><span data-stu-id="034e1-111">Definition</span></span>

```XML
           <xs:complexType name="weatherType">
           <xs:sequence>
     <xs:element name="current"      type="currentType">
  </xs:element>  
     <xs:element name="forecast"      type="forecastType" minOccurs="3"     maxOccurs="unbounded"    >
  </xs:element>  
       </xs:sequence>
     <xs:attribute name="weatherlocationcode"   type="xs:string"      use="required"     />
     <xs:attribute name="timezone"   type="xs:integer"      use="required"     />
     <xs:attribute name="attribution"   type="xs:string"      use="required"     />
     <xs:attribute name="degreetype"   type="xs:string"      use="required"     />
     <xs:attribute name="imagerelativeurl"   type="xs:string"      use="required"     />
     <xs:attribute name="url"   type="xs:string"      use="required"     />
     <xs:attribute name="weatherlocationname"   type="xs:string"      use="required"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a><span data-ttu-id="034e1-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="034e1-112">Elements and attributes</span></span>

<span data-ttu-id="034e1-113">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="034e1-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="034e1-114">子元素</span><span class="sxs-lookup"><span data-stu-id="034e1-114">Child elements</span></span>

|<span data-ttu-id="034e1-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="034e1-115">**Element**</span></span>|<span data-ttu-id="034e1-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="034e1-116">**Type**</span></span>|<span data-ttu-id="034e1-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="034e1-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="034e1-118">current</span><span class="sxs-lookup"><span data-stu-id="034e1-118">current</span></span>](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="034e1-119">currentType</span><span class="sxs-lookup"><span data-stu-id="034e1-119">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="034e1-120">指定当前天气状况。</span><span class="sxs-lookup"><span data-stu-id="034e1-120">Specifies the current weather conditions.</span></span>  <br/> |
|[<span data-ttu-id="034e1-121">forecast</span><span class="sxs-lookup"><span data-stu-id="034e1-121">forecast</span></span>](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="034e1-122">forecastType</span><span class="sxs-lookup"><span data-stu-id="034e1-122">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="034e1-123">指定至少提前三天的未来天气条件，包括今天、明天、明天后一天。</span><span class="sxs-lookup"><span data-stu-id="034e1-123">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="034e1-124">属性</span><span class="sxs-lookup"><span data-stu-id="034e1-124">Attributes</span></span>

|<span data-ttu-id="034e1-125">**属性**</span><span class="sxs-lookup"><span data-stu-id="034e1-125">**Attribute**</span></span>|<span data-ttu-id="034e1-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="034e1-126">**Type**</span></span>|<span data-ttu-id="034e1-127">**必需**</span><span class="sxs-lookup"><span data-stu-id="034e1-127">**Required**</span></span>|<span data-ttu-id="034e1-128">**描述**</span><span class="sxs-lookup"><span data-stu-id="034e1-128">**Description**</span></span>|<span data-ttu-id="034e1-129">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="034e1-129">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="034e1-130">attribution</span><span class="sxs-lookup"><span data-stu-id="034e1-130">attribution</span></span>  <br/> |<span data-ttu-id="034e1-131">xs：string</span><span class="sxs-lookup"><span data-stu-id="034e1-131">xs:string</span></span>  <br/> |<span data-ttu-id="034e1-132">必需</span><span class="sxs-lookup"><span data-stu-id="034e1-132">required</span></span>  <br/> |<span data-ttu-id="034e1-133">指定天气信息的来源。</span><span class="sxs-lookup"><span data-stu-id="034e1-133">Specifies the source of the weather information.</span></span>  <br/> |<span data-ttu-id="034e1-134">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="034e1-134">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="034e1-135">degreetype</span><span class="sxs-lookup"><span data-stu-id="034e1-135">degreetype</span></span>  <br/> |<span data-ttu-id="034e1-136">xs：string</span><span class="sxs-lookup"><span data-stu-id="034e1-136">xs:string</span></span>  <br/> |<span data-ttu-id="034e1-137">必需</span><span class="sxs-lookup"><span data-stu-id="034e1-137">required</span></span>  <br/> |<span data-ttu-id="034e1-138">指定位置温度的单位，例如，摄氏度。</span><span class="sxs-lookup"><span data-stu-id="034e1-138">Specifies the unit for the temperature of the location for example, Celsius.</span></span>  <br/> |<span data-ttu-id="034e1-139">C、F</span><span class="sxs-lookup"><span data-stu-id="034e1-139">C, F</span></span>  <br/> |
|<span data-ttu-id="034e1-140">imagerelativeurl</span><span class="sxs-lookup"><span data-stu-id="034e1-140">imagerelativeurl</span></span>  <br/> |<span data-ttu-id="034e1-141">xs：string</span><span class="sxs-lookup"><span data-stu-id="034e1-141">xs:string</span></span>  <br/> |<span data-ttu-id="034e1-142">必需</span><span class="sxs-lookup"><span data-stu-id="034e1-142">required</span></span>  <br/> |<span data-ttu-id="034e1-143">指定位置的图像 URL。</span><span class="sxs-lookup"><span data-stu-id="034e1-143">Specifies the URL of the image for the location.</span></span>  <br/> |<span data-ttu-id="034e1-144">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="034e1-144">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="034e1-145">timezone</span><span class="sxs-lookup"><span data-stu-id="034e1-145">timezone</span></span>  <br/> |<span data-ttu-id="034e1-146">xs：integer</span><span class="sxs-lookup"><span data-stu-id="034e1-146">xs:integer</span></span>  <br/> |<span data-ttu-id="034e1-147">必需</span><span class="sxs-lookup"><span data-stu-id="034e1-147">required</span></span>  <br/> |<span data-ttu-id="034e1-148">指定 GMT 偏移量。</span><span class="sxs-lookup"><span data-stu-id="034e1-148">Specifies the GMT offset.</span></span>  <br/> |<span data-ttu-id="034e1-149">介于 -11 和 12（含这两个值）之间的值</span><span class="sxs-lookup"><span data-stu-id="034e1-149">A value between -11 and 12 inclusive</span></span>  <br/> |
|<span data-ttu-id="034e1-150">url</span><span class="sxs-lookup"><span data-stu-id="034e1-150">url</span></span>  <br/> |<span data-ttu-id="034e1-151">xs：string</span><span class="sxs-lookup"><span data-stu-id="034e1-151">xs:string</span></span>  <br/> |<span data-ttu-id="034e1-152">必需</span><span class="sxs-lookup"><span data-stu-id="034e1-152">required</span></span>  <br/> |<span data-ttu-id="034e1-153">指定包含指定位置的天气信息的天气服务网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="034e1-153">Specifies the URL for the web page of the weather service that contains weather information for the specified location.</span></span>  <br/> |<span data-ttu-id="034e1-154">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="034e1-154">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="034e1-155">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="034e1-155">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="034e1-156">xs：string</span><span class="sxs-lookup"><span data-stu-id="034e1-156">xs:string</span></span>  <br/> |<span data-ttu-id="034e1-157">必需</span><span class="sxs-lookup"><span data-stu-id="034e1-157">required</span></span>  <br/> |<span data-ttu-id="034e1-158">指定与用于区分多个同名位置的位置关联的代码。</span><span class="sxs-lookup"><span data-stu-id="034e1-158">Specifies the code that is associated with the location used to distinguish multiple location that have the same name.</span></span>  <br/> |<span data-ttu-id="034e1-159">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="034e1-159">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="034e1-160">weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="034e1-160">weatherlocationname</span></span>  <br/> |<span data-ttu-id="034e1-161">xs：string</span><span class="sxs-lookup"><span data-stu-id="034e1-161">xs:string</span></span>  <br/> |<span data-ttu-id="034e1-162">必需</span><span class="sxs-lookup"><span data-stu-id="034e1-162">required</span></span>  <br/> |<span data-ttu-id="034e1-163">指定下拉列表控件中显示的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="034e1-163">Specifies the name of the location that appears in the drop-down control.</span></span>  <br/> |<span data-ttu-id="034e1-164">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="034e1-164">A value of the type xs:string</span></span>  <br/> |
   

