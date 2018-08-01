---
title: CommentEntry_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6d9e99b8-fcd6-f36b-960e-bcf3a23afe04
ms.openlocfilehash: 5ee3c9f2aa8b0af91289ce1cd6bb2355adec3426
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779905"
---
# <a name="commententrytype-complextype-visio-xml"></a><span data-ttu-id="38bd1-102">CommentEntry_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="38bd1-102">CommentEntry_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="38bd1-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="38bd1-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="38bd1-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="38bd1-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="38bd1-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="38bd1-105">**Schema file**</span></span> <br/> |<span data-ttu-id="38bd1-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="38bd1-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="38bd1-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="38bd1-107">**Extension base**</span></span> <br/> |<span data-ttu-id="38bd1-108">xsd: string</span><span class="sxs-lookup"><span data-stu-id="38bd1-108">xsd:string</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="38bd1-109">定义</span><span class="sxs-lookup"><span data-stu-id="38bd1-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="38bd1-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="38bd1-110">Elements and attributes</span></span>

<span data-ttu-id="38bd1-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="38bd1-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="38bd1-112">子元素</span><span class="sxs-lookup"><span data-stu-id="38bd1-112">Child elements</span></span>

<span data-ttu-id="38bd1-113">无。</span><span class="sxs-lookup"><span data-stu-id="38bd1-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="38bd1-114">属性</span><span class="sxs-lookup"><span data-stu-id="38bd1-114">Attributes</span></span>

|<span data-ttu-id="38bd1-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="38bd1-115">**Attribute**</span></span>|<span data-ttu-id="38bd1-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="38bd1-116">**Type**</span></span>|<span data-ttu-id="38bd1-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="38bd1-117">**Required**</span></span>|<span data-ttu-id="38bd1-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="38bd1-118">**Description**</span></span>|<span data-ttu-id="38bd1-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="38bd1-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38bd1-120">作者 Id</span><span class="sxs-lookup"><span data-stu-id="38bd1-120">AuthorID</span></span>  <br/> |<span data-ttu-id="38bd1-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="38bd1-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="38bd1-122">必需</span><span class="sxs-lookup"><span data-stu-id="38bd1-122">required</span></span>  <br/> ||<span data-ttu-id="38bd1-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="38bd1-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="38bd1-124">AutoCommentType</span><span class="sxs-lookup"><span data-stu-id="38bd1-124">AutoCommentType</span></span>  <br/> |<span data-ttu-id="38bd1-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="38bd1-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="38bd1-126">可选</span><span class="sxs-lookup"><span data-stu-id="38bd1-126">optional</span></span>  <br/> ||<span data-ttu-id="38bd1-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="38bd1-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="38bd1-128">CommentID</span><span class="sxs-lookup"><span data-stu-id="38bd1-128">CommentID</span></span>  <br/> |<span data-ttu-id="38bd1-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="38bd1-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="38bd1-130">必需</span><span class="sxs-lookup"><span data-stu-id="38bd1-130">required</span></span>  <br/> ||<span data-ttu-id="38bd1-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="38bd1-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="38bd1-132">Date</span><span class="sxs-lookup"><span data-stu-id="38bd1-132">Date</span></span>  <br/> |<span data-ttu-id="38bd1-133">化</span><span class="sxs-lookup"><span data-stu-id="38bd1-133">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="38bd1-134">必需</span><span class="sxs-lookup"><span data-stu-id="38bd1-134">required</span></span>  <br/> ||<span data-ttu-id="38bd1-135">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="38bd1-135">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="38bd1-136">完成</span><span class="sxs-lookup"><span data-stu-id="38bd1-136">Done</span></span>  <br/> |<span data-ttu-id="38bd1-137">化</span><span class="sxs-lookup"><span data-stu-id="38bd1-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="38bd1-138">可选</span><span class="sxs-lookup"><span data-stu-id="38bd1-138">optional</span></span>  <br/> ||<span data-ttu-id="38bd1-139">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="38bd1-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="38bd1-140">EditDate</span><span class="sxs-lookup"><span data-stu-id="38bd1-140">EditDate</span></span>  <br/> |<span data-ttu-id="38bd1-141">化</span><span class="sxs-lookup"><span data-stu-id="38bd1-141">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="38bd1-142">可选</span><span class="sxs-lookup"><span data-stu-id="38bd1-142">optional</span></span>  <br/> ||<span data-ttu-id="38bd1-143">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="38bd1-143">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="38bd1-144">PageID</span><span class="sxs-lookup"><span data-stu-id="38bd1-144">PageID</span></span>  <br/> |<span data-ttu-id="38bd1-145">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="38bd1-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="38bd1-146">必需</span><span class="sxs-lookup"><span data-stu-id="38bd1-146">required</span></span>  <br/> ||<span data-ttu-id="38bd1-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="38bd1-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="38bd1-148">ShapeID</span><span class="sxs-lookup"><span data-stu-id="38bd1-148">ShapeID</span></span>  <br/> |<span data-ttu-id="38bd1-149">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="38bd1-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="38bd1-150">可选</span><span class="sxs-lookup"><span data-stu-id="38bd1-150">optional</span></span>  <br/> ||<span data-ttu-id="38bd1-151">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="38bd1-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

