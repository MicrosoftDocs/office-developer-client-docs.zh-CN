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
ms.openlocfilehash: 6dec923ce45ddc6470d80e1c973528246e01672f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540985"
---
# <a name="currenttype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="36d5e-103">currentType 复杂类型 (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="36d5e-103">currentType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="36d5e-104">定义有关某个位置的当前天气条件的参数。</span><span class="sxs-lookup"><span data-stu-id="36d5e-104">Defines the parameters about the current weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="36d5e-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="36d5e-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="36d5e-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="36d5e-106">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="36d5e-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="36d5e-107">**Schema file**</span></span> <br/> |<span data-ttu-id="36d5e-108">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="36d5e-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="36d5e-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="36d5e-109">**Extension base**</span></span> <br/> |<span data-ttu-id="36d5e-110">无</span><span class="sxs-lookup"><span data-stu-id="36d5e-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="36d5e-111">定义</span><span class="sxs-lookup"><span data-stu-id="36d5e-111">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="36d5e-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="36d5e-112">Elements and attributes</span></span>

<span data-ttu-id="36d5e-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="36d5e-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="36d5e-114">子元素</span><span class="sxs-lookup"><span data-stu-id="36d5e-114">Child elements</span></span>

<span data-ttu-id="36d5e-115">无。</span><span class="sxs-lookup"><span data-stu-id="36d5e-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="36d5e-116">属性</span><span class="sxs-lookup"><span data-stu-id="36d5e-116">Attributes</span></span>

|<span data-ttu-id="36d5e-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="36d5e-117">**Attribute**</span></span>|<span data-ttu-id="36d5e-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="36d5e-118">**Type**</span></span>|<span data-ttu-id="36d5e-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="36d5e-119">**Required**</span></span>|<span data-ttu-id="36d5e-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="36d5e-120">**Description**</span></span>|<span data-ttu-id="36d5e-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="36d5e-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="36d5e-122">date</span><span class="sxs-lookup"><span data-stu-id="36d5e-122">date</span></span>  <br/> |<span data-ttu-id="36d5e-123">xs: date</span><span class="sxs-lookup"><span data-stu-id="36d5e-123">xs:date</span></span>  <br/> |<span data-ttu-id="36d5e-124">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-124">required</span></span>  <br/> |<span data-ttu-id="36d5e-125">指定今天的日期。</span><span class="sxs-lookup"><span data-stu-id="36d5e-125">Specifies today's date.</span></span>  <br/> |<span data-ttu-id="36d5e-126">类型 xs: date 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-126">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="36d5e-127">为期</span><span class="sxs-lookup"><span data-stu-id="36d5e-127">day</span></span>  <br/> |<span data-ttu-id="36d5e-128">xs: string</span><span class="sxs-lookup"><span data-stu-id="36d5e-128">xs:string</span></span>  <br/> |<span data-ttu-id="36d5e-129">可选</span><span class="sxs-lookup"><span data-stu-id="36d5e-129">optional</span></span>  <br/> |<span data-ttu-id="36d5e-130">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="36d5e-130">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="36d5e-131">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-131">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="36d5e-132">feelslike</span><span class="sxs-lookup"><span data-stu-id="36d5e-132">feelslike</span></span>  <br/> |<span data-ttu-id="36d5e-133">xs: integer</span><span class="sxs-lookup"><span data-stu-id="36d5e-133">xs:integer</span></span>  <br/> |<span data-ttu-id="36d5e-134">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-134">required</span></span>  <br/> |<span data-ttu-id="36d5e-135">指定当前天气的外观的温度。</span><span class="sxs-lookup"><span data-stu-id="36d5e-135">Specifies the temperature of how the current weather feels like.</span></span>  <br/> |<span data-ttu-id="36d5e-136">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-136">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="36d5e-137">湿度</span><span class="sxs-lookup"><span data-stu-id="36d5e-137">humidity</span></span>  <br/> |<span data-ttu-id="36d5e-138">xs: integer</span><span class="sxs-lookup"><span data-stu-id="36d5e-138">xs:integer</span></span>  <br/> |<span data-ttu-id="36d5e-139">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-139">required</span></span>  <br/> |<span data-ttu-id="36d5e-140">指定当前的数值湿度值。</span><span class="sxs-lookup"><span data-stu-id="36d5e-140">Specifies the current numerical humidity value.</span></span>  <br/> |<span data-ttu-id="36d5e-141">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-141">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="36d5e-142">observationpoint</span><span class="sxs-lookup"><span data-stu-id="36d5e-142">observationpoint</span></span>  <br/> |<span data-ttu-id="36d5e-143">xs: string</span><span class="sxs-lookup"><span data-stu-id="36d5e-143">xs:string</span></span>  <br/> |<span data-ttu-id="36d5e-144">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-144">required</span></span>  <br/> |<span data-ttu-id="36d5e-145">指定观察当前天气信息的位置。</span><span class="sxs-lookup"><span data-stu-id="36d5e-145">Specifies where the current weather information is observed from.</span></span>  <br/> |<span data-ttu-id="36d5e-146">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-146">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="36d5e-147">observationtime</span><span class="sxs-lookup"><span data-stu-id="36d5e-147">observationtime</span></span>  <br/> |<span data-ttu-id="36d5e-148">xs: time</span><span class="sxs-lookup"><span data-stu-id="36d5e-148">xs:time</span></span>  <br/> |<span data-ttu-id="36d5e-149">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-149">required</span></span>  <br/> |<span data-ttu-id="36d5e-150">指定何时在中观察当前天气信息。</span><span class="sxs-lookup"><span data-stu-id="36d5e-150">Specifies when the current weather information is observed at.</span></span>  <br/> |<span data-ttu-id="36d5e-151">类型 xs: time 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-151">A value of the type xs:time</span></span>  <br/> |
|<span data-ttu-id="36d5e-152">shortday</span><span class="sxs-lookup"><span data-stu-id="36d5e-152">shortday</span></span>  <br/> |<span data-ttu-id="36d5e-153">xs: string</span><span class="sxs-lookup"><span data-stu-id="36d5e-153">xs:string</span></span>  <br/> |<span data-ttu-id="36d5e-154">可选</span><span class="sxs-lookup"><span data-stu-id="36d5e-154">optional</span></span>  <br/> |<span data-ttu-id="36d5e-155">指定缩写形式的日期。</span><span class="sxs-lookup"><span data-stu-id="36d5e-155">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="36d5e-156">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-156">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="36d5e-157">skycode</span><span class="sxs-lookup"><span data-stu-id="36d5e-157">skycode</span></span>  <br/> |<span data-ttu-id="36d5e-158">xs: integer</span><span class="sxs-lookup"><span data-stu-id="36d5e-158">xs:integer</span></span>  <br/> |<span data-ttu-id="36d5e-159">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-159">required</span></span>  <br/> |<span data-ttu-id="36d5e-160">指定当前天气条件的整数代码。</span><span class="sxs-lookup"><span data-stu-id="36d5e-160">Specifies an integer code for the current weather conditions.</span></span>  <br/> |<span data-ttu-id="36d5e-161">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-161">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="36d5e-162">skytext</span><span class="sxs-lookup"><span data-stu-id="36d5e-162">skytext</span></span>  <br/> |<span data-ttu-id="36d5e-163">xs: string</span><span class="sxs-lookup"><span data-stu-id="36d5e-163">xs:string</span></span>  <br/> |<span data-ttu-id="36d5e-164">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-164">required</span></span>  <br/> |<span data-ttu-id="36d5e-165">指定一个描述当前天气情况的两个字。</span><span class="sxs-lookup"><span data-stu-id="36d5e-165">Specifies one to two words describing current weather conditions.</span></span>  <br/> |<span data-ttu-id="36d5e-166">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-166">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="36d5e-167">量</span><span class="sxs-lookup"><span data-stu-id="36d5e-167">temperature</span></span>  <br/> |<span data-ttu-id="36d5e-168">xs: integer</span><span class="sxs-lookup"><span data-stu-id="36d5e-168">xs:integer</span></span>  <br/> |<span data-ttu-id="36d5e-169">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-169">required</span></span>  <br/> |<span data-ttu-id="36d5e-170">指定位置的当前温度。</span><span class="sxs-lookup"><span data-stu-id="36d5e-170">Specifies the current temperature of the location.</span></span>  <br/> |<span data-ttu-id="36d5e-171">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-171">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="36d5e-172">winddisplay</span><span class="sxs-lookup"><span data-stu-id="36d5e-172">winddisplay</span></span>  <br/> |<span data-ttu-id="36d5e-173">xs: string</span><span class="sxs-lookup"><span data-stu-id="36d5e-173">xs:string</span></span>  <br/> |<span data-ttu-id="36d5e-174">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-174">required</span></span>  <br/> |<span data-ttu-id="36d5e-175">一个描述当前风条件的字符串。</span><span class="sxs-lookup"><span data-stu-id="36d5e-175">A string that describes the current wind conditions.</span></span>  <br/> |<span data-ttu-id="36d5e-176">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-176">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="36d5e-177">windspeed</span><span class="sxs-lookup"><span data-stu-id="36d5e-177">windspeed</span></span>  <br/> |<span data-ttu-id="36d5e-178">xs: integer</span><span class="sxs-lookup"><span data-stu-id="36d5e-178">xs:integer</span></span>  <br/> |<span data-ttu-id="36d5e-179">必需</span><span class="sxs-lookup"><span data-stu-id="36d5e-179">required</span></span>  <br/> |<span data-ttu-id="36d5e-180">指定当前的数值风速度值。</span><span class="sxs-lookup"><span data-stu-id="36d5e-180">Specifies the current numerical wind speed value.</span></span>  <br/> |<span data-ttu-id="36d5e-181">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="36d5e-181">A value of the type xs:integer</span></span>  <br/> |
   

