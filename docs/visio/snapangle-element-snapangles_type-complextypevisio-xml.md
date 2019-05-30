---
title: SnapAngle 元素 (SnapAngles_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d4f93fc5-80fb-3195-d25b-9a407de7848e
description: 包含以度为单位指定对齐角度的浮点数字。
ms.openlocfilehash: be53b3fdbe7aa04b6bcdf703f1859e866f2af2c2
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540453"
---
# <a name="snapangle-element-snapanglestype-complextype-visio-xml"></a><span data-ttu-id="7041a-103">SnapAngle 元素 (SnapAngles_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="7041a-103">SnapAngle element (SnapAngles_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="7041a-104">包含以度为单位指定对齐角度的浮点数字。</span><span class="sxs-lookup"><span data-stu-id="7041a-104">Contains a floating point number that specifies a snap angle in degrees.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="7041a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="7041a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7041a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="7041a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="7041a-107">SnapAngle_Type</span><span class="sxs-lookup"><span data-stu-id="7041a-107">SnapAngle_Type</span></span>](snapangle_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="7041a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7041a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="7041a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7041a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="7041a-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="7041a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="7041a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="7041a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="7041a-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="7041a-112">document.xml, windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7041a-113">定义</span><span class="sxs-lookup"><span data-stu-id="7041a-113">Definition</span></span>

```XML
< xs:element name="SnapAngle" type="SnapAngle_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7041a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7041a-114">Elements and attributes</span></span>

<span data-ttu-id="7041a-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="7041a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="7041a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7041a-116">Parent elements</span></span>

|<span data-ttu-id="7041a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="7041a-117">**Element**</span></span>|<span data-ttu-id="7041a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="7041a-118">**Type**</span></span>|<span data-ttu-id="7041a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="7041a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7041a-120">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="7041a-120">SnapAngles</span></span>](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7041a-121">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="7041a-121">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7041a-122">包含**SnapAngle**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="7041a-122">Contains a collection of **SnapAngle** elements.</span></span>  <br/> |
|[<span data-ttu-id="7041a-123">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="7041a-123">SnapAngles</span></span>](snapangles-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7041a-124">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="7041a-124">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7041a-125">包含**SnapAngle**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="7041a-125">Contains a collection of **SnapAngle** elements.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="7041a-126">子元素</span><span class="sxs-lookup"><span data-stu-id="7041a-126">Child elements</span></span>

<span data-ttu-id="7041a-127">无。</span><span class="sxs-lookup"><span data-stu-id="7041a-127">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="7041a-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="7041a-128">Attributes</span></span>

<span data-ttu-id="7041a-129">无。</span><span class="sxs-lookup"><span data-stu-id="7041a-129">None.</span></span>
  

