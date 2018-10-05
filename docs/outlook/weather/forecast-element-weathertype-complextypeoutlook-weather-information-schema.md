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
ms.openlocfilehash: 01604796d4460cc14005ee00ea6b8f46f04d4742
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398323"
---
# <a name="forecast-element-weathertype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="3a8a9-103">预测元素 （weatherType 复杂类型） （Outlook 天气信息架构）</span><span class="sxs-lookup"><span data-stu-id="3a8a9-103">forecast element (weatherType complexType) (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="3a8a9-104">指定至少三天提前包括今天的未来的天气条件： 今天，明天，天 after 明天。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-104">Specifies the future weather conditions of at least three days ahead including today: Today, Tomorrow, Day after Tomorrow.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="3a8a9-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="3a8a9-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3a8a9-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-106">**Element type**</span></span> <br/> |[<span data-ttu-id="3a8a9-107">forecastType</span><span class="sxs-lookup"><span data-stu-id="3a8a9-107">forecastType</span></span>](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |
|<span data-ttu-id="3a8a9-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="3a8a9-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-109">**Schema file**</span></span> <br/> |<span data-ttu-id="3a8a9-110">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="3a8a9-110">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3a8a9-111">定义</span><span class="sxs-lookup"><span data-stu-id="3a8a9-111">Definition</span></span>

```XML
<xs:element name="forecast"      type="forecastType" minOccurs="3"     maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a><span data-ttu-id="3a8a9-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3a8a9-112">Elements and attributes</span></span>

<span data-ttu-id="3a8a9-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="3a8a9-114">父元素</span><span class="sxs-lookup"><span data-stu-id="3a8a9-114">Parent elements</span></span>

|<span data-ttu-id="3a8a9-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-115">**Element**</span></span>|<span data-ttu-id="3a8a9-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-116">**Type**</span></span>|<span data-ttu-id="3a8a9-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-117">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3a8a9-118">天气</span><span class="sxs-lookup"><span data-stu-id="3a8a9-118">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="3a8a9-119">weatherType</span><span class="sxs-lookup"><span data-stu-id="3a8a9-119">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="3a8a9-120">指定一个位置的天气条件。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-120">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="3a8a9-121">子元素</span><span class="sxs-lookup"><span data-stu-id="3a8a9-121">Child elements</span></span>

<span data-ttu-id="3a8a9-122">无。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-122">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3a8a9-123">属性</span><span class="sxs-lookup"><span data-stu-id="3a8a9-123">Attributes</span></span>

|<span data-ttu-id="3a8a9-124">**属性**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-124">**Attribute**</span></span>|<span data-ttu-id="3a8a9-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-125">**Type**</span></span>|<span data-ttu-id="3a8a9-126">**必需**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-126">**Required**</span></span>|<span data-ttu-id="3a8a9-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-127">**Description**</span></span>|<span data-ttu-id="3a8a9-128">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-128">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3a8a9-129">date</span><span class="sxs-lookup"><span data-stu-id="3a8a9-129">date</span></span>  <br/> |<span data-ttu-id="3a8a9-130">xs: date</span><span class="sxs-lookup"><span data-stu-id="3a8a9-130">xs:date</span></span>  <br/> |<span data-ttu-id="3a8a9-131">必需</span><span class="sxs-lookup"><span data-stu-id="3a8a9-131">required</span></span>  <br/> |<span data-ttu-id="3a8a9-132">指定为预测的日期。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-132">Specifies the date for the forecast.</span></span>  <br/> |<span data-ttu-id="3a8a9-133">值为类型 xs: date</span><span class="sxs-lookup"><span data-stu-id="3a8a9-133">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="3a8a9-134">一天</span><span class="sxs-lookup"><span data-stu-id="3a8a9-134">day</span></span>  <br/> |<span data-ttu-id="3a8a9-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a8a9-135">xs:string</span></span>  <br/> |<span data-ttu-id="3a8a9-136">必需</span><span class="sxs-lookup"><span data-stu-id="3a8a9-136">required</span></span>  <br/> |<span data-ttu-id="3a8a9-137">指定为预测一天。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-137">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="3a8a9-138">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="3a8a9-138">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="3a8a9-139">高</span><span class="sxs-lookup"><span data-stu-id="3a8a9-139">high</span></span>  <br/> |<span data-ttu-id="3a8a9-140">xs:integer</span><span class="sxs-lookup"><span data-stu-id="3a8a9-140">xs:integer</span></span>  <br/> |<span data-ttu-id="3a8a9-141">必需</span><span class="sxs-lookup"><span data-stu-id="3a8a9-141">required</span></span>  <br/> |<span data-ttu-id="3a8a9-142">指定的预测的最高温度。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-142">Specifies the forecasted highest temperature.</span></span>  <br/> |<span data-ttu-id="3a8a9-143">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="3a8a9-143">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="3a8a9-144">低</span><span class="sxs-lookup"><span data-stu-id="3a8a9-144">low</span></span>  <br/> |<span data-ttu-id="3a8a9-145">xs:integer</span><span class="sxs-lookup"><span data-stu-id="3a8a9-145">xs:integer</span></span>  <br/> |<span data-ttu-id="3a8a9-146">必需</span><span class="sxs-lookup"><span data-stu-id="3a8a9-146">required</span></span>  <br/> |<span data-ttu-id="3a8a9-147">指定的预测的最低温度。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-147">Specifies the forecasted lowest temperature.</span></span>  <br/> |<span data-ttu-id="3a8a9-148">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="3a8a9-148">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="3a8a9-149">precip</span><span class="sxs-lookup"><span data-stu-id="3a8a9-149">precip</span></span>  <br/> |<span data-ttu-id="3a8a9-150">xs:integer</span><span class="sxs-lookup"><span data-stu-id="3a8a9-150">xs:integer</span></span>  <br/> |<span data-ttu-id="3a8a9-151">必需</span><span class="sxs-lookup"><span data-stu-id="3a8a9-151">required</span></span>  <br/> |<span data-ttu-id="3a8a9-152">指定雨百分比的可能性。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-152">Specifies the percentage possibility of precipitation.</span></span>  <br/> |<span data-ttu-id="3a8a9-153">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="3a8a9-153">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="3a8a9-154">shortday</span><span class="sxs-lookup"><span data-stu-id="3a8a9-154">shortday</span></span>  <br/> |<span data-ttu-id="3a8a9-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a8a9-155">xs:string</span></span>  <br/> |<span data-ttu-id="3a8a9-156">必需</span><span class="sxs-lookup"><span data-stu-id="3a8a9-156">required</span></span>  <br/> |<span data-ttu-id="3a8a9-157">缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-157">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="3a8a9-158">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="3a8a9-158">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="3a8a9-159">skycodeday</span><span class="sxs-lookup"><span data-stu-id="3a8a9-159">skycodeday</span></span>  <br/> |<span data-ttu-id="3a8a9-160">xs:integer</span><span class="sxs-lookup"><span data-stu-id="3a8a9-160">xs:integer</span></span>  <br/> |<span data-ttu-id="3a8a9-161">必需</span><span class="sxs-lookup"><span data-stu-id="3a8a9-161">required</span></span>  <br/> |<span data-ttu-id="3a8a9-162">指定的预测的条件的代码。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-162">Specifies a code for the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="3a8a9-163">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="3a8a9-163">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="3a8a9-164">skytextday</span><span class="sxs-lookup"><span data-stu-id="3a8a9-164">skytextday</span></span>  <br/> |<span data-ttu-id="3a8a9-165">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a8a9-165">xs:string</span></span>  <br/> |<span data-ttu-id="3a8a9-166">必需</span><span class="sxs-lookup"><span data-stu-id="3a8a9-166">required</span></span>  <br/> |<span data-ttu-id="3a8a9-167">指定一到两个单词的描述的预测的条件。</span><span class="sxs-lookup"><span data-stu-id="3a8a9-167">Specifies one to two words that describe the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="3a8a9-168">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="3a8a9-168">A value of the type xs:string</span></span>  <br/> |
   

