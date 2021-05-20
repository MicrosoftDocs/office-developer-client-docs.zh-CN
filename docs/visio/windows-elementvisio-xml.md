---
title: 'Windows XML (Visio元素) '
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
# <a name="windows-element-visio-xml"></a><span data-ttu-id="f0edc-103">Windows XML (Visio元素) </span><span class="sxs-lookup"><span data-stu-id="f0edc-103">Windows element (Visio XML)</span></span>

<span data-ttu-id="f0edc-104">包含 **文档的 Window** 元素。</span><span class="sxs-lookup"><span data-stu-id="f0edc-104">Contains the **Window** elements for a document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="f0edc-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f0edc-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f0edc-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f0edc-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f0edc-107">Windows_Type</span><span class="sxs-lookup"><span data-stu-id="f0edc-107">Windows_Type</span></span>](windows_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f0edc-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f0edc-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f0edc-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f0edc-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f0edc-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="f0edc-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f0edc-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f0edc-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f0edc-112">windows.xml</span><span class="sxs-lookup"><span data-stu-id="f0edc-112">windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f0edc-113">定义</span><span class="sxs-lookup"><span data-stu-id="f0edc-113">Definition</span></span>

```XML
<xs:element name="Windows" type="Windows_Type" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f0edc-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f0edc-114">Elements and attributes</span></span>

<span data-ttu-id="f0edc-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f0edc-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f0edc-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f0edc-116">Parent elements</span></span>

<span data-ttu-id="f0edc-117">无。</span><span class="sxs-lookup"><span data-stu-id="f0edc-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f0edc-118">子元素</span><span class="sxs-lookup"><span data-stu-id="f0edc-118">Child elements</span></span>

|<span data-ttu-id="f0edc-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="f0edc-119">**Element**</span></span>|<span data-ttu-id="f0edc-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="f0edc-120">**Type**</span></span>|<span data-ttu-id="f0edc-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="f0edc-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f0edc-122">Window</span><span class="sxs-lookup"><span data-stu-id="f0edc-122">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f0edc-123">Window_Type</span><span class="sxs-lookup"><span data-stu-id="f0edc-123">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f0edc-124">代表 Microsoft Visio 实例中打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="f0edc-124">Represents an open window in a Microsoft Visio instance.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f0edc-125">属性</span><span class="sxs-lookup"><span data-stu-id="f0edc-125">Attributes</span></span>

|<span data-ttu-id="f0edc-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="f0edc-126">**Attribute**</span></span>|<span data-ttu-id="f0edc-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="f0edc-127">**Type**</span></span>|<span data-ttu-id="f0edc-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="f0edc-128">**Required**</span></span>|<span data-ttu-id="f0edc-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="f0edc-129">**Description**</span></span>|<span data-ttu-id="f0edc-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f0edc-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f0edc-131">ClientHeight</span><span class="sxs-lookup"><span data-stu-id="f0edc-131">ClientHeight</span></span>  <br/> |<span data-ttu-id="f0edc-132">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f0edc-132">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f0edc-133">可选</span><span class="sxs-lookup"><span data-stu-id="f0edc-133">optional</span></span>  <br/> |<span data-ttu-id="f0edc-134">表示显示区域的高度尺寸</span><span class="sxs-lookup"><span data-stu-id="f0edc-134">Represents the height dimension of a display area</span></span>  <br/> |<span data-ttu-id="f0edc-135">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f0edc-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f0edc-136">ClientWidth</span><span class="sxs-lookup"><span data-stu-id="f0edc-136">ClientWidth</span></span>  <br/> |<span data-ttu-id="f0edc-137">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f0edc-137">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f0edc-138">可选</span><span class="sxs-lookup"><span data-stu-id="f0edc-138">optional</span></span>  <br/> |<span data-ttu-id="f0edc-139">表示显示区域的宽度尺寸</span><span class="sxs-lookup"><span data-stu-id="f0edc-139">Represents the width dimension of a display area</span></span>  <br/> |<span data-ttu-id="f0edc-140">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f0edc-140">Values of the xsd:unsignedShort type.</span></span>  <br/> |
   

