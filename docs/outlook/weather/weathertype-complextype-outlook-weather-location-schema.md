---
title: 'weatherType complexType (Outlook Weather Location Schema) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8054fd9-85ba-fcf6-c96d-a54095d5238c
description: 定义有关位置的天气状况的参数。
ms.openlocfilehash: f7d33cb018daf4ece2ba468b9ebe92b0fc7b1545
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542917"
---
# <a name="weathertype-complextype-outlook-weather-location-schema"></a><span data-ttu-id="967a8-103">weatherType complexType (Outlook Weather Location Schema) </span><span class="sxs-lookup"><span data-stu-id="967a8-103">weatherType complexType (Outlook Weather Location Schema)</span></span>

<span data-ttu-id="967a8-104">定义有关位置的天气状况的参数。</span><span class="sxs-lookup"><span data-stu-id="967a8-104">Defines the parameters about the weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="967a8-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="967a8-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="967a8-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="967a8-106">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|<span data-ttu-id="967a8-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="967a8-107">**Schema file**</span></span> <br/> |<span data-ttu-id="967a8-108">getweatherlocation.xsd</span><span class="sxs-lookup"><span data-stu-id="967a8-108">getweatherlocation.xsd</span></span>  <br/> |
|<span data-ttu-id="967a8-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="967a8-109">**Extension base**</span></span> <br/> |<span data-ttu-id="967a8-110">无</span><span class="sxs-lookup"><span data-stu-id="967a8-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="967a8-111">定义</span><span class="sxs-lookup"><span data-stu-id="967a8-111">Definition</span></span>

```XML
       <xs:complexType name="weatherType">
     <xs:attribute name="weatherlocationname"   type="xs:string"      use="required"     />
     <xs:attribute name="weatherlocationcode"   type="xs:string"      use="required"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a><span data-ttu-id="967a8-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="967a8-112">Elements and attributes</span></span>

<span data-ttu-id="967a8-113">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="967a8-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="967a8-114">子元素</span><span class="sxs-lookup"><span data-stu-id="967a8-114">Child elements</span></span>

<span data-ttu-id="967a8-115">无。</span><span class="sxs-lookup"><span data-stu-id="967a8-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="967a8-116">属性</span><span class="sxs-lookup"><span data-stu-id="967a8-116">Attributes</span></span>

|<span data-ttu-id="967a8-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="967a8-117">**Attribute**</span></span>|<span data-ttu-id="967a8-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="967a8-118">**Type**</span></span>|<span data-ttu-id="967a8-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="967a8-119">**Required**</span></span>|<span data-ttu-id="967a8-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="967a8-120">**Description**</span></span>|<span data-ttu-id="967a8-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="967a8-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="967a8-122">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="967a8-122">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="967a8-123">xs：string</span><span class="sxs-lookup"><span data-stu-id="967a8-123">xs:string</span></span>  <br/> |<span data-ttu-id="967a8-124">必需</span><span class="sxs-lookup"><span data-stu-id="967a8-124">required</span></span>  <br/> |<span data-ttu-id="967a8-125">指定与位置相关联的代码，以使用相同的名称区分多个位置。</span><span class="sxs-lookup"><span data-stu-id="967a8-125">Specifies a code that is associated with the location to distinguish multiple locations with the same name.</span></span>  <br/> |<span data-ttu-id="967a8-126">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="967a8-126">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="967a8-127">weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="967a8-127">weatherlocationname</span></span>  <br/> |<span data-ttu-id="967a8-128">xs：string</span><span class="sxs-lookup"><span data-stu-id="967a8-128">xs:string</span></span>  <br/> |<span data-ttu-id="967a8-129">必需</span><span class="sxs-lookup"><span data-stu-id="967a8-129">required</span></span>  <br/> |<span data-ttu-id="967a8-130">指定位置的名称。</span><span class="sxs-lookup"><span data-stu-id="967a8-130">Specifies the name of the location.</span></span>  <br/> |<span data-ttu-id="967a8-131">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="967a8-131">A value of the type xs:string</span></span>  <br/> |
   

