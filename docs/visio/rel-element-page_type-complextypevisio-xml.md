---
title: Rel 元素 (Page_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d61b1b97-c360-4d9d-217f-e6f45f760e42
description: 指定与具有相应的网页 XML 的部件的关系。
ms.openlocfilehash: 7a45764817175f670cdb009157e21a1a25f31cc5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319997"
---
# <a name="rel-element-pagetype-complextype-visio-xml"></a><span data-ttu-id="c2335-103">Rel 元素 (Page_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="c2335-103">Rel element (Page_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="c2335-104">指定与具有相应的网页 XML 的部件的关系。</span><span class="sxs-lookup"><span data-stu-id="c2335-104">Specifies a relationship to a part with the corresponding page XML.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c2335-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c2335-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c2335-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c2335-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c2335-107">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="c2335-107">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c2335-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c2335-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c2335-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c2335-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c2335-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="c2335-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c2335-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c2335-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c2335-112">pages. .xml、xml、recordset、.xml、第 .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="c2335-112">pages.xml, masters.xml, recordsets.xml, page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c2335-113">定义</span><span class="sxs-lookup"><span data-stu-id="c2335-113">Definition</span></span>

```XML
< xs:element name="Rel" type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c2335-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c2335-114">Elements and attributes</span></span>

<span data-ttu-id="c2335-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="c2335-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c2335-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c2335-116">Parent elements</span></span>

|<span data-ttu-id="c2335-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c2335-117">**Element**</span></span>|<span data-ttu-id="c2335-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c2335-118">**Type**</span></span>|<span data-ttu-id="c2335-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c2335-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c2335-120">Page</span><span class="sxs-lookup"><span data-stu-id="c2335-120">Page</span></span>](page-element-pages_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c2335-121">Page_Type</span><span class="sxs-lookup"><span data-stu-id="c2335-121">Page_Type</span></span>](page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c2335-122">指定存储在绘图中的页面 XML 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="c2335-122">Specifies one instance of page XML stored in the drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c2335-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c2335-123">Child elements</span></span>

<span data-ttu-id="c2335-124">无。</span><span class="sxs-lookup"><span data-stu-id="c2335-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c2335-125">属性</span><span class="sxs-lookup"><span data-stu-id="c2335-125">Attributes</span></span>

|<span data-ttu-id="c2335-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="c2335-126">**Attribute**</span></span>|<span data-ttu-id="c2335-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="c2335-127">**Type**</span></span>|<span data-ttu-id="c2335-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="c2335-128">**Required**</span></span>|<span data-ttu-id="c2335-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="c2335-129">**Description**</span></span>|<span data-ttu-id="c2335-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c2335-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2335-131">r:id</span><span class="sxs-lookup"><span data-stu-id="c2335-131">r:id</span></span>  <br/> |<span data-ttu-id="c2335-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c2335-132">xsd:string</span></span>  <br/> <span data-ttu-id="c2335-133">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="c2335-133">See Remarks.</span></span>  <br/> |<span data-ttu-id="c2335-134">必需</span><span class="sxs-lookup"><span data-stu-id="c2335-134">required</span></span>  <br/> |<span data-ttu-id="c2335-135">指定与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="c2335-135">Specifies a relationship to a part.</span></span>  <br/> |<span data-ttu-id="c2335-136">"rId #"</span><span class="sxs-lookup"><span data-stu-id="c2335-136">"rId#"</span></span>  <br/> <span data-ttu-id="c2335-137">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="c2335-137">See Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c2335-138">注解</span><span class="sxs-lookup"><span data-stu-id="c2335-138">Remarks</span></span>

<span data-ttu-id="c2335-139">**r:id**属性的值必须是**ST_RelationshipID**类型。</span><span class="sxs-lookup"><span data-stu-id="c2335-139">The value of the **r:id** attribute must be an **ST_RelationshipID** type.</span></span> <span data-ttu-id="c2335-140">**ST_RelationshipID**类型是一个必须采用 "rId #" 格式的字符串, 其中最后一个字符必须是数字。</span><span class="sxs-lookup"><span data-stu-id="c2335-140">The **ST_RelationshipID** type is a string that must be in the format 'rId#', where the final character must be a number.</span></span> <span data-ttu-id="c2335-141">该数字在**Rel**元素的所有同辈元素中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c2335-141">The number must be unique among all sibling elements of the **Rel** element.</span></span> 
  
<span data-ttu-id="c2335-142">有关 ST_RelationshipID 类型的详细信息, 请参阅[ISO/IEC 29500 第1部分规范](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。</span><span class="sxs-lookup"><span data-stu-id="c2335-142">For more information about the ST_RelationshipID type, see the [ISO/IEC 29500 Part 1 specification](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).</span></span>
  

