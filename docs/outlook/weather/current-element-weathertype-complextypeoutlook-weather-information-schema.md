---
title: 'current 元素 (weatherType complexType)  (Outlook Weather Information Schema) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d592a396-f935-c44c-409f-b849c327cfbd
description: 指定当前天气状况。
ms.openlocfilehash: 1303212da1336112599ae5328498cca0d4ab5f89
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541006"
---
# <a name="current-element-weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="2c986-103">current 元素 (weatherType complexType)  (Outlook Weather Information Schema) </span><span class="sxs-lookup"><span data-stu-id="2c986-103">current element (weatherType complexType) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="2c986-104">指定当前天气状况。</span><span class="sxs-lookup"><span data-stu-id="2c986-104">Specifies the current weather conditions.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2c986-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="2c986-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2c986-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2c986-106">**Element type**</span></span> <br/> |[<span data-ttu-id="2c986-107">currentType</span><span class="sxs-lookup"><span data-stu-id="2c986-107">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="2c986-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2c986-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="2c986-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2c986-109">**Schema file**</span></span> <br/> |<span data-ttu-id="2c986-110">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="2c986-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2c986-111">定义</span><span class="sxs-lookup"><span data-stu-id="2c986-111">Definition</span></span>

```XML
<xs:element name="current"      type="currentType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="2c986-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2c986-112">Elements and attributes</span></span>

<span data-ttu-id="2c986-113">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2c986-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="2c986-114">父元素</span><span class="sxs-lookup"><span data-stu-id="2c986-114">Parent elements</span></span>

|<span data-ttu-id="2c986-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="2c986-115">**Element**</span></span>|<span data-ttu-id="2c986-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="2c986-116">**Type**</span></span>|<span data-ttu-id="2c986-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c986-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2c986-118">weather</span><span class="sxs-lookup"><span data-stu-id="2c986-118">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="2c986-119">weatherType</span><span class="sxs-lookup"><span data-stu-id="2c986-119">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="2c986-120">指定位置的天气状况。</span><span class="sxs-lookup"><span data-stu-id="2c986-120">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="2c986-121">子元素</span><span class="sxs-lookup"><span data-stu-id="2c986-121">Child elements</span></span>

<span data-ttu-id="2c986-122">无。</span><span class="sxs-lookup"><span data-stu-id="2c986-122">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2c986-123">属性</span><span class="sxs-lookup"><span data-stu-id="2c986-123">Attributes</span></span>

|<span data-ttu-id="2c986-124">**属性**</span><span class="sxs-lookup"><span data-stu-id="2c986-124">**Attribute**</span></span>|<span data-ttu-id="2c986-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="2c986-125">**Type**</span></span>|<span data-ttu-id="2c986-126">**必需**</span><span class="sxs-lookup"><span data-stu-id="2c986-126">**Required**</span></span>|<span data-ttu-id="2c986-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="2c986-127">**Description**</span></span>|<span data-ttu-id="2c986-128">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2c986-128">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c986-129">date</span><span class="sxs-lookup"><span data-stu-id="2c986-129">date</span></span>  <br/> |<span data-ttu-id="2c986-130">xs：date</span><span class="sxs-lookup"><span data-stu-id="2c986-130">xs:date</span></span>  <br/> |<span data-ttu-id="2c986-131">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-131">required</span></span>  <br/> |<span data-ttu-id="2c986-132">指定今天的日期。</span><span class="sxs-lookup"><span data-stu-id="2c986-132">Specifies today's date.</span></span>  <br/> |<span data-ttu-id="2c986-133">xs：date 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-133">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="2c986-134">day</span><span class="sxs-lookup"><span data-stu-id="2c986-134">day</span></span>  <br/> |<span data-ttu-id="2c986-135">xs：string</span><span class="sxs-lookup"><span data-stu-id="2c986-135">xs:string</span></span>  <br/> |<span data-ttu-id="2c986-136">可选</span><span class="sxs-lookup"><span data-stu-id="2c986-136">optional</span></span>  <br/> |<span data-ttu-id="2c986-137">指定预测的一天。</span><span class="sxs-lookup"><span data-stu-id="2c986-137">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="2c986-138">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-138">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c986-139">感觉相似</span><span class="sxs-lookup"><span data-stu-id="2c986-139">feelslike</span></span>  <br/> |<span data-ttu-id="2c986-140">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2c986-140">xs:integer</span></span>  <br/> |<span data-ttu-id="2c986-141">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-141">required</span></span>  <br/> |<span data-ttu-id="2c986-142">指定当前天气的温度。</span><span class="sxs-lookup"><span data-stu-id="2c986-142">Specifies the temperature of how the current weather feels like.</span></span>  <br/> |<span data-ttu-id="2c986-143">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-143">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="2c986-144">一些</span><span class="sxs-lookup"><span data-stu-id="2c986-144">humidity</span></span>  <br/> |<span data-ttu-id="2c986-145">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2c986-145">xs:integer</span></span>  <br/> |<span data-ttu-id="2c986-146">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-146">required</span></span>  <br/> |<span data-ttu-id="2c986-147">指定当前的数值数值。</span><span class="sxs-lookup"><span data-stu-id="2c986-147">Specifies the current numerical humidity value.</span></span>  <br/> |<span data-ttu-id="2c986-148">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-148">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="2c986-149">观察点</span><span class="sxs-lookup"><span data-stu-id="2c986-149">observationpoint</span></span>  <br/> |<span data-ttu-id="2c986-150">xs：string</span><span class="sxs-lookup"><span data-stu-id="2c986-150">xs:string</span></span>  <br/> |<span data-ttu-id="2c986-151">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-151">required</span></span>  <br/> |<span data-ttu-id="2c986-152">指定从何处观测当前天气信息。</span><span class="sxs-lookup"><span data-stu-id="2c986-152">Specifies where the current weather information is observed from.</span></span>  <br/> |<span data-ttu-id="2c986-153">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-153">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c986-154">观察时间</span><span class="sxs-lookup"><span data-stu-id="2c986-154">observationtime</span></span>  <br/> |<span data-ttu-id="2c986-155">xs：time</span><span class="sxs-lookup"><span data-stu-id="2c986-155">xs:time</span></span>  <br/> |<span data-ttu-id="2c986-156">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-156">required</span></span>  <br/> |<span data-ttu-id="2c986-157">指定何时观测到当前天气信息。</span><span class="sxs-lookup"><span data-stu-id="2c986-157">Specifies when the current weather information is observed at.</span></span>  <br/> |<span data-ttu-id="2c986-158">xs：time 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-158">A value of the type xs:time</span></span>  <br/> |
|<span data-ttu-id="2c986-159">shortday</span><span class="sxs-lookup"><span data-stu-id="2c986-159">shortday</span></span>  <br/> |<span data-ttu-id="2c986-160">xs：string</span><span class="sxs-lookup"><span data-stu-id="2c986-160">xs:string</span></span>  <br/> |<span data-ttu-id="2c986-161">可选</span><span class="sxs-lookup"><span data-stu-id="2c986-161">optional</span></span>  <br/> |<span data-ttu-id="2c986-162">以缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="2c986-162">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="2c986-163">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-163">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c986-164">skycode</span><span class="sxs-lookup"><span data-stu-id="2c986-164">skycode</span></span>  <br/> |<span data-ttu-id="2c986-165">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2c986-165">xs:integer</span></span>  <br/> |<span data-ttu-id="2c986-166">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-166">required</span></span>  <br/> |<span data-ttu-id="2c986-167">指定当前天气条件的整数代码。</span><span class="sxs-lookup"><span data-stu-id="2c986-167">Specifies an integer code for the current weather conditions.</span></span>  <br/> |<span data-ttu-id="2c986-168">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-168">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="2c986-169">skytext</span><span class="sxs-lookup"><span data-stu-id="2c986-169">skytext</span></span>  <br/> |<span data-ttu-id="2c986-170">xs：string</span><span class="sxs-lookup"><span data-stu-id="2c986-170">xs:string</span></span>  <br/> |<span data-ttu-id="2c986-171">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-171">required</span></span>  <br/> |<span data-ttu-id="2c986-172">指定描述当前天气条件的一到两个单词。</span><span class="sxs-lookup"><span data-stu-id="2c986-172">Specifies one to two words describing current weather conditions.</span></span>  <br/> |<span data-ttu-id="2c986-173">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-173">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c986-174">temperature</span><span class="sxs-lookup"><span data-stu-id="2c986-174">temperature</span></span>  <br/> |<span data-ttu-id="2c986-175">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2c986-175">xs:integer</span></span>  <br/> |<span data-ttu-id="2c986-176">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-176">required</span></span>  <br/> |<span data-ttu-id="2c986-177">指定位置的当前温度。</span><span class="sxs-lookup"><span data-stu-id="2c986-177">Specifies the current temperature of the location.</span></span>  <br/> |<span data-ttu-id="2c986-178">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-178">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="2c986-179">winddisplay</span><span class="sxs-lookup"><span data-stu-id="2c986-179">winddisplay</span></span>  <br/> |<span data-ttu-id="2c986-180">xs：string</span><span class="sxs-lookup"><span data-stu-id="2c986-180">xs:string</span></span>  <br/> |<span data-ttu-id="2c986-181">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-181">required</span></span>  <br/> |<span data-ttu-id="2c986-182">一个描述当前温度条件的字符串。</span><span class="sxs-lookup"><span data-stu-id="2c986-182">A string that describes the current wind conditions.</span></span>  <br/> |<span data-ttu-id="2c986-183">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-183">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="2c986-184">将</span><span class="sxs-lookup"><span data-stu-id="2c986-184">windspeed</span></span>  <br/> |<span data-ttu-id="2c986-185">xs：integer</span><span class="sxs-lookup"><span data-stu-id="2c986-185">xs:integer</span></span>  <br/> |<span data-ttu-id="2c986-186">必需</span><span class="sxs-lookup"><span data-stu-id="2c986-186">required</span></span>  <br/> |<span data-ttu-id="2c986-187">指定当前数值的时速值。</span><span class="sxs-lookup"><span data-stu-id="2c986-187">Specifies the current numerical wind speed value.</span></span>  <br/> |<span data-ttu-id="2c986-188">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="2c986-188">A value of the type xs:integer</span></span>  <br/> |
   

