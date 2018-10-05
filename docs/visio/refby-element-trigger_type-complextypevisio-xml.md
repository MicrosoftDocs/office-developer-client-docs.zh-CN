---
title: RefBy 元素 （Trigger_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09f2430a-184d-eaa2-2cb9-51bb24345c51
description: 指定绘图中的页面的引用。
ms.openlocfilehash: d987825345b64bd6e202970fc786aedaf49c6a94
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383315"
---
# <a name="refby-element-triggertype-complextype-visio-xml"></a><span data-ttu-id="62019-103">RefBy 元素 （Trigger_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="62019-103">RefBy element (Trigger_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="62019-104">指定绘图中的页面的引用。</span><span class="sxs-lookup"><span data-stu-id="62019-104">Specifies a reference to a page in the drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="62019-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="62019-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="62019-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="62019-106">**Element type**</span></span> <br/> |[<span data-ttu-id="62019-107">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="62019-107">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="62019-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="62019-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="62019-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="62019-109">**Schema file**</span></span> <br/> |<span data-ttu-id="62019-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="62019-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="62019-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="62019-111">**Document parts**</span></span> <br/> ||
   
## <a name="definition"></a><span data-ttu-id="62019-112">定义</span><span class="sxs-lookup"><span data-stu-id="62019-112">Definition</span></span>

```XML
< xs:element name="RefBy" type="RefBy_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="62019-113">元素和属性</span><span class="sxs-lookup"><span data-stu-id="62019-113">Elements and attributes</span></span>

<span data-ttu-id="62019-114">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="62019-114">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="62019-115">父元素</span><span class="sxs-lookup"><span data-stu-id="62019-115">Parent elements</span></span>

|<span data-ttu-id="62019-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="62019-116">**Element**</span></span>|<span data-ttu-id="62019-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="62019-117">**Type**</span></span>|<span data-ttu-id="62019-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="62019-118">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="62019-119">Trigger</span><span class="sxs-lookup"><span data-stu-id="62019-119">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="62019-120">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="62019-120">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="62019-121">提供对 Microsoft Visio 重新计算 Visio 文件中的文档部件之间的关系的说明。</span><span class="sxs-lookup"><span data-stu-id="62019-121">Provides instructions to Microsoft Visio to recalculate a relationship between document parts in a Visio file.</span></span>  <br/> |

   
### <a name="child-elements"></a><span data-ttu-id="62019-122">子元素</span><span class="sxs-lookup"><span data-stu-id="62019-122">Child elements</span></span>

<span data-ttu-id="62019-123">无。</span><span class="sxs-lookup"><span data-stu-id="62019-123">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="62019-124">属性</span><span class="sxs-lookup"><span data-stu-id="62019-124">Attributes</span></span>

|<span data-ttu-id="62019-125">**属性**</span><span class="sxs-lookup"><span data-stu-id="62019-125">**Attribute**</span></span>|<span data-ttu-id="62019-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="62019-126">**Type**</span></span>|<span data-ttu-id="62019-127">**必需**</span><span class="sxs-lookup"><span data-stu-id="62019-127">**Required**</span></span>|<span data-ttu-id="62019-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="62019-128">**Description**</span></span>|<span data-ttu-id="62019-129">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="62019-129">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62019-130">ID</span><span class="sxs-lookup"><span data-stu-id="62019-130">ID</span></span>  <br/> |<span data-ttu-id="62019-131">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="62019-131">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="62019-132">必需</span><span class="sxs-lookup"><span data-stu-id="62019-132">required</span></span>  <br/> |<span data-ttu-id="62019-133">指定在绘图页的 ID 属性。</span><span class="sxs-lookup"><span data-stu-id="62019-133">Specifies the ID attribute of a page in the drawing.</span></span>  <br/> |<span data-ttu-id="62019-134">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62019-134">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="62019-135">T</span><span class="sxs-lookup"><span data-stu-id="62019-135">T</span></span>  <br/> |<span data-ttu-id="62019-136">xsd: string</span><span class="sxs-lookup"><span data-stu-id="62019-136">xsd:string</span></span>  <br/> |<span data-ttu-id="62019-137">必需</span><span class="sxs-lookup"><span data-stu-id="62019-137">required</span></span>  <br/> |<span data-ttu-id="62019-138">指定引用类型。</span><span class="sxs-lookup"><span data-stu-id="62019-138">Specifies the reference type.</span></span>  <br/> |<span data-ttu-id="62019-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62019-139">Values of the xsd:string type.</span></span>  <br/> |
   

