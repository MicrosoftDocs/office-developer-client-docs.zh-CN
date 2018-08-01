---
title: weatherType 复杂类型 （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b94d848e-868a-5d5e-ad82-39ed9bd5b357
description: 指定一个位置的天气条件。
ms.openlocfilehash: b333bb6ce60dd1613bceda0a57e7e34c9819bd84
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779413"
---
# <a name="weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="977f3-103">weatherType 复杂类型 （Outlook 天气信息架构）</span><span class="sxs-lookup"><span data-stu-id="977f3-103">weatherType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="977f3-104">指定一个位置的天气条件。</span><span class="sxs-lookup"><span data-stu-id="977f3-104">Specifies the weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="977f3-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="977f3-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="977f3-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="977f3-106">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="977f3-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="977f3-107">**Schema file**</span></span> <br/> |<span data-ttu-id="977f3-108">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="977f3-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="977f3-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="977f3-109">**Extension base**</span></span> <br/> |<span data-ttu-id="977f3-110">无</span><span class="sxs-lookup"><span data-stu-id="977f3-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="977f3-111">定义</span><span class="sxs-lookup"><span data-stu-id="977f3-111">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="977f3-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="977f3-112">Elements and attributes</span></span>

<span data-ttu-id="977f3-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="977f3-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="977f3-114">子元素</span><span class="sxs-lookup"><span data-stu-id="977f3-114">Child elements</span></span>

|<span data-ttu-id="977f3-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="977f3-115">**Element**</span></span>|<span data-ttu-id="977f3-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="977f3-116">**Type**</span></span>|<span data-ttu-id="977f3-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="977f3-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="977f3-118">当前</span><span class="sxs-lookup"><span data-stu-id="977f3-118">current</span></span>](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="977f3-119">currentType</span><span class="sxs-lookup"><span data-stu-id="977f3-119">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="977f3-120">指定当前的天气条件。</span><span class="sxs-lookup"><span data-stu-id="977f3-120">Specifies the current weather conditions.</span></span>  <br/> |
|[<span data-ttu-id="977f3-121">预测</span><span class="sxs-lookup"><span data-stu-id="977f3-121">forecast</span></span>](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="977f3-122">forecastType</span><span class="sxs-lookup"><span data-stu-id="977f3-122">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="977f3-123">指定至少三天提前包括今天的未来的天气条件： 今天，明天，天 after 明天。</span><span class="sxs-lookup"><span data-stu-id="977f3-123">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="977f3-124">Attributes</span><span class="sxs-lookup"><span data-stu-id="977f3-124">Attributes</span></span>

|<span data-ttu-id="977f3-125">**属性**</span><span class="sxs-lookup"><span data-stu-id="977f3-125">**Attribute**</span></span>|<span data-ttu-id="977f3-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="977f3-126">**Type**</span></span>|<span data-ttu-id="977f3-127">**必需**</span><span class="sxs-lookup"><span data-stu-id="977f3-127">**Required**</span></span>|<span data-ttu-id="977f3-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="977f3-128">**Description**</span></span>|<span data-ttu-id="977f3-129">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="977f3-129">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="977f3-130">属性</span><span class="sxs-lookup"><span data-stu-id="977f3-130">attribution</span></span>  <br/> |<span data-ttu-id="977f3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="977f3-131">xs:string</span></span>  <br/> |<span data-ttu-id="977f3-132">必需</span><span class="sxs-lookup"><span data-stu-id="977f3-132">required</span></span>  <br/> |<span data-ttu-id="977f3-133">指定的天气信息的源。</span><span class="sxs-lookup"><span data-stu-id="977f3-133">Specifies the source of the weather information.</span></span>  <br/> |<span data-ttu-id="977f3-134">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="977f3-134">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="977f3-135">degreetype</span><span class="sxs-lookup"><span data-stu-id="977f3-135">degreetype</span></span>  <br/> |<span data-ttu-id="977f3-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="977f3-136">xs:string</span></span>  <br/> |<span data-ttu-id="977f3-137">必需</span><span class="sxs-lookup"><span data-stu-id="977f3-137">required</span></span>  <br/> |<span data-ttu-id="977f3-138">指定的位置，如摄氏度温度的单位。</span><span class="sxs-lookup"><span data-stu-id="977f3-138">Specifies the unit for the temperature of the location for example, Celsius.</span></span>  <br/> |<span data-ttu-id="977f3-139">C F</span><span class="sxs-lookup"><span data-stu-id="977f3-139">C, F</span></span>  <br/> |
|<span data-ttu-id="977f3-140">imagerelativeurl</span><span class="sxs-lookup"><span data-stu-id="977f3-140">imagerelativeurl</span></span>  <br/> |<span data-ttu-id="977f3-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="977f3-141">xs:string</span></span>  <br/> |<span data-ttu-id="977f3-142">必需</span><span class="sxs-lookup"><span data-stu-id="977f3-142">required</span></span>  <br/> |<span data-ttu-id="977f3-143">指定位置的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="977f3-143">Specifies the URL of the image for the location.</span></span>  <br/> |<span data-ttu-id="977f3-144">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="977f3-144">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="977f3-145">timezone</span><span class="sxs-lookup"><span data-stu-id="977f3-145">timezone</span></span>  <br/> |<span data-ttu-id="977f3-146">xs:integer</span><span class="sxs-lookup"><span data-stu-id="977f3-146">xs:integer</span></span>  <br/> |<span data-ttu-id="977f3-147">必需</span><span class="sxs-lookup"><span data-stu-id="977f3-147">required</span></span>  <br/> |<span data-ttu-id="977f3-148">指定格林威治标准时间偏移量。</span><span class="sxs-lookup"><span data-stu-id="977f3-148">Specifies the GMT offset.</span></span>  <br/> |<span data-ttu-id="977f3-149">-11 和 12 非独占之间的值</span><span class="sxs-lookup"><span data-stu-id="977f3-149">A value between -11 and 12 inclusive</span></span>  <br/> |
|<span data-ttu-id="977f3-150">url</span><span class="sxs-lookup"><span data-stu-id="977f3-150">url</span></span>  <br/> |<span data-ttu-id="977f3-151">xs:string</span><span class="sxs-lookup"><span data-stu-id="977f3-151">xs:string</span></span>  <br/> |<span data-ttu-id="977f3-152">必需</span><span class="sxs-lookup"><span data-stu-id="977f3-152">required</span></span>  <br/> |<span data-ttu-id="977f3-153">指定包含指定的位置的天气信息的天气服务网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="977f3-153">Specifies the URL for the web page of the weather service that contains weather information for the specified location.</span></span>  <br/> |<span data-ttu-id="977f3-154">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="977f3-154">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="977f3-155">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="977f3-155">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="977f3-156">xs:string</span><span class="sxs-lookup"><span data-stu-id="977f3-156">xs:string</span></span>  <br/> |<span data-ttu-id="977f3-157">必需</span><span class="sxs-lookup"><span data-stu-id="977f3-157">required</span></span>  <br/> |<span data-ttu-id="977f3-158">指定与用于区分具有相同名称的多个位置的位置相关联的代码。</span><span class="sxs-lookup"><span data-stu-id="977f3-158">Specifies the code that is associated with the location used to distinguish multiple location that have the same name.</span></span>  <br/> |<span data-ttu-id="977f3-159">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="977f3-159">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="977f3-160">weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="977f3-160">weatherlocationname</span></span>  <br/> |<span data-ttu-id="977f3-161">xs:string</span><span class="sxs-lookup"><span data-stu-id="977f3-161">xs:string</span></span>  <br/> |<span data-ttu-id="977f3-162">必需</span><span class="sxs-lookup"><span data-stu-id="977f3-162">required</span></span>  <br/> |<span data-ttu-id="977f3-163">在下拉列表控件中指定的位置的显示名称。</span><span class="sxs-lookup"><span data-stu-id="977f3-163">Specifies the name of the location that appears in the drop-down control.</span></span>  <br/> |<span data-ttu-id="977f3-164">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="977f3-164">A value of the type xs:string</span></span>  <br/> |
   

