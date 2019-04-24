---
title: SnapAngles 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 803ddfc1-b7d3-736f-2d85-7b8780ef9278
description: 包含 SnapAngle 元素的集合。
ms.openlocfilehash: 8121a65505c5283ea3cc4ff93a94fdae4c64d7a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334655"
---
# <a name="snapangles-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="f40dd-103">SnapAngles 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="f40dd-103">SnapAngles element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="f40dd-104">包含**SnapAngle**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="f40dd-104">Contains a collection of **SnapAngle** elements.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="f40dd-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f40dd-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f40dd-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f40dd-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f40dd-107">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="f40dd-107">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f40dd-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f40dd-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f40dd-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f40dd-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f40dd-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="f40dd-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f40dd-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f40dd-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f40dd-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="f40dd-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f40dd-113">定义</span><span class="sxs-lookup"><span data-stu-id="f40dd-113">Definition</span></span>

```XML
< xs:element name="SnapAngles" type="SnapAngles_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f40dd-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f40dd-114">Elements and attributes</span></span>

<span data-ttu-id="f40dd-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="f40dd-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f40dd-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f40dd-116">Parent elements</span></span>

|<span data-ttu-id="f40dd-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f40dd-117">**Element**</span></span>|<span data-ttu-id="f40dd-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f40dd-118">**Type**</span></span>|<span data-ttu-id="f40dd-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f40dd-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f40dd-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="f40dd-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f40dd-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="f40dd-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f40dd-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="f40dd-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f40dd-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f40dd-123">Child elements</span></span>

|<span data-ttu-id="f40dd-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="f40dd-124">**Element**</span></span>|<span data-ttu-id="f40dd-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f40dd-125">**Type**</span></span>|<span data-ttu-id="f40dd-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f40dd-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f40dd-127">SnapAngle</span><span class="sxs-lookup"><span data-stu-id="f40dd-127">SnapAngle</span></span>](snapangle-element-snapangles_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f40dd-128">SnapAngle_Type</span><span class="sxs-lookup"><span data-stu-id="f40dd-128">SnapAngle_Type</span></span>](snapangle_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f40dd-129">包含以度为单位指定对齐角度的浮点数字。</span><span class="sxs-lookup"><span data-stu-id="f40dd-129">Contains a floating point number that specifies a snap angle in degrees.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f40dd-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="f40dd-130">Attributes</span></span>

<span data-ttu-id="f40dd-131">无。</span><span class="sxs-lookup"><span data-stu-id="f40dd-131">None.</span></span>
  

