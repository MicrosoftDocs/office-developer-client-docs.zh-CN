---
title: 'forecast 元素 (weatherType complexType)  (Outlook Weather Information Schema) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9124fa30-d58b-8354-91e9-8d2237a8251d
description: 指定至少提前三天的未来天气条件，包括今天、明天、明天后一天。
ms.openlocfilehash: 5e442ee5995bbd51c5e518162286bc199a625dbd
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540978"
---
# <a name="forecast-element-weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="2039b-103">forecast 元素 (weatherType complexType)  (Outlook Weather Information Schema) </span><span class="sxs-lookup"><span data-stu-id="2039b-103">forecast element (weatherType complexType) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="2039b-104">指定至少提前三天的未来天气条件，包括今天、明天、明天后一天。</span><span class="sxs-lookup"><span data-stu-id="2039b-104">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2039b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="2039b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2039b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2039b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="2039b-107">forecastType</span><span class="sxs-lookup"><span data-stu-id="2039b-107">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="2039b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2039b-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="2039b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2039b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="2039b-110">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="2039b-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2039b-111">定义</span><span class="sxs-lookup"><span data-stu-id="2039b-111">Definition</span></span>

```XML
<xs:element name="forecast"      type="forecastType" minOccurs="3"     maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="2039b-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2039b-112">Elements and attributes</span></span>

<span data-ttu-id="2039b-113">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2039b-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="2039b-114">父元素</span><span class="sxs-lookup"><span data-stu-id="2039b-114">Parent elements</span></span>

|<span data-ttu-id="2039b-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="2039b-115">**Element**</span></span>|<span data-ttu-id="2039b-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="2039b-116">**Type**</span></span>|<span data-ttu-id="2039b-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="2039b-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2039b-118">weather</span><span class="sxs-lookup"><span data-stu-id="2039b-118">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="2039b-119">weatherType</span><span class="sxs-lookup"><span data-stu-id="2039b-119">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="2039b-120">指定位置的天气状况。</span><span class="sxs-lookup"><span data-stu-id="2039b-120">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="2039b-121">子元素</span><span class="sxs-lookup"><span data-stu-id="2039b-121">Child elements</span></span>

<span data-ttu-id="2039b-122">无。</span><span class="sxs-lookup"><span data-stu-id="2039b-122">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2039b-123">属性</span><span class="sxs-lookup"><span data-stu-id="2039b-123">Attributes</span></span>

|<span data-ttu-id="2039b-124">**属性**</span><span class="sxs-lookup"><span data-stu-id="2039b-124">**Attribute**</span></span>|<span data-ttu-id="2039b-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="2039b-125">**Type**</span></span>|<span data-ttu-id="2039b-126">**必需**</span><span class="sxs-lookup"><span data-stu-id="2039b-126">**Required**</span></span>|<span data-ttu-id="2039b-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="2039b-127">**Description**</span></span>|<span data-ttu-id="2039b-128">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2039b-128">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2039b-129">date</span><span class="sxs-lookup"><span data-stu-id="2039b-129">date</span></span>  <br/> |<span data-ttu-id="2039b-130">xs：date</span><span class="sxs-lookup"><span data-stu-id="2039b-130">xs:date</span></span>  <br/> |<span data-ttu-id="2039b-131">必需</span><span class="sxs-lookup"><span data-stu-id="2039b-131">required</span></span>  <br/> |<span data-ttu-id="2039b-132">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="2039b-132">Specifies the date for the forecast.</span></span>  <br/> |<span data-ttu-id="2039b-133">xs：date 类型的值</span><span class="sxs-lookup"><span data-stu-id="2039b-133">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="2039b-134">day</span><span class="sxs-lookup"><span data-stu-id="2039b-134">day</span></span>  <br/> |<span data-ttu-id="2039b-135">xs：string</span><span class="sxs-lookup"><span data-stu-id="2039b-135">xs:string</span></span>  <br/> |<span data-ttu-id="2039b-136">必需</span><span class="sxs-lookup"><span data-stu-id="2039b-136">required</span></span>  <br/> |<span data-ttu-id="2039b-137">指定预测的一天。</span><span class="sxs-lookup"><span data-stu-id="2039b-137">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="2039b-138">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="2039b-138">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2039b-139">high</span><span class="sxs-lookup"><span data-stu-id="2039b-139">high</span></span>  <br/> |<span data-ttu-id="2039b-140">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2039b-140">xs:integer</span></span>  <br/> |<span data-ttu-id="2039b-141">必需</span><span class="sxs-lookup"><span data-stu-id="2039b-141">required</span></span>  <br/> |<span data-ttu-id="2039b-142">指定预测的最高温度。</span><span class="sxs-lookup"><span data-stu-id="2039b-142">Specifies the forecasted highest temperature.</span></span>  <br/> |<span data-ttu-id="2039b-143">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2039b-143">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="2039b-144">low</span><span class="sxs-lookup"><span data-stu-id="2039b-144">low</span></span>  <br/> |<span data-ttu-id="2039b-145">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2039b-145">xs:integer</span></span>  <br/> |<span data-ttu-id="2039b-146">必需</span><span class="sxs-lookup"><span data-stu-id="2039b-146">required</span></span>  <br/> |<span data-ttu-id="2039b-147">指定预测的最低温度。</span><span class="sxs-lookup"><span data-stu-id="2039b-147">Specifies the forecasted lowest temperature.</span></span>  <br/> |<span data-ttu-id="2039b-148">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2039b-148">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="2039b-149">precip</span><span class="sxs-lookup"><span data-stu-id="2039b-149">precip</span></span>  <br/> |<span data-ttu-id="2039b-150">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2039b-150">xs:integer</span></span>  <br/> |<span data-ttu-id="2039b-151">必需</span><span class="sxs-lookup"><span data-stu-id="2039b-151">required</span></span>  <br/> |<span data-ttu-id="2039b-152">指定可能性的百分比。</span><span class="sxs-lookup"><span data-stu-id="2039b-152">Specifies the percentage possibility of precipitation.</span></span>  <br/> |<span data-ttu-id="2039b-153">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2039b-153">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="2039b-154">shortday</span><span class="sxs-lookup"><span data-stu-id="2039b-154">shortday</span></span>  <br/> |<span data-ttu-id="2039b-155">xs：string</span><span class="sxs-lookup"><span data-stu-id="2039b-155">xs:string</span></span>  <br/> |<span data-ttu-id="2039b-156">必需</span><span class="sxs-lookup"><span data-stu-id="2039b-156">required</span></span>  <br/> |<span data-ttu-id="2039b-157">以缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="2039b-157">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="2039b-158">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="2039b-158">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2039b-159">skycodeday</span><span class="sxs-lookup"><span data-stu-id="2039b-159">skycodeday</span></span>  <br/> |<span data-ttu-id="2039b-160">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2039b-160">xs:integer</span></span>  <br/> |<span data-ttu-id="2039b-161">必需</span><span class="sxs-lookup"><span data-stu-id="2039b-161">required</span></span>  <br/> |<span data-ttu-id="2039b-162">指定预测条件的代码。</span><span class="sxs-lookup"><span data-stu-id="2039b-162">Specifies a code for the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="2039b-163">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2039b-163">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="2039b-164">skytextday</span><span class="sxs-lookup"><span data-stu-id="2039b-164">skytextday</span></span>  <br/> |<span data-ttu-id="2039b-165">xs：string</span><span class="sxs-lookup"><span data-stu-id="2039b-165">xs:string</span></span>  <br/> |<span data-ttu-id="2039b-166">必需</span><span class="sxs-lookup"><span data-stu-id="2039b-166">required</span></span>  <br/> |<span data-ttu-id="2039b-167">指定描述预测条件的一到两个单词。</span><span class="sxs-lookup"><span data-stu-id="2039b-167">Specifies one to two words that describe the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="2039b-168">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="2039b-168">A value of the type xs:string</span></span>  <br/> |
   

