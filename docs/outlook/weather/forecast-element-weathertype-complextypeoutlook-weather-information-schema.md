---
title: 预报元素 (weatherType 复杂类型) (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9124fa30-d58b-8354-91e9-8d2237a8251d
description: '指定至少三天前的后续天气条件, 包括今天: 今天、明天、一天后。'
ms.openlocfilehash: 5e442ee5995bbd51c5e518162286bc199a625dbd
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540978"
---
# <a name="forecast-element-weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="75c67-103">预报元素 (weatherType 复杂类型) (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="75c67-103">forecast element (weatherType complexType) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="75c67-104">指定至少三天前的后续天气条件, 包括今天: 今天、明天、一天后。</span><span class="sxs-lookup"><span data-stu-id="75c67-104">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="75c67-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="75c67-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="75c67-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="75c67-106">**Element type**</span></span> <br/> |[<span data-ttu-id="75c67-107">forecastType</span><span class="sxs-lookup"><span data-stu-id="75c67-107">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="75c67-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="75c67-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="75c67-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="75c67-109">**Schema file**</span></span> <br/> |<span data-ttu-id="75c67-110">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="75c67-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="75c67-111">定义</span><span class="sxs-lookup"><span data-stu-id="75c67-111">Definition</span></span>

```XML
<xs:element name="forecast"      type="forecastType" minOccurs="3"     maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="75c67-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="75c67-112">Elements and attributes</span></span>

<span data-ttu-id="75c67-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="75c67-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="75c67-114">父元素</span><span class="sxs-lookup"><span data-stu-id="75c67-114">Parent elements</span></span>

|<span data-ttu-id="75c67-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="75c67-115">**Element**</span></span>|<span data-ttu-id="75c67-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="75c67-116">**Type**</span></span>|<span data-ttu-id="75c67-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="75c67-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="75c67-118">气候</span><span class="sxs-lookup"><span data-stu-id="75c67-118">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="75c67-119">weatherType</span><span class="sxs-lookup"><span data-stu-id="75c67-119">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="75c67-120">指定位置的天气情况。</span><span class="sxs-lookup"><span data-stu-id="75c67-120">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="75c67-121">子元素</span><span class="sxs-lookup"><span data-stu-id="75c67-121">Child elements</span></span>

<span data-ttu-id="75c67-122">无。</span><span class="sxs-lookup"><span data-stu-id="75c67-122">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="75c67-123">属性</span><span class="sxs-lookup"><span data-stu-id="75c67-123">Attributes</span></span>

|<span data-ttu-id="75c67-124">**属性**</span><span class="sxs-lookup"><span data-stu-id="75c67-124">**Attribute**</span></span>|<span data-ttu-id="75c67-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="75c67-125">**Type**</span></span>|<span data-ttu-id="75c67-126">**必需**</span><span class="sxs-lookup"><span data-stu-id="75c67-126">**Required**</span></span>|<span data-ttu-id="75c67-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="75c67-127">**Description**</span></span>|<span data-ttu-id="75c67-128">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="75c67-128">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="75c67-129">date</span><span class="sxs-lookup"><span data-stu-id="75c67-129">date</span></span>  <br/> |<span data-ttu-id="75c67-130">xs: date</span><span class="sxs-lookup"><span data-stu-id="75c67-130">xs:date</span></span>  <br/> |<span data-ttu-id="75c67-131">必需</span><span class="sxs-lookup"><span data-stu-id="75c67-131">required</span></span>  <br/> |<span data-ttu-id="75c67-132">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="75c67-132">Specifies the date for the forecast.</span></span>  <br/> |<span data-ttu-id="75c67-133">类型 xs: date 的值</span><span class="sxs-lookup"><span data-stu-id="75c67-133">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="75c67-134">为期</span><span class="sxs-lookup"><span data-stu-id="75c67-134">day</span></span>  <br/> |<span data-ttu-id="75c67-135">xs: string</span><span class="sxs-lookup"><span data-stu-id="75c67-135">xs:string</span></span>  <br/> |<span data-ttu-id="75c67-136">必需</span><span class="sxs-lookup"><span data-stu-id="75c67-136">required</span></span>  <br/> |<span data-ttu-id="75c67-137">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="75c67-137">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="75c67-138">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="75c67-138">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="75c67-139">高效</span><span class="sxs-lookup"><span data-stu-id="75c67-139">high</span></span>  <br/> |<span data-ttu-id="75c67-140">xs: integer</span><span class="sxs-lookup"><span data-stu-id="75c67-140">xs:integer</span></span>  <br/> |<span data-ttu-id="75c67-141">必需</span><span class="sxs-lookup"><span data-stu-id="75c67-141">required</span></span>  <br/> |<span data-ttu-id="75c67-142">指定预测的最高温度。</span><span class="sxs-lookup"><span data-stu-id="75c67-142">Specifies the forecasted highest temperature.</span></span>  <br/> |<span data-ttu-id="75c67-143">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="75c67-143">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="75c67-144">降低</span><span class="sxs-lookup"><span data-stu-id="75c67-144">low</span></span>  <br/> |<span data-ttu-id="75c67-145">xs: integer</span><span class="sxs-lookup"><span data-stu-id="75c67-145">xs:integer</span></span>  <br/> |<span data-ttu-id="75c67-146">必需</span><span class="sxs-lookup"><span data-stu-id="75c67-146">required</span></span>  <br/> |<span data-ttu-id="75c67-147">指定预测的最低温度。</span><span class="sxs-lookup"><span data-stu-id="75c67-147">Specifies the forecasted lowest temperature.</span></span>  <br/> |<span data-ttu-id="75c67-148">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="75c67-148">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="75c67-149">precip</span><span class="sxs-lookup"><span data-stu-id="75c67-149">precip</span></span>  <br/> |<span data-ttu-id="75c67-150">xs: integer</span><span class="sxs-lookup"><span data-stu-id="75c67-150">xs:integer</span></span>  <br/> |<span data-ttu-id="75c67-151">必需</span><span class="sxs-lookup"><span data-stu-id="75c67-151">required</span></span>  <br/> |<span data-ttu-id="75c67-152">指定 precipitation 的百分比可能性。</span><span class="sxs-lookup"><span data-stu-id="75c67-152">Specifies the percentage possibility of precipitation.</span></span>  <br/> |<span data-ttu-id="75c67-153">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="75c67-153">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="75c67-154">shortday</span><span class="sxs-lookup"><span data-stu-id="75c67-154">shortday</span></span>  <br/> |<span data-ttu-id="75c67-155">xs: string</span><span class="sxs-lookup"><span data-stu-id="75c67-155">xs:string</span></span>  <br/> |<span data-ttu-id="75c67-156">必需</span><span class="sxs-lookup"><span data-stu-id="75c67-156">required</span></span>  <br/> |<span data-ttu-id="75c67-157">指定缩写形式的日期。</span><span class="sxs-lookup"><span data-stu-id="75c67-157">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="75c67-158">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="75c67-158">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="75c67-159">skycodeday</span><span class="sxs-lookup"><span data-stu-id="75c67-159">skycodeday</span></span>  <br/> |<span data-ttu-id="75c67-160">xs: integer</span><span class="sxs-lookup"><span data-stu-id="75c67-160">xs:integer</span></span>  <br/> |<span data-ttu-id="75c67-161">必需</span><span class="sxs-lookup"><span data-stu-id="75c67-161">required</span></span>  <br/> |<span data-ttu-id="75c67-162">指定预测条件的代码。</span><span class="sxs-lookup"><span data-stu-id="75c67-162">Specifies a code for the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="75c67-163">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="75c67-163">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="75c67-164">skytextday</span><span class="sxs-lookup"><span data-stu-id="75c67-164">skytextday</span></span>  <br/> |<span data-ttu-id="75c67-165">xs: string</span><span class="sxs-lookup"><span data-stu-id="75c67-165">xs:string</span></span>  <br/> |<span data-ttu-id="75c67-166">必需</span><span class="sxs-lookup"><span data-stu-id="75c67-166">required</span></span>  <br/> |<span data-ttu-id="75c67-167">指定一到两个描述预测条件的词。</span><span class="sxs-lookup"><span data-stu-id="75c67-167">Specifies one to two words that describe the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="75c67-168">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="75c67-168">A value of the type xs:string</span></span>  <br/> |
   

