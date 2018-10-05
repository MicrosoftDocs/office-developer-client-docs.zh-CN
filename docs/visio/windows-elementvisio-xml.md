---
title: Windows 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1880734a-f086-ce6c-5a93-47851bcdd99d
description: 包含文档的窗口元素。
ms.openlocfilehash: df4d4bc48db157bd05fd39177975c9dbeaa5de52
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386801"
---
# <a name="windows-element-visio-xml"></a><span data-ttu-id="265f9-103">Windows 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="265f9-103">Windows element ('Visio XML')</span></span>

<span data-ttu-id="265f9-104">包含文档的**窗口**元素。</span><span class="sxs-lookup"><span data-stu-id="265f9-104">Contains the **Window** elements for a document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="265f9-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="265f9-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="265f9-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="265f9-106">**Element type**</span></span> <br/> |[<span data-ttu-id="265f9-107">Windows_Type</span><span class="sxs-lookup"><span data-stu-id="265f9-107">Windows_Type</span></span>](windows_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="265f9-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="265f9-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="265f9-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="265f9-109">**Schema file**</span></span> <br/> |<span data-ttu-id="265f9-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="265f9-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="265f9-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="265f9-111">**Document parts**</span></span> <br/> |<span data-ttu-id="265f9-112">windows.xml</span><span class="sxs-lookup"><span data-stu-id="265f9-112">windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="265f9-113">定义</span><span class="sxs-lookup"><span data-stu-id="265f9-113">Definition</span></span>

```XML
<xs:element name="Windows" type="Windows_Type" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="265f9-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="265f9-114">Elements and attributes</span></span>

<span data-ttu-id="265f9-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="265f9-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="265f9-116">父元素</span><span class="sxs-lookup"><span data-stu-id="265f9-116">Parent elements</span></span>

<span data-ttu-id="265f9-117">无。</span><span class="sxs-lookup"><span data-stu-id="265f9-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="265f9-118">子元素</span><span class="sxs-lookup"><span data-stu-id="265f9-118">Child elements</span></span>

|<span data-ttu-id="265f9-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="265f9-119">**Element**</span></span>|<span data-ttu-id="265f9-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="265f9-120">**Type**</span></span>|<span data-ttu-id="265f9-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="265f9-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="265f9-122">Window</span><span class="sxs-lookup"><span data-stu-id="265f9-122">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="265f9-123">Window_Type</span><span class="sxs-lookup"><span data-stu-id="265f9-123">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="265f9-124">代表 Microsoft Visio 实例中打开的窗口。
</span><span class="sxs-lookup"><span data-stu-id="265f9-124">Represents an open window in a Microsoft Visio instance.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="265f9-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="265f9-125">Attributes</span></span>

|<span data-ttu-id="265f9-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="265f9-126">**Attribute**</span></span>|<span data-ttu-id="265f9-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="265f9-127">**Type**</span></span>|<span data-ttu-id="265f9-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="265f9-128">**Required**</span></span>|<span data-ttu-id="265f9-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="265f9-129">**Description**</span></span>|<span data-ttu-id="265f9-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="265f9-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="265f9-131">ClientHeight</span><span class="sxs-lookup"><span data-stu-id="265f9-131">ClientHeight</span></span>  <br/> |<span data-ttu-id="265f9-132">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="265f9-132">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="265f9-133">可选</span><span class="sxs-lookup"><span data-stu-id="265f9-133">optional</span></span>  <br/> |<span data-ttu-id="265f9-134">代表尺寸显示区域的高度</span><span class="sxs-lookup"><span data-stu-id="265f9-134">Represents the height dimension of a display area</span></span>  <br/> |<span data-ttu-id="265f9-135">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="265f9-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="265f9-136">ClientWidth</span><span class="sxs-lookup"><span data-stu-id="265f9-136">ClientWidth</span></span>  <br/> |<span data-ttu-id="265f9-137">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="265f9-137">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="265f9-138">可选</span><span class="sxs-lookup"><span data-stu-id="265f9-138">optional</span></span>  <br/> |<span data-ttu-id="265f9-139">代表显示区域的宽度维度</span><span class="sxs-lookup"><span data-stu-id="265f9-139">Represents the width dimension of a display area</span></span>  <br/> |<span data-ttu-id="265f9-140">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="265f9-140">Values of the xsd:unsignedShort type.</span></span>  <br/> |
   

