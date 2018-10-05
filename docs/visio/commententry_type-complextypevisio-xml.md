---
title: CommentEntry_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6d9e99b8-fcd6-f36b-960e-bcf3a23afe04
ms.openlocfilehash: eabfe218414874cdc7f10234ed6eeb1fa2f75cf4
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384792"
---
# <a name="commententrytype-complextype-visio-xml"></a><span data-ttu-id="4ee7e-102">CommentEntry_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4ee7e-102">CommentEntry_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="4ee7e-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="4ee7e-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4ee7e-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4ee7e-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="4ee7e-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4ee7e-105">**Schema file**</span></span> <br/> |<span data-ttu-id="4ee7e-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="4ee7e-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="4ee7e-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="4ee7e-107">**Extension base**</span></span> <br/> |<span data-ttu-id="4ee7e-108">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4ee7e-108">xsd:string</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4ee7e-109">定义</span><span class="sxs-lookup"><span data-stu-id="4ee7e-109">Definition</span></span>

```XML
      <xs:complexType name="CommentEntry_Type">
        <xs:complexContent>
        <xs:extension base="xsd:string">
      
    <xs:attribute name="AuthorID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="PageID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ShapeID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Date"
  type="xsd:dateTime"
     use="required"
    />
    <xs:attribute name="EditDate"
  type="xsd:dateTime"
    />
    <xs:attribute name="Done"
  type="xsd:boolean"
    />
    <xs:attribute name="CommentID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="AutoCommentType"
  type="xsd:unsignedInt"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4ee7e-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4ee7e-110">Elements and attributes</span></span>

<span data-ttu-id="4ee7e-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="4ee7e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4ee7e-112">Child elements</span></span>

<span data-ttu-id="4ee7e-113">无。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4ee7e-114">属性</span><span class="sxs-lookup"><span data-stu-id="4ee7e-114">Attributes</span></span>

|<span data-ttu-id="4ee7e-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="4ee7e-115">**Attribute**</span></span>|<span data-ttu-id="4ee7e-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="4ee7e-116">**Type**</span></span>|<span data-ttu-id="4ee7e-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="4ee7e-117">**Required**</span></span>|<span data-ttu-id="4ee7e-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ee7e-118">**Description**</span></span>|<span data-ttu-id="4ee7e-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4ee7e-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ee7e-120">作者 Id</span><span class="sxs-lookup"><span data-stu-id="4ee7e-120">AuthorID</span></span>  <br/> |<span data-ttu-id="4ee7e-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ee7e-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ee7e-122">必需</span><span class="sxs-lookup"><span data-stu-id="4ee7e-122">required</span></span>  <br/> ||<span data-ttu-id="4ee7e-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4ee7e-124">AutoCommentType</span><span class="sxs-lookup"><span data-stu-id="4ee7e-124">AutoCommentType</span></span>  <br/> |<span data-ttu-id="4ee7e-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ee7e-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ee7e-126">可选</span><span class="sxs-lookup"><span data-stu-id="4ee7e-126">optional</span></span>  <br/> ||<span data-ttu-id="4ee7e-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4ee7e-128">CommentID</span><span class="sxs-lookup"><span data-stu-id="4ee7e-128">CommentID</span></span>  <br/> |<span data-ttu-id="4ee7e-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ee7e-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ee7e-130">必需</span><span class="sxs-lookup"><span data-stu-id="4ee7e-130">required</span></span>  <br/> ||<span data-ttu-id="4ee7e-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4ee7e-132">Date</span><span class="sxs-lookup"><span data-stu-id="4ee7e-132">Date</span></span>  <br/> |<span data-ttu-id="4ee7e-133">化</span><span class="sxs-lookup"><span data-stu-id="4ee7e-133">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="4ee7e-134">必需</span><span class="sxs-lookup"><span data-stu-id="4ee7e-134">required</span></span>  <br/> ||<span data-ttu-id="4ee7e-135">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-135">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="4ee7e-136">完成</span><span class="sxs-lookup"><span data-stu-id="4ee7e-136">Done</span></span>  <br/> |<span data-ttu-id="4ee7e-137">化</span><span class="sxs-lookup"><span data-stu-id="4ee7e-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="4ee7e-138">可选</span><span class="sxs-lookup"><span data-stu-id="4ee7e-138">optional</span></span>  <br/> ||<span data-ttu-id="4ee7e-139">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="4ee7e-140">EditDate</span><span class="sxs-lookup"><span data-stu-id="4ee7e-140">EditDate</span></span>  <br/> |<span data-ttu-id="4ee7e-141">化</span><span class="sxs-lookup"><span data-stu-id="4ee7e-141">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="4ee7e-142">可选</span><span class="sxs-lookup"><span data-stu-id="4ee7e-142">optional</span></span>  <br/> ||<span data-ttu-id="4ee7e-143">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-143">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="4ee7e-144">PageID</span><span class="sxs-lookup"><span data-stu-id="4ee7e-144">PageID</span></span>  <br/> |<span data-ttu-id="4ee7e-145">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ee7e-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ee7e-146">必需</span><span class="sxs-lookup"><span data-stu-id="4ee7e-146">required</span></span>  <br/> ||<span data-ttu-id="4ee7e-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4ee7e-148">ShapeID</span><span class="sxs-lookup"><span data-stu-id="4ee7e-148">ShapeID</span></span>  <br/> |<span data-ttu-id="4ee7e-149">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ee7e-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ee7e-150">可选</span><span class="sxs-lookup"><span data-stu-id="4ee7e-150">optional</span></span>  <br/> ||<span data-ttu-id="4ee7e-151">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ee7e-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

