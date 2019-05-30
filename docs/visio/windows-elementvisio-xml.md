---
title: Windows 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1880734a-f086-ce6c-5a93-47851bcdd99d
description: 包含文档的 Window 元素。
ms.openlocfilehash: fcffcd5257b14c0ae0203a41f369536e583c1798
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538443"
---
# <a name="windows-element-visio-xml"></a><span data-ttu-id="ad5df-103">Windows 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ad5df-103">Windows element (Visio XML)</span></span>

<span data-ttu-id="ad5df-104">包含文档的**Window**元素。</span><span class="sxs-lookup"><span data-stu-id="ad5df-104">Contains the **Window** elements for a document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="ad5df-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="ad5df-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ad5df-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="ad5df-106">**Element type**</span></span> <br/> |[<span data-ttu-id="ad5df-107">Windows_Type</span><span class="sxs-lookup"><span data-stu-id="ad5df-107">Windows_Type</span></span>](windows_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="ad5df-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ad5df-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="ad5df-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ad5df-109">**Schema file**</span></span> <br/> |<span data-ttu-id="ad5df-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="ad5df-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="ad5df-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="ad5df-111">**Document parts**</span></span> <br/> |<span data-ttu-id="ad5df-112">windows .xml</span><span class="sxs-lookup"><span data-stu-id="ad5df-112">windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ad5df-113">定义</span><span class="sxs-lookup"><span data-stu-id="ad5df-113">Definition</span></span>

```XML
<xs:element name="Windows" type="Windows_Type" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ad5df-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ad5df-114">Elements and attributes</span></span>

<span data-ttu-id="ad5df-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="ad5df-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="ad5df-116">父元素</span><span class="sxs-lookup"><span data-stu-id="ad5df-116">Parent elements</span></span>

<span data-ttu-id="ad5df-117">无。</span><span class="sxs-lookup"><span data-stu-id="ad5df-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ad5df-118">子元素</span><span class="sxs-lookup"><span data-stu-id="ad5df-118">Child elements</span></span>

|<span data-ttu-id="ad5df-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="ad5df-119">**Element**</span></span>|<span data-ttu-id="ad5df-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="ad5df-120">**Type**</span></span>|<span data-ttu-id="ad5df-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="ad5df-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ad5df-122">Window</span><span class="sxs-lookup"><span data-stu-id="ad5df-122">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ad5df-123">Window_Type</span><span class="sxs-lookup"><span data-stu-id="ad5df-123">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ad5df-124">代表 Microsoft Visio 实例中打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="ad5df-124">Represents an open window in a Microsoft Visio instance.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="ad5df-125">属性</span><span class="sxs-lookup"><span data-stu-id="ad5df-125">Attributes</span></span>

|<span data-ttu-id="ad5df-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="ad5df-126">**Attribute**</span></span>|<span data-ttu-id="ad5df-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="ad5df-127">**Type**</span></span>|<span data-ttu-id="ad5df-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="ad5df-128">**Required**</span></span>|<span data-ttu-id="ad5df-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="ad5df-129">**Description**</span></span>|<span data-ttu-id="ad5df-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ad5df-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad5df-131">ClientHeight</span><span class="sxs-lookup"><span data-stu-id="ad5df-131">ClientHeight</span></span>  <br/> |<span data-ttu-id="ad5df-132">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="ad5df-132">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="ad5df-133">可选</span><span class="sxs-lookup"><span data-stu-id="ad5df-133">optional</span></span>  <br/> |<span data-ttu-id="ad5df-134">表示显示区域的高度尺寸</span><span class="sxs-lookup"><span data-stu-id="ad5df-134">Represents the height dimension of a display area</span></span>  <br/> |<span data-ttu-id="ad5df-135">Xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ad5df-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="ad5df-136">ClientWidth</span><span class="sxs-lookup"><span data-stu-id="ad5df-136">ClientWidth</span></span>  <br/> |<span data-ttu-id="ad5df-137">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="ad5df-137">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="ad5df-138">可选</span><span class="sxs-lookup"><span data-stu-id="ad5df-138">optional</span></span>  <br/> |<span data-ttu-id="ad5df-139">表示显示区域的宽度尺寸</span><span class="sxs-lookup"><span data-stu-id="ad5df-139">Represents the width dimension of a display area</span></span>  <br/> |<span data-ttu-id="ad5df-140">Xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ad5df-140">Values of the xsd:unsignedShort type.</span></span>  <br/> |
   

