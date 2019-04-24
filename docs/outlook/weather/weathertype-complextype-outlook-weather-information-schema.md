---
title: weatherType 复杂类型 (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b94d848e-868a-5d5e-ad82-39ed9bd5b357
description: 指定位置的天气情况。
ms.openlocfilehash: ffa91c4982b5703041c79b47eb15a3a2b845b429
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355039"
---
# <a name="weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="574e6-103">weatherType 复杂类型 (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="574e6-103">weatherType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="574e6-104">指定位置的天气情况。</span><span class="sxs-lookup"><span data-stu-id="574e6-104">Specifies the weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="574e6-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="574e6-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="574e6-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="574e6-106">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="574e6-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="574e6-107">**Schema file**</span></span> <br/> |<span data-ttu-id="574e6-108">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="574e6-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="574e6-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="574e6-109">**Extension base**</span></span> <br/> |<span data-ttu-id="574e6-110">无</span><span class="sxs-lookup"><span data-stu-id="574e6-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="574e6-111">定义</span><span class="sxs-lookup"><span data-stu-id="574e6-111">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="574e6-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="574e6-112">Elements and attributes</span></span>

<span data-ttu-id="574e6-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="574e6-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="574e6-114">子元素</span><span class="sxs-lookup"><span data-stu-id="574e6-114">Child elements</span></span>

|<span data-ttu-id="574e6-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="574e6-115">**Element**</span></span>|<span data-ttu-id="574e6-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="574e6-116">**Type**</span></span>|<span data-ttu-id="574e6-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="574e6-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="574e6-118">目前</span><span class="sxs-lookup"><span data-stu-id="574e6-118">current</span></span>](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="574e6-119">currentType</span><span class="sxs-lookup"><span data-stu-id="574e6-119">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="574e6-120">指定当前天气情况。</span><span class="sxs-lookup"><span data-stu-id="574e6-120">Specifies the current weather conditions.</span></span>  <br/> |
|[<span data-ttu-id="574e6-121">预测</span><span class="sxs-lookup"><span data-stu-id="574e6-121">forecast</span></span>](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="574e6-122">forecastType</span><span class="sxs-lookup"><span data-stu-id="574e6-122">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="574e6-123">指定至少三天前的后续天气条件, 包括今天: 今天、明天、一天后。</span><span class="sxs-lookup"><span data-stu-id="574e6-123">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="574e6-124">属性</span><span class="sxs-lookup"><span data-stu-id="574e6-124">Attributes</span></span>

|<span data-ttu-id="574e6-125">**属性**</span><span class="sxs-lookup"><span data-stu-id="574e6-125">**Attribute**</span></span>|<span data-ttu-id="574e6-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="574e6-126">**Type**</span></span>|<span data-ttu-id="574e6-127">**必需**</span><span class="sxs-lookup"><span data-stu-id="574e6-127">**Required**</span></span>|<span data-ttu-id="574e6-128">**描述**</span><span class="sxs-lookup"><span data-stu-id="574e6-128">**Description**</span></span>|<span data-ttu-id="574e6-129">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="574e6-129">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="574e6-130">attribution</span><span class="sxs-lookup"><span data-stu-id="574e6-130">attribution</span></span>  <br/> |<span data-ttu-id="574e6-131">xs: string</span><span class="sxs-lookup"><span data-stu-id="574e6-131">xs:string</span></span>  <br/> |<span data-ttu-id="574e6-132">必需</span><span class="sxs-lookup"><span data-stu-id="574e6-132">required</span></span>  <br/> |<span data-ttu-id="574e6-133">指定天气信息的来源。</span><span class="sxs-lookup"><span data-stu-id="574e6-133">Specifies the source of the weather information.</span></span>  <br/> |<span data-ttu-id="574e6-134">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="574e6-134">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="574e6-135">degreetype</span><span class="sxs-lookup"><span data-stu-id="574e6-135">degreetype</span></span>  <br/> |<span data-ttu-id="574e6-136">xs: string</span><span class="sxs-lookup"><span data-stu-id="574e6-136">xs:string</span></span>  <br/> |<span data-ttu-id="574e6-137">必需</span><span class="sxs-lookup"><span data-stu-id="574e6-137">required</span></span>  <br/> |<span data-ttu-id="574e6-138">指定位置温度的单位 (例如, 摄氏温度)。</span><span class="sxs-lookup"><span data-stu-id="574e6-138">Specifies the unit for the temperature of the location for example, Celsius.</span></span>  <br/> |<span data-ttu-id="574e6-139">C、F</span><span class="sxs-lookup"><span data-stu-id="574e6-139">C, F</span></span>  <br/> |
|<span data-ttu-id="574e6-140">imagerelativeurl</span><span class="sxs-lookup"><span data-stu-id="574e6-140">imagerelativeurl</span></span>  <br/> |<span data-ttu-id="574e6-141">xs: string</span><span class="sxs-lookup"><span data-stu-id="574e6-141">xs:string</span></span>  <br/> |<span data-ttu-id="574e6-142">必需</span><span class="sxs-lookup"><span data-stu-id="574e6-142">required</span></span>  <br/> |<span data-ttu-id="574e6-143">指定位置的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="574e6-143">Specifies the URL of the image for the location.</span></span>  <br/> |<span data-ttu-id="574e6-144">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="574e6-144">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="574e6-145">时区</span><span class="sxs-lookup"><span data-stu-id="574e6-145">timezone</span></span>  <br/> |<span data-ttu-id="574e6-146">xs: integer</span><span class="sxs-lookup"><span data-stu-id="574e6-146">xs:integer</span></span>  <br/> |<span data-ttu-id="574e6-147">必需</span><span class="sxs-lookup"><span data-stu-id="574e6-147">required</span></span>  <br/> |<span data-ttu-id="574e6-148">指定 GMT 偏移量。</span><span class="sxs-lookup"><span data-stu-id="574e6-148">Specifies the GMT offset.</span></span>  <br/> |<span data-ttu-id="574e6-149">介于-11 和12之间的值 (含)</span><span class="sxs-lookup"><span data-stu-id="574e6-149">A value between -11 and 12 inclusive</span></span>  <br/> |
|<span data-ttu-id="574e6-150">url</span><span class="sxs-lookup"><span data-stu-id="574e6-150">url</span></span>  <br/> |<span data-ttu-id="574e6-151">xs: string</span><span class="sxs-lookup"><span data-stu-id="574e6-151">xs:string</span></span>  <br/> |<span data-ttu-id="574e6-152">必需</span><span class="sxs-lookup"><span data-stu-id="574e6-152">required</span></span>  <br/> |<span data-ttu-id="574e6-153">指定包含指定位置的天气信息的天气服务网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="574e6-153">Specifies the URL for the web page of the weather service that contains weather information for the specified location.</span></span>  <br/> |<span data-ttu-id="574e6-154">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="574e6-154">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="574e6-155">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="574e6-155">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="574e6-156">xs: string</span><span class="sxs-lookup"><span data-stu-id="574e6-156">xs:string</span></span>  <br/> |<span data-ttu-id="574e6-157">必需</span><span class="sxs-lookup"><span data-stu-id="574e6-157">required</span></span>  <br/> |<span data-ttu-id="574e6-158">指定与用于区分具有相同名称的多个位置的位置相关联的代码。</span><span class="sxs-lookup"><span data-stu-id="574e6-158">Specifies the code that is associated with the location used to distinguish multiple location that have the same name.</span></span>  <br/> |<span data-ttu-id="574e6-159">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="574e6-159">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="574e6-160">表示 weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="574e6-160">weatherlocationname</span></span>  <br/> |<span data-ttu-id="574e6-161">xs: string</span><span class="sxs-lookup"><span data-stu-id="574e6-161">xs:string</span></span>  <br/> |<span data-ttu-id="574e6-162">必需</span><span class="sxs-lookup"><span data-stu-id="574e6-162">required</span></span>  <br/> |<span data-ttu-id="574e6-163">指定在下拉控件中显示的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="574e6-163">Specifies the name of the location that appears in the drop-down control.</span></span>  <br/> |<span data-ttu-id="574e6-164">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="574e6-164">A value of the type xs:string</span></span>  <br/> |
   

