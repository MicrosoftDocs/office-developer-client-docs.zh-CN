---
title: 预测元素 （weatherType 复杂类型） （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9124fa30-d58b-8354-91e9-8d2237a8251d
description: 指定至少三天提前包括今天的未来的天气条件： 今天，明天，天 after 明天。
ms.openlocfilehash: c618b753ddf8a72fce270800675982f1a7f7af5b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779343"
---
# <a name="forecast-element-weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="e29be-103">预测元素 （weatherType 复杂类型） （Outlook 天气信息架构）</span><span class="sxs-lookup"><span data-stu-id="e29be-103">forecast element (weatherType complexType) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="e29be-104">指定至少三天提前包括今天的未来的天气条件： 今天，明天，天 after 明天。</span><span class="sxs-lookup"><span data-stu-id="e29be-104">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="e29be-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e29be-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e29be-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e29be-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e29be-107">forecastType</span><span class="sxs-lookup"><span data-stu-id="e29be-107">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="e29be-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e29be-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="e29be-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e29be-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e29be-110">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="e29be-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e29be-111">定义</span><span class="sxs-lookup"><span data-stu-id="e29be-111">Definition</span></span>

```XML
<xs:element name="forecast"      type="forecastType" minOccurs="3"     maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="e29be-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e29be-112">Elements and attributes</span></span>

<span data-ttu-id="e29be-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="e29be-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e29be-114">父元素</span><span class="sxs-lookup"><span data-stu-id="e29be-114">Parent elements</span></span>

|<span data-ttu-id="e29be-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="e29be-115">**Element**</span></span>|<span data-ttu-id="e29be-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="e29be-116">**Type**</span></span>|<span data-ttu-id="e29be-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="e29be-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e29be-118">天气</span><span class="sxs-lookup"><span data-stu-id="e29be-118">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="e29be-119">weatherType</span><span class="sxs-lookup"><span data-stu-id="e29be-119">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="e29be-120">指定一个位置的天气条件。</span><span class="sxs-lookup"><span data-stu-id="e29be-120">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e29be-121">子元素</span><span class="sxs-lookup"><span data-stu-id="e29be-121">Child elements</span></span>

<span data-ttu-id="e29be-122">无。</span><span class="sxs-lookup"><span data-stu-id="e29be-122">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="e29be-123">属性</span><span class="sxs-lookup"><span data-stu-id="e29be-123">Attributes</span></span>

|<span data-ttu-id="e29be-124">**属性**</span><span class="sxs-lookup"><span data-stu-id="e29be-124">**Attribute**</span></span>|<span data-ttu-id="e29be-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="e29be-125">**Type**</span></span>|<span data-ttu-id="e29be-126">**必需**</span><span class="sxs-lookup"><span data-stu-id="e29be-126">**Required**</span></span>|<span data-ttu-id="e29be-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="e29be-127">**Description**</span></span>|<span data-ttu-id="e29be-128">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e29be-128">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e29be-129">date</span><span class="sxs-lookup"><span data-stu-id="e29be-129">date</span></span>  <br/> |<span data-ttu-id="e29be-130">xs: date</span><span class="sxs-lookup"><span data-stu-id="e29be-130">xs:date</span></span>  <br/> |<span data-ttu-id="e29be-131">必需</span><span class="sxs-lookup"><span data-stu-id="e29be-131">required</span></span>  <br/> |<span data-ttu-id="e29be-132">指定为预测的日期。</span><span class="sxs-lookup"><span data-stu-id="e29be-132">Specifies the date for the forecast.</span></span>  <br/> |<span data-ttu-id="e29be-133">值为类型 xs: date</span><span class="sxs-lookup"><span data-stu-id="e29be-133">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="e29be-134">一天</span><span class="sxs-lookup"><span data-stu-id="e29be-134">day</span></span>  <br/> |<span data-ttu-id="e29be-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="e29be-135">xs:string</span></span>  <br/> |<span data-ttu-id="e29be-136">必需</span><span class="sxs-lookup"><span data-stu-id="e29be-136">required</span></span>  <br/> |<span data-ttu-id="e29be-137">指定为预测一天。</span><span class="sxs-lookup"><span data-stu-id="e29be-137">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="e29be-138">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="e29be-138">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="e29be-139">高</span><span class="sxs-lookup"><span data-stu-id="e29be-139">high</span></span>  <br/> |<span data-ttu-id="e29be-140">xs:integer</span><span class="sxs-lookup"><span data-stu-id="e29be-140">xs:integer</span></span>  <br/> |<span data-ttu-id="e29be-141">必需</span><span class="sxs-lookup"><span data-stu-id="e29be-141">required</span></span>  <br/> |<span data-ttu-id="e29be-142">指定的预测的最高温度。</span><span class="sxs-lookup"><span data-stu-id="e29be-142">Specifies the forecasted highest temperature.</span></span>  <br/> |<span data-ttu-id="e29be-143">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="e29be-143">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="e29be-144">低</span><span class="sxs-lookup"><span data-stu-id="e29be-144">low</span></span>  <br/> |<span data-ttu-id="e29be-145">xs:integer</span><span class="sxs-lookup"><span data-stu-id="e29be-145">xs:integer</span></span>  <br/> |<span data-ttu-id="e29be-146">必需</span><span class="sxs-lookup"><span data-stu-id="e29be-146">required</span></span>  <br/> |<span data-ttu-id="e29be-147">指定的预测的最低温度。</span><span class="sxs-lookup"><span data-stu-id="e29be-147">Specifies the forecasted lowest temperature.</span></span>  <br/> |<span data-ttu-id="e29be-148">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="e29be-148">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="e29be-149">precip</span><span class="sxs-lookup"><span data-stu-id="e29be-149">precip</span></span>  <br/> |<span data-ttu-id="e29be-150">xs:integer</span><span class="sxs-lookup"><span data-stu-id="e29be-150">xs:integer</span></span>  <br/> |<span data-ttu-id="e29be-151">必需</span><span class="sxs-lookup"><span data-stu-id="e29be-151">required</span></span>  <br/> |<span data-ttu-id="e29be-152">指定雨百分比的可能性。</span><span class="sxs-lookup"><span data-stu-id="e29be-152">Specifies the percentage possibility of precipitation.</span></span>  <br/> |<span data-ttu-id="e29be-153">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="e29be-153">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="e29be-154">shortday</span><span class="sxs-lookup"><span data-stu-id="e29be-154">shortday</span></span>  <br/> |<span data-ttu-id="e29be-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="e29be-155">xs:string</span></span>  <br/> |<span data-ttu-id="e29be-156">必需</span><span class="sxs-lookup"><span data-stu-id="e29be-156">required</span></span>  <br/> |<span data-ttu-id="e29be-157">缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="e29be-157">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="e29be-158">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="e29be-158">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="e29be-159">skycodeday</span><span class="sxs-lookup"><span data-stu-id="e29be-159">skycodeday</span></span>  <br/> |<span data-ttu-id="e29be-160">xs:integer</span><span class="sxs-lookup"><span data-stu-id="e29be-160">xs:integer</span></span>  <br/> |<span data-ttu-id="e29be-161">必需</span><span class="sxs-lookup"><span data-stu-id="e29be-161">required</span></span>  <br/> |<span data-ttu-id="e29be-162">指定的预测的条件的代码。</span><span class="sxs-lookup"><span data-stu-id="e29be-162">Specifies a code for the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="e29be-163">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="e29be-163">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="e29be-164">skytextday</span><span class="sxs-lookup"><span data-stu-id="e29be-164">skytextday</span></span>  <br/> |<span data-ttu-id="e29be-165">xs:string</span><span class="sxs-lookup"><span data-stu-id="e29be-165">xs:string</span></span>  <br/> |<span data-ttu-id="e29be-166">必需</span><span class="sxs-lookup"><span data-stu-id="e29be-166">required</span></span>  <br/> |<span data-ttu-id="e29be-167">指定一到两个单词的描述的预测的条件。</span><span class="sxs-lookup"><span data-stu-id="e29be-167">Specifies one to two words that describe the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="e29be-168">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="e29be-168">A value of the type xs:string</span></span>  <br/> |
   

