---
title: 'CommentEntry_Type XML (Visio复杂类型) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6d9e99b8-fcd6-f36b-960e-bcf3a23afe04
ms.openlocfilehash: 840f660d72acbda052d4729846d8a26686d82b2a
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540124"
---
# <a name="commententry_type-complextype-visio-xml"></a><span data-ttu-id="ba069-102">CommentEntry_Type XML (Visio复杂类型) </span><span class="sxs-lookup"><span data-stu-id="ba069-102">CommentEntry_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="ba069-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ba069-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ba069-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ba069-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ba069-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ba069-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ba069-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="ba069-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ba069-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ba069-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ba069-108">xsd：string</span><span class="sxs-lookup"><span data-stu-id="ba069-108">xsd:string</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ba069-109">定义</span><span class="sxs-lookup"><span data-stu-id="ba069-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="ba069-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ba069-110">Elements and attributes</span></span>

<span data-ttu-id="ba069-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ba069-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ba069-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ba069-112">Child elements</span></span>

<span data-ttu-id="ba069-113">无。</span><span class="sxs-lookup"><span data-stu-id="ba069-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ba069-114">属性</span><span class="sxs-lookup"><span data-stu-id="ba069-114">Attributes</span></span>

|<span data-ttu-id="ba069-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="ba069-115">**Attribute**</span></span>|<span data-ttu-id="ba069-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="ba069-116">**Type**</span></span>|<span data-ttu-id="ba069-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="ba069-117">**Required**</span></span>|<span data-ttu-id="ba069-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="ba069-118">**Description**</span></span>|<span data-ttu-id="ba069-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ba069-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ba069-120">AuthorID</span><span class="sxs-lookup"><span data-stu-id="ba069-120">AuthorID</span></span>  <br/> |<span data-ttu-id="ba069-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ba069-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ba069-122">必需</span><span class="sxs-lookup"><span data-stu-id="ba069-122">required</span></span>  <br/> ||<span data-ttu-id="ba069-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba069-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ba069-124">AutoCommentType</span><span class="sxs-lookup"><span data-stu-id="ba069-124">AutoCommentType</span></span>  <br/> |<span data-ttu-id="ba069-125">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ba069-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ba069-126">可选</span><span class="sxs-lookup"><span data-stu-id="ba069-126">optional</span></span>  <br/> ||<span data-ttu-id="ba069-127">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba069-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ba069-128">CommentID</span><span class="sxs-lookup"><span data-stu-id="ba069-128">CommentID</span></span>  <br/> |<span data-ttu-id="ba069-129">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ba069-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ba069-130">必需</span><span class="sxs-lookup"><span data-stu-id="ba069-130">required</span></span>  <br/> ||<span data-ttu-id="ba069-131">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba069-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ba069-132">日期</span><span class="sxs-lookup"><span data-stu-id="ba069-132">Date</span></span>  <br/> |<span data-ttu-id="ba069-133">xsd：dateTime</span><span class="sxs-lookup"><span data-stu-id="ba069-133">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="ba069-134">必需</span><span class="sxs-lookup"><span data-stu-id="ba069-134">required</span></span>  <br/> ||<span data-ttu-id="ba069-135">xsd：dateTime 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba069-135">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="ba069-136">完成</span><span class="sxs-lookup"><span data-stu-id="ba069-136">Done</span></span>  <br/> |<span data-ttu-id="ba069-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="ba069-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="ba069-138">可选</span><span class="sxs-lookup"><span data-stu-id="ba069-138">optional</span></span>  <br/> ||<span data-ttu-id="ba069-139">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba069-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="ba069-140">EditDate</span><span class="sxs-lookup"><span data-stu-id="ba069-140">EditDate</span></span>  <br/> |<span data-ttu-id="ba069-141">xsd：dateTime</span><span class="sxs-lookup"><span data-stu-id="ba069-141">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="ba069-142">可选</span><span class="sxs-lookup"><span data-stu-id="ba069-142">optional</span></span>  <br/> ||<span data-ttu-id="ba069-143">xsd：dateTime 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba069-143">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="ba069-144">PageID</span><span class="sxs-lookup"><span data-stu-id="ba069-144">PageID</span></span>  <br/> |<span data-ttu-id="ba069-145">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ba069-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ba069-146">必需</span><span class="sxs-lookup"><span data-stu-id="ba069-146">required</span></span>  <br/> ||<span data-ttu-id="ba069-147">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba069-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ba069-148">ShapeID</span><span class="sxs-lookup"><span data-stu-id="ba069-148">ShapeID</span></span>  <br/> |<span data-ttu-id="ba069-149">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ba069-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ba069-150">可选</span><span class="sxs-lookup"><span data-stu-id="ba069-150">optional</span></span>  <br/> ||<span data-ttu-id="ba069-151">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba069-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

