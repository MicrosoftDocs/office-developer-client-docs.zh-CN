---
title: current 元素 (weatherType 复杂类型) (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d592a396-f935-c44c-409f-b849c327cfbd
description: 指定当前天气情况。
ms.openlocfilehash: 1303212da1336112599ae5328498cca0d4ab5f89
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541006"
---
# <a name="current-element-weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="96a86-103">current 元素 (weatherType 复杂类型) (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="96a86-103">current element (weatherType complexType) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="96a86-104">指定当前天气情况。</span><span class="sxs-lookup"><span data-stu-id="96a86-104">Specifies the current weather conditions.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="96a86-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="96a86-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="96a86-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="96a86-106">**Element type**</span></span> <br/> |[<span data-ttu-id="96a86-107">currentType</span><span class="sxs-lookup"><span data-stu-id="96a86-107">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="96a86-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="96a86-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="96a86-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="96a86-109">**Schema file**</span></span> <br/> |<span data-ttu-id="96a86-110">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="96a86-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="96a86-111">定义</span><span class="sxs-lookup"><span data-stu-id="96a86-111">Definition</span></span>

```XML
<xs:element name="current"      type="currentType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="96a86-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="96a86-112">Elements and attributes</span></span>

<span data-ttu-id="96a86-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="96a86-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="96a86-114">父元素</span><span class="sxs-lookup"><span data-stu-id="96a86-114">Parent elements</span></span>

|<span data-ttu-id="96a86-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="96a86-115">**Element**</span></span>|<span data-ttu-id="96a86-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="96a86-116">**Type**</span></span>|<span data-ttu-id="96a86-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="96a86-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="96a86-118">气候</span><span class="sxs-lookup"><span data-stu-id="96a86-118">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="96a86-119">weatherType</span><span class="sxs-lookup"><span data-stu-id="96a86-119">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="96a86-120">指定位置的天气情况。</span><span class="sxs-lookup"><span data-stu-id="96a86-120">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="96a86-121">子元素</span><span class="sxs-lookup"><span data-stu-id="96a86-121">Child elements</span></span>

<span data-ttu-id="96a86-122">无。</span><span class="sxs-lookup"><span data-stu-id="96a86-122">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="96a86-123">属性</span><span class="sxs-lookup"><span data-stu-id="96a86-123">Attributes</span></span>

|<span data-ttu-id="96a86-124">**属性**</span><span class="sxs-lookup"><span data-stu-id="96a86-124">**Attribute**</span></span>|<span data-ttu-id="96a86-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="96a86-125">**Type**</span></span>|<span data-ttu-id="96a86-126">**必需**</span><span class="sxs-lookup"><span data-stu-id="96a86-126">**Required**</span></span>|<span data-ttu-id="96a86-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="96a86-127">**Description**</span></span>|<span data-ttu-id="96a86-128">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="96a86-128">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96a86-129">date</span><span class="sxs-lookup"><span data-stu-id="96a86-129">date</span></span>  <br/> |<span data-ttu-id="96a86-130">xs: date</span><span class="sxs-lookup"><span data-stu-id="96a86-130">xs:date</span></span>  <br/> |<span data-ttu-id="96a86-131">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-131">required</span></span>  <br/> |<span data-ttu-id="96a86-132">指定今天的日期。</span><span class="sxs-lookup"><span data-stu-id="96a86-132">Specifies today's date.</span></span>  <br/> |<span data-ttu-id="96a86-133">类型 xs: date 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-133">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="96a86-134">为期</span><span class="sxs-lookup"><span data-stu-id="96a86-134">day</span></span>  <br/> |<span data-ttu-id="96a86-135">xs: string</span><span class="sxs-lookup"><span data-stu-id="96a86-135">xs:string</span></span>  <br/> |<span data-ttu-id="96a86-136">可选</span><span class="sxs-lookup"><span data-stu-id="96a86-136">optional</span></span>  <br/> |<span data-ttu-id="96a86-137">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="96a86-137">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="96a86-138">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-138">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="96a86-139">feelslike</span><span class="sxs-lookup"><span data-stu-id="96a86-139">feelslike</span></span>  <br/> |<span data-ttu-id="96a86-140">xs: integer</span><span class="sxs-lookup"><span data-stu-id="96a86-140">xs:integer</span></span>  <br/> |<span data-ttu-id="96a86-141">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-141">required</span></span>  <br/> |<span data-ttu-id="96a86-142">指定当前天气的外观的温度。</span><span class="sxs-lookup"><span data-stu-id="96a86-142">Specifies the temperature of how the current weather feels like.</span></span>  <br/> |<span data-ttu-id="96a86-143">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-143">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="96a86-144">湿度</span><span class="sxs-lookup"><span data-stu-id="96a86-144">humidity</span></span>  <br/> |<span data-ttu-id="96a86-145">xs: integer</span><span class="sxs-lookup"><span data-stu-id="96a86-145">xs:integer</span></span>  <br/> |<span data-ttu-id="96a86-146">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-146">required</span></span>  <br/> |<span data-ttu-id="96a86-147">指定当前的数值湿度值。</span><span class="sxs-lookup"><span data-stu-id="96a86-147">Specifies the current numerical humidity value.</span></span>  <br/> |<span data-ttu-id="96a86-148">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-148">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="96a86-149">observationpoint</span><span class="sxs-lookup"><span data-stu-id="96a86-149">observationpoint</span></span>  <br/> |<span data-ttu-id="96a86-150">xs: string</span><span class="sxs-lookup"><span data-stu-id="96a86-150">xs:string</span></span>  <br/> |<span data-ttu-id="96a86-151">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-151">required</span></span>  <br/> |<span data-ttu-id="96a86-152">指定观察当前天气信息的位置。</span><span class="sxs-lookup"><span data-stu-id="96a86-152">Specifies where the current weather information is observed from.</span></span>  <br/> |<span data-ttu-id="96a86-153">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-153">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="96a86-154">observationtime</span><span class="sxs-lookup"><span data-stu-id="96a86-154">observationtime</span></span>  <br/> |<span data-ttu-id="96a86-155">xs: time</span><span class="sxs-lookup"><span data-stu-id="96a86-155">xs:time</span></span>  <br/> |<span data-ttu-id="96a86-156">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-156">required</span></span>  <br/> |<span data-ttu-id="96a86-157">指定何时在中观察当前天气信息。</span><span class="sxs-lookup"><span data-stu-id="96a86-157">Specifies when the current weather information is observed at.</span></span>  <br/> |<span data-ttu-id="96a86-158">类型 xs: time 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-158">A value of the type xs:time</span></span>  <br/> |
|<span data-ttu-id="96a86-159">shortday</span><span class="sxs-lookup"><span data-stu-id="96a86-159">shortday</span></span>  <br/> |<span data-ttu-id="96a86-160">xs: string</span><span class="sxs-lookup"><span data-stu-id="96a86-160">xs:string</span></span>  <br/> |<span data-ttu-id="96a86-161">可选</span><span class="sxs-lookup"><span data-stu-id="96a86-161">optional</span></span>  <br/> |<span data-ttu-id="96a86-162">指定缩写形式的日期。</span><span class="sxs-lookup"><span data-stu-id="96a86-162">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="96a86-163">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-163">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="96a86-164">skycode</span><span class="sxs-lookup"><span data-stu-id="96a86-164">skycode</span></span>  <br/> |<span data-ttu-id="96a86-165">xs: integer</span><span class="sxs-lookup"><span data-stu-id="96a86-165">xs:integer</span></span>  <br/> |<span data-ttu-id="96a86-166">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-166">required</span></span>  <br/> |<span data-ttu-id="96a86-167">指定当前天气条件的整数代码。</span><span class="sxs-lookup"><span data-stu-id="96a86-167">Specifies an integer code for the current weather conditions.</span></span>  <br/> |<span data-ttu-id="96a86-168">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-168">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="96a86-169">skytext</span><span class="sxs-lookup"><span data-stu-id="96a86-169">skytext</span></span>  <br/> |<span data-ttu-id="96a86-170">xs: string</span><span class="sxs-lookup"><span data-stu-id="96a86-170">xs:string</span></span>  <br/> |<span data-ttu-id="96a86-171">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-171">required</span></span>  <br/> |<span data-ttu-id="96a86-172">指定一个描述当前天气情况的两个字。</span><span class="sxs-lookup"><span data-stu-id="96a86-172">Specifies one to two words describing current weather conditions.</span></span>  <br/> |<span data-ttu-id="96a86-173">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-173">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="96a86-174">量</span><span class="sxs-lookup"><span data-stu-id="96a86-174">temperature</span></span>  <br/> |<span data-ttu-id="96a86-175">xs: integer</span><span class="sxs-lookup"><span data-stu-id="96a86-175">xs:integer</span></span>  <br/> |<span data-ttu-id="96a86-176">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-176">required</span></span>  <br/> |<span data-ttu-id="96a86-177">指定位置的当前温度。</span><span class="sxs-lookup"><span data-stu-id="96a86-177">Specifies the current temperature of the location.</span></span>  <br/> |<span data-ttu-id="96a86-178">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-178">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="96a86-179">winddisplay</span><span class="sxs-lookup"><span data-stu-id="96a86-179">winddisplay</span></span>  <br/> |<span data-ttu-id="96a86-180">xs: string</span><span class="sxs-lookup"><span data-stu-id="96a86-180">xs:string</span></span>  <br/> |<span data-ttu-id="96a86-181">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-181">required</span></span>  <br/> |<span data-ttu-id="96a86-182">一个描述当前风条件的字符串。</span><span class="sxs-lookup"><span data-stu-id="96a86-182">A string that describes the current wind conditions.</span></span>  <br/> |<span data-ttu-id="96a86-183">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-183">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="96a86-184">windspeed</span><span class="sxs-lookup"><span data-stu-id="96a86-184">windspeed</span></span>  <br/> |<span data-ttu-id="96a86-185">xs: integer</span><span class="sxs-lookup"><span data-stu-id="96a86-185">xs:integer</span></span>  <br/> |<span data-ttu-id="96a86-186">必需</span><span class="sxs-lookup"><span data-stu-id="96a86-186">required</span></span>  <br/> |<span data-ttu-id="96a86-187">指定当前的数值风速度值。</span><span class="sxs-lookup"><span data-stu-id="96a86-187">Specifies the current numerical wind speed value.</span></span>  <br/> |<span data-ttu-id="96a86-188">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="96a86-188">A value of the type xs:integer</span></span>  <br/> |
   

