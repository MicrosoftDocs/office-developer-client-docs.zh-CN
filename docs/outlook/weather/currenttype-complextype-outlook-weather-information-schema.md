---
title: 'currentType complexType (Outlook天气信息架构) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9f4663ac-13d3-6c46-f839-ba6bca4047a3
description: 定义有关位置当前天气状况的参数。
ms.openlocfilehash: 6dec923ce45ddc6470d80e1c973528246e01672f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540985"
---
# <a name="currenttype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="ad9df-103">currentType complexType (Outlook天气信息架构) </span><span class="sxs-lookup"><span data-stu-id="ad9df-103">currentType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="ad9df-104">定义有关位置当前天气状况的参数。</span><span class="sxs-lookup"><span data-stu-id="ad9df-104">Defines the parameters about the current weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="ad9df-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="ad9df-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ad9df-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ad9df-106">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="ad9df-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ad9df-107">**Schema file**</span></span> <br/> |<span data-ttu-id="ad9df-108">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="ad9df-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="ad9df-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ad9df-109">**Extension base**</span></span> <br/> |<span data-ttu-id="ad9df-110">无</span><span class="sxs-lookup"><span data-stu-id="ad9df-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ad9df-111">定义</span><span class="sxs-lookup"><span data-stu-id="ad9df-111">Definition</span></span>

```XML
       <xs:complexType name="currentType">
     <xs:attribute name="winddisplay"   type="xs:string"      use="required"     />
     <xs:attribute name="windspeed"   type="xs:integer"      use="required"     />
     <xs:attribute name="humidity"   type="xs:integer"      use="required"     />
     <xs:attribute name="feelslike"   type="xs:integer"      use="required"     />
     <xs:attribute name="observationpoint"   type="xs:string"      use="required"     />
     <xs:attribute name="observationtime"   type="xs:time"      use="required"     />
     <xs:attribute name="date"   type="xs:date"      use="required"     />
     <xs:attribute name="skytext"   type="xs:string"      use="required"     />
     <xs:attribute name="skycode"   type="xs:integer"      use="required"     />
     <xs:attribute name="temperature"   type="xs:integer"      use="required"     />
     <xs:attribute name="shortday"   type="xs:string"      use="optional"     />
     <xs:attribute name="day"   type="xs:string"      use="optional"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a><span data-ttu-id="ad9df-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ad9df-112">Elements and attributes</span></span>

<span data-ttu-id="ad9df-113">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ad9df-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ad9df-114">子元素</span><span class="sxs-lookup"><span data-stu-id="ad9df-114">Child elements</span></span>

<span data-ttu-id="ad9df-115">无。</span><span class="sxs-lookup"><span data-stu-id="ad9df-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ad9df-116">属性</span><span class="sxs-lookup"><span data-stu-id="ad9df-116">Attributes</span></span>

|<span data-ttu-id="ad9df-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="ad9df-117">**Attribute**</span></span>|<span data-ttu-id="ad9df-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="ad9df-118">**Type**</span></span>|<span data-ttu-id="ad9df-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="ad9df-119">**Required**</span></span>|<span data-ttu-id="ad9df-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="ad9df-120">**Description**</span></span>|<span data-ttu-id="ad9df-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ad9df-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad9df-122">date</span><span class="sxs-lookup"><span data-stu-id="ad9df-122">date</span></span>  <br/> |<span data-ttu-id="ad9df-123">xs：date</span><span class="sxs-lookup"><span data-stu-id="ad9df-123">xs:date</span></span>  <br/> |<span data-ttu-id="ad9df-124">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-124">required</span></span>  <br/> |<span data-ttu-id="ad9df-125">指定今天的日期。</span><span class="sxs-lookup"><span data-stu-id="ad9df-125">Specifies today's date.</span></span>  <br/> |<span data-ttu-id="ad9df-126">xs：date 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-126">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="ad9df-127">day</span><span class="sxs-lookup"><span data-stu-id="ad9df-127">day</span></span>  <br/> |<span data-ttu-id="ad9df-128">xs：string</span><span class="sxs-lookup"><span data-stu-id="ad9df-128">xs:string</span></span>  <br/> |<span data-ttu-id="ad9df-129">可选</span><span class="sxs-lookup"><span data-stu-id="ad9df-129">optional</span></span>  <br/> |<span data-ttu-id="ad9df-130">指定预测的一天。</span><span class="sxs-lookup"><span data-stu-id="ad9df-130">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="ad9df-131">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-131">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="ad9df-132">感觉相似</span><span class="sxs-lookup"><span data-stu-id="ad9df-132">feelslike</span></span>  <br/> |<span data-ttu-id="ad9df-133">xs：integer</span><span class="sxs-lookup"><span data-stu-id="ad9df-133">xs:integer</span></span>  <br/> |<span data-ttu-id="ad9df-134">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-134">required</span></span>  <br/> |<span data-ttu-id="ad9df-135">指定当前天气的温度。</span><span class="sxs-lookup"><span data-stu-id="ad9df-135">Specifies the temperature of how the current weather feels like.</span></span>  <br/> |<span data-ttu-id="ad9df-136">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-136">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="ad9df-137">一些</span><span class="sxs-lookup"><span data-stu-id="ad9df-137">humidity</span></span>  <br/> |<span data-ttu-id="ad9df-138">xs：integer</span><span class="sxs-lookup"><span data-stu-id="ad9df-138">xs:integer</span></span>  <br/> |<span data-ttu-id="ad9df-139">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-139">required</span></span>  <br/> |<span data-ttu-id="ad9df-140">指定当前的数值数值。</span><span class="sxs-lookup"><span data-stu-id="ad9df-140">Specifies the current numerical humidity value.</span></span>  <br/> |<span data-ttu-id="ad9df-141">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-141">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="ad9df-142">观察点</span><span class="sxs-lookup"><span data-stu-id="ad9df-142">observationpoint</span></span>  <br/> |<span data-ttu-id="ad9df-143">xs：string</span><span class="sxs-lookup"><span data-stu-id="ad9df-143">xs:string</span></span>  <br/> |<span data-ttu-id="ad9df-144">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-144">required</span></span>  <br/> |<span data-ttu-id="ad9df-145">指定从何处观测当前天气信息。</span><span class="sxs-lookup"><span data-stu-id="ad9df-145">Specifies where the current weather information is observed from.</span></span>  <br/> |<span data-ttu-id="ad9df-146">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-146">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="ad9df-147">观察时间</span><span class="sxs-lookup"><span data-stu-id="ad9df-147">observationtime</span></span>  <br/> |<span data-ttu-id="ad9df-148">xs：time</span><span class="sxs-lookup"><span data-stu-id="ad9df-148">xs:time</span></span>  <br/> |<span data-ttu-id="ad9df-149">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-149">required</span></span>  <br/> |<span data-ttu-id="ad9df-150">指定何时观测到当前天气信息。</span><span class="sxs-lookup"><span data-stu-id="ad9df-150">Specifies when the current weather information is observed at.</span></span>  <br/> |<span data-ttu-id="ad9df-151">xs：time 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-151">A value of the type xs:time</span></span>  <br/> |
|<span data-ttu-id="ad9df-152">shortday</span><span class="sxs-lookup"><span data-stu-id="ad9df-152">shortday</span></span>  <br/> |<span data-ttu-id="ad9df-153">xs：string</span><span class="sxs-lookup"><span data-stu-id="ad9df-153">xs:string</span></span>  <br/> |<span data-ttu-id="ad9df-154">可选</span><span class="sxs-lookup"><span data-stu-id="ad9df-154">optional</span></span>  <br/> |<span data-ttu-id="ad9df-155">以缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="ad9df-155">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="ad9df-156">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-156">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="ad9df-157">skycode</span><span class="sxs-lookup"><span data-stu-id="ad9df-157">skycode</span></span>  <br/> |<span data-ttu-id="ad9df-158">xs：integer</span><span class="sxs-lookup"><span data-stu-id="ad9df-158">xs:integer</span></span>  <br/> |<span data-ttu-id="ad9df-159">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-159">required</span></span>  <br/> |<span data-ttu-id="ad9df-160">指定当前天气条件的整数代码。</span><span class="sxs-lookup"><span data-stu-id="ad9df-160">Specifies an integer code for the current weather conditions.</span></span>  <br/> |<span data-ttu-id="ad9df-161">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-161">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="ad9df-162">skytext</span><span class="sxs-lookup"><span data-stu-id="ad9df-162">skytext</span></span>  <br/> |<span data-ttu-id="ad9df-163">xs：string</span><span class="sxs-lookup"><span data-stu-id="ad9df-163">xs:string</span></span>  <br/> |<span data-ttu-id="ad9df-164">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-164">required</span></span>  <br/> |<span data-ttu-id="ad9df-165">指定描述当前天气条件的一到两个单词。</span><span class="sxs-lookup"><span data-stu-id="ad9df-165">Specifies one to two words describing current weather conditions.</span></span>  <br/> |<span data-ttu-id="ad9df-166">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-166">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="ad9df-167">temperature</span><span class="sxs-lookup"><span data-stu-id="ad9df-167">temperature</span></span>  <br/> |<span data-ttu-id="ad9df-168">xs：integer</span><span class="sxs-lookup"><span data-stu-id="ad9df-168">xs:integer</span></span>  <br/> |<span data-ttu-id="ad9df-169">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-169">required</span></span>  <br/> |<span data-ttu-id="ad9df-170">指定位置的当前温度。</span><span class="sxs-lookup"><span data-stu-id="ad9df-170">Specifies the current temperature of the location.</span></span>  <br/> |<span data-ttu-id="ad9df-171">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-171">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="ad9df-172">winddisplay</span><span class="sxs-lookup"><span data-stu-id="ad9df-172">winddisplay</span></span>  <br/> |<span data-ttu-id="ad9df-173">xs：string</span><span class="sxs-lookup"><span data-stu-id="ad9df-173">xs:string</span></span>  <br/> |<span data-ttu-id="ad9df-174">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-174">required</span></span>  <br/> |<span data-ttu-id="ad9df-175">一个描述当前温度条件的字符串。</span><span class="sxs-lookup"><span data-stu-id="ad9df-175">A string that describes the current wind conditions.</span></span>  <br/> |<span data-ttu-id="ad9df-176">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-176">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="ad9df-177">将</span><span class="sxs-lookup"><span data-stu-id="ad9df-177">windspeed</span></span>  <br/> |<span data-ttu-id="ad9df-178">xs：integer</span><span class="sxs-lookup"><span data-stu-id="ad9df-178">xs:integer</span></span>  <br/> |<span data-ttu-id="ad9df-179">必需</span><span class="sxs-lookup"><span data-stu-id="ad9df-179">required</span></span>  <br/> |<span data-ttu-id="ad9df-180">指定当前数值的时速值。</span><span class="sxs-lookup"><span data-stu-id="ad9df-180">Specifies the current numerical wind speed value.</span></span>  <br/> |<span data-ttu-id="ad9df-181">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="ad9df-181">A value of the type xs:integer</span></span>  <br/> |
   

