---
title: weatherdata 元素 (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 84b16927-964e-24be-feaa-e0c11cf062f3
description: 定义气象元素。
ms.openlocfilehash: bb8c76efd03661083a15aa315cf42c3a6c088b6f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538982"
---
# <a name="weatherdata-element-outlook-weather-information-schema"></a><span data-ttu-id="c8240-103">weatherdata 元素 (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="c8240-103">weatherdata element (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="c8240-104">定义气象元素。</span><span class="sxs-lookup"><span data-stu-id="c8240-104">Defines the weather element.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c8240-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c8240-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c8240-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c8240-106">**Element type**</span></span> <br/> ||
|<span data-ttu-id="c8240-107">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c8240-107">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="c8240-108">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c8240-108">**Schema file**</span></span> <br/> |<span data-ttu-id="c8240-109">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="c8240-109">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c8240-110">定义</span><span class="sxs-lookup"><span data-stu-id="c8240-110">Definition</span></span>

```XML
    <xs:element name="weatherdata"
    >
          <xs:complexType>
          <xs:sequence>
    <xs:element name="weather"
     type="weatherType">
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
    </xs:element>
    
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c8240-111">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c8240-111">Elements and attributes</span></span>

<span data-ttu-id="c8240-112">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="c8240-112">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c8240-113">父元素</span><span class="sxs-lookup"><span data-stu-id="c8240-113">Parent elements</span></span>

<span data-ttu-id="c8240-114">无。</span><span class="sxs-lookup"><span data-stu-id="c8240-114">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c8240-115">子元素</span><span class="sxs-lookup"><span data-stu-id="c8240-115">Child elements</span></span>

|<span data-ttu-id="c8240-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="c8240-116">**Element**</span></span>|<span data-ttu-id="c8240-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="c8240-117">**Type**</span></span>|<span data-ttu-id="c8240-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="c8240-118">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c8240-119">气候</span><span class="sxs-lookup"><span data-stu-id="c8240-119">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="c8240-120">weatherType</span><span class="sxs-lookup"><span data-stu-id="c8240-120">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="c8240-121">指定位置的天气情况。</span><span class="sxs-lookup"><span data-stu-id="c8240-121">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="c8240-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="c8240-122">Attributes</span></span>

<span data-ttu-id="c8240-123">无。</span><span class="sxs-lookup"><span data-stu-id="c8240-123">None.</span></span>
  

