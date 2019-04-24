---
title: weatherdata 元素 (Outlook 天气位置架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 14e0c469-31dc-fbe2-0d45-da602df04f13
description: 定义气象元素。
ms.openlocfilehash: ade57264fab592d3314aa9a3376e129a5f3719c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355032"
---
# <a name="weatherdata-element-outlook-weather-location-schema"></a><span data-ttu-id="009d8-103">weatherdata 元素 (Outlook 天气位置架构)</span><span class="sxs-lookup"><span data-stu-id="009d8-103">weatherdata element (Outlook Weather Location Schema)</span></span>

<span data-ttu-id="009d8-104">定义气象元素。</span><span class="sxs-lookup"><span data-stu-id="009d8-104">Defines the weather element.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="009d8-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="009d8-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="009d8-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="009d8-106">**Element type**</span></span> <br/> ||
|<span data-ttu-id="009d8-107">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="009d8-107">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|<span data-ttu-id="009d8-108">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="009d8-108">**Schema file**</span></span> <br/> |<span data-ttu-id="009d8-109">getweatherlocation</span><span class="sxs-lookup"><span data-stu-id="009d8-109">getweatherlocation.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="009d8-110">定义</span><span class="sxs-lookup"><span data-stu-id="009d8-110">Definition</span></span>

```XML
    <xs:element name="weatherdata"
    >
          <xs:complexType>
          <xs:sequence>
    <xs:element name="weather"
     type="weatherType" maxOccurs="unbounded"
      >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
    </xs:element>
    
```

## <a name="elements-and-attributes"></a><span data-ttu-id="009d8-111">元素和属性</span><span class="sxs-lookup"><span data-stu-id="009d8-111">Elements and attributes</span></span>

<span data-ttu-id="009d8-112">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="009d8-112">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="009d8-113">父元素</span><span class="sxs-lookup"><span data-stu-id="009d8-113">Parent elements</span></span>

<span data-ttu-id="009d8-114">无。</span><span class="sxs-lookup"><span data-stu-id="009d8-114">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="009d8-115">子元素</span><span class="sxs-lookup"><span data-stu-id="009d8-115">Child elements</span></span>

|<span data-ttu-id="009d8-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="009d8-116">**Element**</span></span>|<span data-ttu-id="009d8-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="009d8-117">**Type**</span></span>|<span data-ttu-id="009d8-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="009d8-118">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="009d8-119">气候</span><span class="sxs-lookup"><span data-stu-id="009d8-119">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-location-schema.md) <br/> |[<span data-ttu-id="009d8-120">weatherType</span><span class="sxs-lookup"><span data-stu-id="009d8-120">weatherType</span></span>](weathertype-complextype-outlook-weather-location-schema.md) <br/> |<span data-ttu-id="009d8-121">指定要在其上报告天气的位置。</span><span class="sxs-lookup"><span data-stu-id="009d8-121">Specifies the location to report weather on.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="009d8-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="009d8-122">Attributes</span></span>

<span data-ttu-id="009d8-123">无。</span><span class="sxs-lookup"><span data-stu-id="009d8-123">None.</span></span>
  

