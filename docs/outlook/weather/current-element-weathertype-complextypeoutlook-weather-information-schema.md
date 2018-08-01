---
title: 当前元素 （weatherType 复杂类型） （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d592a396-f935-c44c-409f-b849c327cfbd
description: 指定当前的天气条件。
ms.openlocfilehash: 12265c463f0f1bba15c9bf1723cbbea6c505dba9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779336"
---
# <a name="current-element-weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="785ea-103">当前元素 （weatherType 复杂类型） （Outlook 天气信息架构）</span><span class="sxs-lookup"><span data-stu-id="785ea-103">current element (weatherType complexType) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="785ea-104">指定当前的天气条件。</span><span class="sxs-lookup"><span data-stu-id="785ea-104">Specifies the current weather conditions.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="785ea-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="785ea-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="785ea-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="785ea-106">**Element type**</span></span> <br/> |[<span data-ttu-id="785ea-107">currentType</span><span class="sxs-lookup"><span data-stu-id="785ea-107">currentType</span></span>](currenttype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="785ea-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="785ea-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="785ea-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="785ea-109">**Schema file**</span></span> <br/> |<span data-ttu-id="785ea-110">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="785ea-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="785ea-111">定义</span><span class="sxs-lookup"><span data-stu-id="785ea-111">Definition</span></span>

```XML
<xs:element name="current"      type="currentType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="785ea-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="785ea-112">Elements and attributes</span></span>

<span data-ttu-id="785ea-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="785ea-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="785ea-114">父元素</span><span class="sxs-lookup"><span data-stu-id="785ea-114">Parent elements</span></span>

|<span data-ttu-id="785ea-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="785ea-115">**Element**</span></span>|<span data-ttu-id="785ea-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="785ea-116">**Type**</span></span>|<span data-ttu-id="785ea-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="785ea-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="785ea-118">天气</span><span class="sxs-lookup"><span data-stu-id="785ea-118">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="785ea-119">weatherType</span><span class="sxs-lookup"><span data-stu-id="785ea-119">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="785ea-120">指定一个位置的天气条件。</span><span class="sxs-lookup"><span data-stu-id="785ea-120">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="785ea-121">子元素</span><span class="sxs-lookup"><span data-stu-id="785ea-121">Child elements</span></span>

<span data-ttu-id="785ea-122">无。</span><span class="sxs-lookup"><span data-stu-id="785ea-122">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="785ea-123">属性</span><span class="sxs-lookup"><span data-stu-id="785ea-123">Attributes</span></span>

|<span data-ttu-id="785ea-124">**属性**</span><span class="sxs-lookup"><span data-stu-id="785ea-124">**Attribute**</span></span>|<span data-ttu-id="785ea-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="785ea-125">**Type**</span></span>|<span data-ttu-id="785ea-126">**必需**</span><span class="sxs-lookup"><span data-stu-id="785ea-126">**Required**</span></span>|<span data-ttu-id="785ea-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="785ea-127">**Description**</span></span>|<span data-ttu-id="785ea-128">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="785ea-128">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="785ea-129">date</span><span class="sxs-lookup"><span data-stu-id="785ea-129">date</span></span>  <br/> |<span data-ttu-id="785ea-130">xs: date</span><span class="sxs-lookup"><span data-stu-id="785ea-130">xs:date</span></span>  <br/> |<span data-ttu-id="785ea-131">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-131">required</span></span>  <br/> |<span data-ttu-id="785ea-132">指定今天的日期。</span><span class="sxs-lookup"><span data-stu-id="785ea-132">Specifies today's date.</span></span>  <br/> |<span data-ttu-id="785ea-133">值为类型 xs: date</span><span class="sxs-lookup"><span data-stu-id="785ea-133">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="785ea-134">一天</span><span class="sxs-lookup"><span data-stu-id="785ea-134">day</span></span>  <br/> |<span data-ttu-id="785ea-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="785ea-135">xs:string</span></span>  <br/> |<span data-ttu-id="785ea-136">可选</span><span class="sxs-lookup"><span data-stu-id="785ea-136">optional</span></span>  <br/> |<span data-ttu-id="785ea-137">指定为预测一天。</span><span class="sxs-lookup"><span data-stu-id="785ea-137">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="785ea-138">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="785ea-138">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="785ea-139">feelslike</span><span class="sxs-lookup"><span data-stu-id="785ea-139">feelslike</span></span>  <br/> |<span data-ttu-id="785ea-140">xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-140">xs:integer</span></span>  <br/> |<span data-ttu-id="785ea-141">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-141">required</span></span>  <br/> |<span data-ttu-id="785ea-142">指定如何当前天气外观的温度。</span><span class="sxs-lookup"><span data-stu-id="785ea-142">Specifies the temperature of how the current weather feels like.</span></span>  <br/> |<span data-ttu-id="785ea-143">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-143">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="785ea-144">湿度</span><span class="sxs-lookup"><span data-stu-id="785ea-144">humidity</span></span>  <br/> |<span data-ttu-id="785ea-145">xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-145">xs:integer</span></span>  <br/> |<span data-ttu-id="785ea-146">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-146">required</span></span>  <br/> |<span data-ttu-id="785ea-147">指定当前的数字湿度值。</span><span class="sxs-lookup"><span data-stu-id="785ea-147">Specifies the current numerical humidity value.</span></span>  <br/> |<span data-ttu-id="785ea-148">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-148">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="785ea-149">observationpoint</span><span class="sxs-lookup"><span data-stu-id="785ea-149">observationpoint</span></span>  <br/> |<span data-ttu-id="785ea-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="785ea-150">xs:string</span></span>  <br/> |<span data-ttu-id="785ea-151">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-151">required</span></span>  <br/> |<span data-ttu-id="785ea-152">指定从其中观察到当前的天气信息。</span><span class="sxs-lookup"><span data-stu-id="785ea-152">Specifies where the current weather information is observed from.</span></span>  <br/> |<span data-ttu-id="785ea-153">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="785ea-153">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="785ea-154">observationtime</span><span class="sxs-lookup"><span data-stu-id="785ea-154">observationtime</span></span>  <br/> |<span data-ttu-id="785ea-155">xs:time</span><span class="sxs-lookup"><span data-stu-id="785ea-155">xs:time</span></span>  <br/> |<span data-ttu-id="785ea-156">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-156">required</span></span>  <br/> |<span data-ttu-id="785ea-157">指定当在观察到当前的天气信息。</span><span class="sxs-lookup"><span data-stu-id="785ea-157">Specifies when the current weather information is observed at.</span></span>  <br/> |<span data-ttu-id="785ea-158">值为类型 xs:time</span><span class="sxs-lookup"><span data-stu-id="785ea-158">A value of the type xs:time</span></span>  <br/> |
|<span data-ttu-id="785ea-159">shortday</span><span class="sxs-lookup"><span data-stu-id="785ea-159">shortday</span></span>  <br/> |<span data-ttu-id="785ea-160">xs:string</span><span class="sxs-lookup"><span data-stu-id="785ea-160">xs:string</span></span>  <br/> |<span data-ttu-id="785ea-161">可选</span><span class="sxs-lookup"><span data-stu-id="785ea-161">optional</span></span>  <br/> |<span data-ttu-id="785ea-162">缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="785ea-162">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="785ea-163">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="785ea-163">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="785ea-164">skycode</span><span class="sxs-lookup"><span data-stu-id="785ea-164">skycode</span></span>  <br/> |<span data-ttu-id="785ea-165">xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-165">xs:integer</span></span>  <br/> |<span data-ttu-id="785ea-166">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-166">required</span></span>  <br/> |<span data-ttu-id="785ea-167">指定为当前的天气条件整数代码。</span><span class="sxs-lookup"><span data-stu-id="785ea-167">Specifies an integer code for the current weather conditions.</span></span>  <br/> |<span data-ttu-id="785ea-168">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-168">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="785ea-169">skytext</span><span class="sxs-lookup"><span data-stu-id="785ea-169">skytext</span></span>  <br/> |<span data-ttu-id="785ea-170">xs:string</span><span class="sxs-lookup"><span data-stu-id="785ea-170">xs:string</span></span>  <br/> |<span data-ttu-id="785ea-171">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-171">required</span></span>  <br/> |<span data-ttu-id="785ea-172">指定一到两个单词描述当前天气条件。</span><span class="sxs-lookup"><span data-stu-id="785ea-172">Specifies one to two words describing current weather conditions.</span></span>  <br/> |<span data-ttu-id="785ea-173">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="785ea-173">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="785ea-174">温度</span><span class="sxs-lookup"><span data-stu-id="785ea-174">temperature</span></span>  <br/> |<span data-ttu-id="785ea-175">xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-175">xs:integer</span></span>  <br/> |<span data-ttu-id="785ea-176">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-176">required</span></span>  <br/> |<span data-ttu-id="785ea-177">指定当前温度的位置。</span><span class="sxs-lookup"><span data-stu-id="785ea-177">Specifies the current temperature of the location.</span></span>  <br/> |<span data-ttu-id="785ea-178">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-178">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="785ea-179">winddisplay</span><span class="sxs-lookup"><span data-stu-id="785ea-179">winddisplay</span></span>  <br/> |<span data-ttu-id="785ea-180">xs:string</span><span class="sxs-lookup"><span data-stu-id="785ea-180">xs:string</span></span>  <br/> |<span data-ttu-id="785ea-181">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-181">required</span></span>  <br/> |<span data-ttu-id="785ea-182">描述的当前风条件的字符串。</span><span class="sxs-lookup"><span data-stu-id="785ea-182">A string that describes the current wind conditions.</span></span>  <br/> |<span data-ttu-id="785ea-183">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="785ea-183">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="785ea-184">windspeed</span><span class="sxs-lookup"><span data-stu-id="785ea-184">windspeed</span></span>  <br/> |<span data-ttu-id="785ea-185">xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-185">xs:integer</span></span>  <br/> |<span data-ttu-id="785ea-186">必需</span><span class="sxs-lookup"><span data-stu-id="785ea-186">required</span></span>  <br/> |<span data-ttu-id="785ea-187">指定当前数字风速度值。</span><span class="sxs-lookup"><span data-stu-id="785ea-187">Specifies the current numerical wind speed value.</span></span>  <br/> |<span data-ttu-id="785ea-188">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="785ea-188">A value of the type xs:integer</span></span>  <br/> |
   

