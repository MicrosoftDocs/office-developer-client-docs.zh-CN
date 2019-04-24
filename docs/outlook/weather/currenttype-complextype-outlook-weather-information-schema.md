---
title: currentType 复杂类型 (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9f4663ac-13d3-6c46-f839-ba6bca4047a3
description: 定义有关某个位置的当前天气条件的参数。
ms.openlocfilehash: 16d3e23375f68315c9b9f3a7e914d93f4fec9d0a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338449"
---
# <a name="currenttype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="674f7-103">currentType 复杂类型 (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="674f7-103">currentType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="674f7-104">定义有关某个位置的当前天气条件的参数。</span><span class="sxs-lookup"><span data-stu-id="674f7-104">Defines the parameters about the current weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="674f7-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="674f7-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="674f7-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="674f7-106">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="674f7-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="674f7-107">**Schema file**</span></span> <br/> |<span data-ttu-id="674f7-108">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="674f7-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="674f7-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="674f7-109">**Extension base**</span></span> <br/> |<span data-ttu-id="674f7-110">无</span><span class="sxs-lookup"><span data-stu-id="674f7-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="674f7-111">定义</span><span class="sxs-lookup"><span data-stu-id="674f7-111">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="674f7-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="674f7-112">Elements and attributes</span></span>

<span data-ttu-id="674f7-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="674f7-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="674f7-114">子元素</span><span class="sxs-lookup"><span data-stu-id="674f7-114">Child elements</span></span>

<span data-ttu-id="674f7-115">无。</span><span class="sxs-lookup"><span data-stu-id="674f7-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="674f7-116">属性</span><span class="sxs-lookup"><span data-stu-id="674f7-116">Attributes</span></span>

|<span data-ttu-id="674f7-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="674f7-117">**Attribute**</span></span>|<span data-ttu-id="674f7-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="674f7-118">**Type**</span></span>|<span data-ttu-id="674f7-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="674f7-119">**Required**</span></span>|<span data-ttu-id="674f7-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="674f7-120">**Description**</span></span>|<span data-ttu-id="674f7-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="674f7-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="674f7-122">date</span><span class="sxs-lookup"><span data-stu-id="674f7-122">date</span></span>  <br/> |<span data-ttu-id="674f7-123">xs: date</span><span class="sxs-lookup"><span data-stu-id="674f7-123">xs:date</span></span>  <br/> |<span data-ttu-id="674f7-124">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-124">required</span></span>  <br/> |<span data-ttu-id="674f7-125">指定今天的日期。</span><span class="sxs-lookup"><span data-stu-id="674f7-125">Specifies today's date.</span></span>  <br/> |<span data-ttu-id="674f7-126">类型 xs: date 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-126">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="674f7-127">为期</span><span class="sxs-lookup"><span data-stu-id="674f7-127">day</span></span>  <br/> |<span data-ttu-id="674f7-128">xs: string</span><span class="sxs-lookup"><span data-stu-id="674f7-128">xs:string</span></span>  <br/> |<span data-ttu-id="674f7-129">可选</span><span class="sxs-lookup"><span data-stu-id="674f7-129">optional</span></span>  <br/> |<span data-ttu-id="674f7-130">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="674f7-130">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="674f7-131">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-131">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="674f7-132">feelslike</span><span class="sxs-lookup"><span data-stu-id="674f7-132">feelslike</span></span>  <br/> |<span data-ttu-id="674f7-133">xs: integer</span><span class="sxs-lookup"><span data-stu-id="674f7-133">xs:integer</span></span>  <br/> |<span data-ttu-id="674f7-134">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-134">required</span></span>  <br/> |<span data-ttu-id="674f7-135">指定当前天气的外观的温度。</span><span class="sxs-lookup"><span data-stu-id="674f7-135">Specifies the temperature of how the current weather feels like.</span></span>  <br/> |<span data-ttu-id="674f7-136">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-136">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="674f7-137">湿度</span><span class="sxs-lookup"><span data-stu-id="674f7-137">humidity</span></span>  <br/> |<span data-ttu-id="674f7-138">xs: integer</span><span class="sxs-lookup"><span data-stu-id="674f7-138">xs:integer</span></span>  <br/> |<span data-ttu-id="674f7-139">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-139">required</span></span>  <br/> |<span data-ttu-id="674f7-140">指定当前的数值湿度值。</span><span class="sxs-lookup"><span data-stu-id="674f7-140">Specifies the current numerical humidity value.</span></span>  <br/> |<span data-ttu-id="674f7-141">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-141">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="674f7-142">observationpoint</span><span class="sxs-lookup"><span data-stu-id="674f7-142">observationpoint</span></span>  <br/> |<span data-ttu-id="674f7-143">xs: string</span><span class="sxs-lookup"><span data-stu-id="674f7-143">xs:string</span></span>  <br/> |<span data-ttu-id="674f7-144">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-144">required</span></span>  <br/> |<span data-ttu-id="674f7-145">指定观察当前天气信息的位置。</span><span class="sxs-lookup"><span data-stu-id="674f7-145">Specifies where the current weather information is observed from.</span></span>  <br/> |<span data-ttu-id="674f7-146">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-146">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="674f7-147">observationtime</span><span class="sxs-lookup"><span data-stu-id="674f7-147">observationtime</span></span>  <br/> |<span data-ttu-id="674f7-148">xs: time</span><span class="sxs-lookup"><span data-stu-id="674f7-148">xs:time</span></span>  <br/> |<span data-ttu-id="674f7-149">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-149">required</span></span>  <br/> |<span data-ttu-id="674f7-150">指定何时在中观察当前天气信息。</span><span class="sxs-lookup"><span data-stu-id="674f7-150">Specifies when the current weather information is observed at.</span></span>  <br/> |<span data-ttu-id="674f7-151">类型 xs: time 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-151">A value of the type xs:time</span></span>  <br/> |
|<span data-ttu-id="674f7-152">shortday</span><span class="sxs-lookup"><span data-stu-id="674f7-152">shortday</span></span>  <br/> |<span data-ttu-id="674f7-153">xs: string</span><span class="sxs-lookup"><span data-stu-id="674f7-153">xs:string</span></span>  <br/> |<span data-ttu-id="674f7-154">可选</span><span class="sxs-lookup"><span data-stu-id="674f7-154">optional</span></span>  <br/> |<span data-ttu-id="674f7-155">指定缩写形式的日期。</span><span class="sxs-lookup"><span data-stu-id="674f7-155">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="674f7-156">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-156">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="674f7-157">skycode</span><span class="sxs-lookup"><span data-stu-id="674f7-157">skycode</span></span>  <br/> |<span data-ttu-id="674f7-158">xs: integer</span><span class="sxs-lookup"><span data-stu-id="674f7-158">xs:integer</span></span>  <br/> |<span data-ttu-id="674f7-159">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-159">required</span></span>  <br/> |<span data-ttu-id="674f7-160">指定当前天气条件的整数代码。</span><span class="sxs-lookup"><span data-stu-id="674f7-160">Specifies an integer code for the current weather conditions.</span></span>  <br/> |<span data-ttu-id="674f7-161">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-161">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="674f7-162">skytext</span><span class="sxs-lookup"><span data-stu-id="674f7-162">skytext</span></span>  <br/> |<span data-ttu-id="674f7-163">xs: string</span><span class="sxs-lookup"><span data-stu-id="674f7-163">xs:string</span></span>  <br/> |<span data-ttu-id="674f7-164">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-164">required</span></span>  <br/> |<span data-ttu-id="674f7-165">指定一个描述当前天气情况的两个字。</span><span class="sxs-lookup"><span data-stu-id="674f7-165">Specifies one to two words describing current weather conditions.</span></span>  <br/> |<span data-ttu-id="674f7-166">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-166">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="674f7-167">量</span><span class="sxs-lookup"><span data-stu-id="674f7-167">temperature</span></span>  <br/> |<span data-ttu-id="674f7-168">xs: integer</span><span class="sxs-lookup"><span data-stu-id="674f7-168">xs:integer</span></span>  <br/> |<span data-ttu-id="674f7-169">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-169">required</span></span>  <br/> |<span data-ttu-id="674f7-170">指定位置的当前温度。</span><span class="sxs-lookup"><span data-stu-id="674f7-170">Specifies the current temperature of the location.</span></span>  <br/> |<span data-ttu-id="674f7-171">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-171">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="674f7-172">winddisplay</span><span class="sxs-lookup"><span data-stu-id="674f7-172">winddisplay</span></span>  <br/> |<span data-ttu-id="674f7-173">xs: string</span><span class="sxs-lookup"><span data-stu-id="674f7-173">xs:string</span></span>  <br/> |<span data-ttu-id="674f7-174">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-174">required</span></span>  <br/> |<span data-ttu-id="674f7-175">一个描述当前风条件的字符串。</span><span class="sxs-lookup"><span data-stu-id="674f7-175">A string that describes the current wind conditions.</span></span>  <br/> |<span data-ttu-id="674f7-176">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-176">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="674f7-177">windspeed</span><span class="sxs-lookup"><span data-stu-id="674f7-177">windspeed</span></span>  <br/> |<span data-ttu-id="674f7-178">xs: integer</span><span class="sxs-lookup"><span data-stu-id="674f7-178">xs:integer</span></span>  <br/> |<span data-ttu-id="674f7-179">必需</span><span class="sxs-lookup"><span data-stu-id="674f7-179">required</span></span>  <br/> |<span data-ttu-id="674f7-180">指定当前的数值风速度值。</span><span class="sxs-lookup"><span data-stu-id="674f7-180">Specifies the current numerical wind speed value.</span></span>  <br/> |<span data-ttu-id="674f7-181">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="674f7-181">A value of the type xs:integer</span></span>  <br/> |
   

