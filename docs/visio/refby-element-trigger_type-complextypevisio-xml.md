---
title: RefBy 元素 （Trigger_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09f2430a-184d-eaa2-2cb9-51bb24345c51
description: 指定绘图中的页面的引用。
ms.openlocfilehash: 57ac63c4488b68d3af3c6e4a75417e2c7937723c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781029"
---
# <a name="refby-element-triggertype-complextype-visio-xml"></a><span data-ttu-id="b0d6f-103">RefBy 元素 （Trigger_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b0d6f-103">RefBy element (Trigger_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="b0d6f-104">指定绘图中的页面的引用。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-104">Specifies a reference to a page in the drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b0d6f-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b0d6f-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b0d6f-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b0d6f-107">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="b0d6f-107">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b0d6f-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b0d6f-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b0d6f-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="b0d6f-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b0d6f-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-111">**Document parts**</span></span> <br/> ||
   
## <a name="definition"></a><span data-ttu-id="b0d6f-112">定义</span><span class="sxs-lookup"><span data-stu-id="b0d6f-112">Definition</span></span>

```XML
< xs:element name="RefBy" type="RefBy_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b0d6f-113">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b0d6f-113">Elements and attributes</span></span>

<span data-ttu-id="b0d6f-114">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-114">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b0d6f-115">父元素</span><span class="sxs-lookup"><span data-stu-id="b0d6f-115">Parent elements</span></span>

|<span data-ttu-id="b0d6f-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-116">**Element**</span></span>|<span data-ttu-id="b0d6f-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-117">**Type**</span></span>|<span data-ttu-id="b0d6f-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-118">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b0d6f-119">Trigger</span><span class="sxs-lookup"><span data-stu-id="b0d6f-119">Trigger</span></span>](http://msdn.microsoft.com/library/6dbd2c66-3b29-03f6-648f-723d359ded0d%28Office.15%29.aspx) <br/> |[<span data-ttu-id="b0d6f-120">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="b0d6f-120">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b0d6f-121">提供对 Microsoft Visio 重新计算 Visio 文件中的文档部件之间的关系的说明。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-121">Provides instructions to Microsoft Visio to recalculate a relationship between document parts in a Visio file.</span></span>  <br/> |
|[<span data-ttu-id="b0d6f-122">Trigger</span><span class="sxs-lookup"><span data-stu-id="b0d6f-122">Trigger</span></span>](http://msdn.microsoft.com/library/e4eeb238-f6d0-fb23-db1c-01d55b0a8d88%28Office.15%29.aspx) <br/> |[<span data-ttu-id="b0d6f-123">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="b0d6f-123">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b0d6f-124">提供对 Microsoft Visio 重新计算 Visio 文件中的文档部件之间的关系的说明。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-124">Provides instructions to Microsoft Visio to recalculate a relationship between document parts in a Visio file.</span></span>  <br/> |
|[<span data-ttu-id="b0d6f-125">Trigger</span><span class="sxs-lookup"><span data-stu-id="b0d6f-125">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="b0d6f-126">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="b0d6f-126">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b0d6f-127">提供对 Microsoft Visio 重新计算 Visio 文件中的文档部件之间的关系的说明。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-127">Provides instructions to Microsoft Visio to recalculate a relationship between document parts in a Visio file.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="b0d6f-128">子元素</span><span class="sxs-lookup"><span data-stu-id="b0d6f-128">Child elements</span></span>

<span data-ttu-id="b0d6f-129">无。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-129">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b0d6f-130">属性</span><span class="sxs-lookup"><span data-stu-id="b0d6f-130">Attributes</span></span>

|<span data-ttu-id="b0d6f-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-131">**Attribute**</span></span>|<span data-ttu-id="b0d6f-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-132">**Type**</span></span>|<span data-ttu-id="b0d6f-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-133">**Required**</span></span>|<span data-ttu-id="b0d6f-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-134">**Description**</span></span>|<span data-ttu-id="b0d6f-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b0d6f-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b0d6f-136">ID</span><span class="sxs-lookup"><span data-stu-id="b0d6f-136">ID</span></span>  <br/> |<span data-ttu-id="b0d6f-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b0d6f-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b0d6f-138">必需</span><span class="sxs-lookup"><span data-stu-id="b0d6f-138">required</span></span>  <br/> |<span data-ttu-id="b0d6f-139">指定在绘图页的 ID 属性。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-139">Specifies the ID attribute of a page in the drawing.</span></span>  <br/> |<span data-ttu-id="b0d6f-140">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b0d6f-141">T</span><span class="sxs-lookup"><span data-stu-id="b0d6f-141">T</span></span>  <br/> |<span data-ttu-id="b0d6f-142">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b0d6f-142">xsd:string</span></span>  <br/> |<span data-ttu-id="b0d6f-143">必需</span><span class="sxs-lookup"><span data-stu-id="b0d6f-143">required</span></span>  <br/> |<span data-ttu-id="b0d6f-144">指定引用类型。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-144">Specifies the reference type.</span></span>  <br/> |<span data-ttu-id="b0d6f-145">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b0d6f-145">Values of the xsd:string type.</span></span>  <br/> |
   

