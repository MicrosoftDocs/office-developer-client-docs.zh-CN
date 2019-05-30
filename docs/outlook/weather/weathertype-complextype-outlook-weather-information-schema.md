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
ms.openlocfilehash: ac7b8f37e71da203db0f6aefc8e20b29e810c3cf
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542945"
---
# <a name="weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="416d9-103">weatherType 复杂类型 (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="416d9-103">weatherType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="416d9-104">指定位置的天气情况。</span><span class="sxs-lookup"><span data-stu-id="416d9-104">Specifies the weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="416d9-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="416d9-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="416d9-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="416d9-106">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="416d9-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="416d9-107">**Schema file**</span></span> <br/> |<span data-ttu-id="416d9-108">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="416d9-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="416d9-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="416d9-109">**Extension base**</span></span> <br/> |<span data-ttu-id="416d9-110">无</span><span class="sxs-lookup"><span data-stu-id="416d9-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="416d9-111">定义</span><span class="sxs-lookup"><span data-stu-id="416d9-111">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="416d9-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="416d9-112">Elements and attributes</span></span>

<span data-ttu-id="416d9-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="416d9-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="416d9-114">子元素</span><span class="sxs-lookup"><span data-stu-id="416d9-114">Child elements</span></span>

|<span data-ttu-id="416d9-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="416d9-115">**Element**</span></span>|<span data-ttu-id="416d9-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="416d9-116">**Type**</span></span>|<span data-ttu-id="416d9-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="416d9-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="416d9-118">目前</span><span class="sxs-lookup"><span data-stu-id="416d9-118">current</span></span>](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="416d9-119">currentType</span><span class="sxs-lookup"><span data-stu-id="416d9-119">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="416d9-120">指定当前天气情况。</span><span class="sxs-lookup"><span data-stu-id="416d9-120">Specifies the current weather conditions.</span></span>  <br/> |
|[<span data-ttu-id="416d9-121">预测</span><span class="sxs-lookup"><span data-stu-id="416d9-121">forecast</span></span>](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="416d9-122">forecastType</span><span class="sxs-lookup"><span data-stu-id="416d9-122">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="416d9-123">指定至少三天前的后续天气条件, 包括今天: 今天、明天、一天后。</span><span class="sxs-lookup"><span data-stu-id="416d9-123">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="416d9-124">属性</span><span class="sxs-lookup"><span data-stu-id="416d9-124">Attributes</span></span>

|<span data-ttu-id="416d9-125">**属性**</span><span class="sxs-lookup"><span data-stu-id="416d9-125">**Attribute**</span></span>|<span data-ttu-id="416d9-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="416d9-126">**Type**</span></span>|<span data-ttu-id="416d9-127">**必需**</span><span class="sxs-lookup"><span data-stu-id="416d9-127">**Required**</span></span>|<span data-ttu-id="416d9-128">**描述**</span><span class="sxs-lookup"><span data-stu-id="416d9-128">**Description**</span></span>|<span data-ttu-id="416d9-129">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="416d9-129">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="416d9-130">attribution</span><span class="sxs-lookup"><span data-stu-id="416d9-130">attribution</span></span>  <br/> |<span data-ttu-id="416d9-131">xs: string</span><span class="sxs-lookup"><span data-stu-id="416d9-131">xs:string</span></span>  <br/> |<span data-ttu-id="416d9-132">必需</span><span class="sxs-lookup"><span data-stu-id="416d9-132">required</span></span>  <br/> |<span data-ttu-id="416d9-133">指定天气信息的来源。</span><span class="sxs-lookup"><span data-stu-id="416d9-133">Specifies the source of the weather information.</span></span>  <br/> |<span data-ttu-id="416d9-134">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="416d9-134">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="416d9-135">degreetype</span><span class="sxs-lookup"><span data-stu-id="416d9-135">degreetype</span></span>  <br/> |<span data-ttu-id="416d9-136">xs: string</span><span class="sxs-lookup"><span data-stu-id="416d9-136">xs:string</span></span>  <br/> |<span data-ttu-id="416d9-137">必需</span><span class="sxs-lookup"><span data-stu-id="416d9-137">required</span></span>  <br/> |<span data-ttu-id="416d9-138">指定位置温度的单位 (例如, 摄氏温度)。</span><span class="sxs-lookup"><span data-stu-id="416d9-138">Specifies the unit for the temperature of the location for example, Celsius.</span></span>  <br/> |<span data-ttu-id="416d9-139">C、F</span><span class="sxs-lookup"><span data-stu-id="416d9-139">C, F</span></span>  <br/> |
|<span data-ttu-id="416d9-140">imagerelativeurl</span><span class="sxs-lookup"><span data-stu-id="416d9-140">imagerelativeurl</span></span>  <br/> |<span data-ttu-id="416d9-141">xs: string</span><span class="sxs-lookup"><span data-stu-id="416d9-141">xs:string</span></span>  <br/> |<span data-ttu-id="416d9-142">必需</span><span class="sxs-lookup"><span data-stu-id="416d9-142">required</span></span>  <br/> |<span data-ttu-id="416d9-143">指定位置的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="416d9-143">Specifies the URL of the image for the location.</span></span>  <br/> |<span data-ttu-id="416d9-144">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="416d9-144">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="416d9-145">时区</span><span class="sxs-lookup"><span data-stu-id="416d9-145">timezone</span></span>  <br/> |<span data-ttu-id="416d9-146">xs: integer</span><span class="sxs-lookup"><span data-stu-id="416d9-146">xs:integer</span></span>  <br/> |<span data-ttu-id="416d9-147">必需</span><span class="sxs-lookup"><span data-stu-id="416d9-147">required</span></span>  <br/> |<span data-ttu-id="416d9-148">指定 GMT 偏移量。</span><span class="sxs-lookup"><span data-stu-id="416d9-148">Specifies the GMT offset.</span></span>  <br/> |<span data-ttu-id="416d9-149">介于-11 和12之间的值 (含)</span><span class="sxs-lookup"><span data-stu-id="416d9-149">A value between -11 and 12 inclusive</span></span>  <br/> |
|<span data-ttu-id="416d9-150">url</span><span class="sxs-lookup"><span data-stu-id="416d9-150">url</span></span>  <br/> |<span data-ttu-id="416d9-151">xs: string</span><span class="sxs-lookup"><span data-stu-id="416d9-151">xs:string</span></span>  <br/> |<span data-ttu-id="416d9-152">必需</span><span class="sxs-lookup"><span data-stu-id="416d9-152">required</span></span>  <br/> |<span data-ttu-id="416d9-153">指定包含指定位置的天气信息的天气服务网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="416d9-153">Specifies the URL for the web page of the weather service that contains weather information for the specified location.</span></span>  <br/> |<span data-ttu-id="416d9-154">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="416d9-154">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="416d9-155">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="416d9-155">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="416d9-156">xs: string</span><span class="sxs-lookup"><span data-stu-id="416d9-156">xs:string</span></span>  <br/> |<span data-ttu-id="416d9-157">必需</span><span class="sxs-lookup"><span data-stu-id="416d9-157">required</span></span>  <br/> |<span data-ttu-id="416d9-158">指定与用于区分具有相同名称的多个位置的位置相关联的代码。</span><span class="sxs-lookup"><span data-stu-id="416d9-158">Specifies the code that is associated with the location used to distinguish multiple location that have the same name.</span></span>  <br/> |<span data-ttu-id="416d9-159">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="416d9-159">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="416d9-160">表示 weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="416d9-160">weatherlocationname</span></span>  <br/> |<span data-ttu-id="416d9-161">xs: string</span><span class="sxs-lookup"><span data-stu-id="416d9-161">xs:string</span></span>  <br/> |<span data-ttu-id="416d9-162">必需</span><span class="sxs-lookup"><span data-stu-id="416d9-162">required</span></span>  <br/> |<span data-ttu-id="416d9-163">指定在下拉控件中显示的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="416d9-163">Specifies the name of the location that appears in the drop-down control.</span></span>  <br/> |<span data-ttu-id="416d9-164">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="416d9-164">A value of the type xs:string</span></span>  <br/> |
   

