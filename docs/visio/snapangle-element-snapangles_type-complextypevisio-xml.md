---
title: SnapAngle 元素 （SnapAngles_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d4f93fc5-80fb-3195-d25b-9a407de7848e
description: 包含浮点数指定管理角度单位为度。
ms.openlocfilehash: c283be7d613c574d60412f645271d2c947ae0ffb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397000"
---
# <a name="snapangle-element-snapanglestype-complextype-visio-xml"></a><span data-ttu-id="44cde-103">SnapAngle 元素 （SnapAngles_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="44cde-103">SnapAngle element (SnapAngles_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="44cde-104">包含浮点数指定管理角度单位为度。</span><span class="sxs-lookup"><span data-stu-id="44cde-104">Contains a floating point number that specifies a snap angle in degrees.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="44cde-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="44cde-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="44cde-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="44cde-106">**Element type**</span></span> <br/> |[<span data-ttu-id="44cde-107">SnapAngle_Type</span><span class="sxs-lookup"><span data-stu-id="44cde-107">SnapAngle_Type</span></span>](snapangle_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="44cde-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="44cde-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="44cde-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="44cde-109">**Schema file**</span></span> <br/> |<span data-ttu-id="44cde-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="44cde-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="44cde-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="44cde-111">**Document parts**</span></span> <br/> |<span data-ttu-id="44cde-112">document.xml、 windows.xml</span><span class="sxs-lookup"><span data-stu-id="44cde-112">document.xml, windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="44cde-113">定义</span><span class="sxs-lookup"><span data-stu-id="44cde-113">Definition</span></span>

```XML
< xs:element name="SnapAngle" type="SnapAngle_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="44cde-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="44cde-114">Elements and attributes</span></span>

<span data-ttu-id="44cde-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="44cde-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="44cde-116">父元素</span><span class="sxs-lookup"><span data-stu-id="44cde-116">Parent elements</span></span>

|<span data-ttu-id="44cde-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="44cde-117">**Element**</span></span>|<span data-ttu-id="44cde-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="44cde-118">**Type**</span></span>|<span data-ttu-id="44cde-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="44cde-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="44cde-120">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="44cde-120">SnapAngles</span></span>](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="44cde-121">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="44cde-121">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="44cde-122">包含**SnapAngle**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="44cde-122">Contains a collection of **SnapAngle** elements.</span></span>  <br/> |
|[<span data-ttu-id="44cde-123">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="44cde-123">SnapAngles</span></span>](snapangles-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="44cde-124">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="44cde-124">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="44cde-125">包含**SnapAngle**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="44cde-125">Contains a collection of **SnapAngle** elements.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="44cde-126">子元素</span><span class="sxs-lookup"><span data-stu-id="44cde-126">Child elements</span></span>

<span data-ttu-id="44cde-127">无。</span><span class="sxs-lookup"><span data-stu-id="44cde-127">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="44cde-128">属性</span><span class="sxs-lookup"><span data-stu-id="44cde-128">Attributes</span></span>

<span data-ttu-id="44cde-129">无。</span><span class="sxs-lookup"><span data-stu-id="44cde-129">None.</span></span>
  

