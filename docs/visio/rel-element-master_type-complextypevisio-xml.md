---
title: Rel 元素 （Master_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 151cdd13-d00b-249c-7ebd-1ae9c4042b03
description: 指定相应的主 XML 与部件的关系。
ms.openlocfilehash: 8cd16c55b24cd6edec993cb913709beff72ee325
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781046"
---
# <a name="rel-element-mastertype-complextype-visio-xml"></a><span data-ttu-id="5f17c-103">Rel 元素 （Master_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5f17c-103">Rel element (Master_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="5f17c-104">指定相应的主 XML 与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="5f17c-104">Specifies a relationship to a part with the corresponding master XML.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="5f17c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="5f17c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5f17c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="5f17c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="5f17c-107">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="5f17c-107">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="5f17c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5f17c-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="5f17c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5f17c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="5f17c-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="5f17c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="5f17c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="5f17c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="5f17c-112">pages.xml、 masters.xml、 recordsets.xml、 页 #.xml、 主 #.xml</span><span class="sxs-lookup"><span data-stu-id="5f17c-112">pages.xml, masters.xml, recordsets.xml, page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5f17c-113">定义</span><span class="sxs-lookup"><span data-stu-id="5f17c-113">Definition</span></span>

```XML
< xs:element name="Rel"  type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5f17c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5f17c-114">Elements and attributes</span></span>

<span data-ttu-id="5f17c-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5f17c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="5f17c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="5f17c-116">Parent elements</span></span>

|<span data-ttu-id="5f17c-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="5f17c-117">**Element**</span></span>|<span data-ttu-id="5f17c-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="5f17c-118">**Type**</span></span>|<span data-ttu-id="5f17c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f17c-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5f17c-120">Master</span><span class="sxs-lookup"><span data-stu-id="5f17c-120">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5f17c-121">Master_Type</span><span class="sxs-lookup"><span data-stu-id="5f17c-121">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5f17c-122">指定存储在绘图中的主 XML 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="5f17c-122">Specifies one instance of master XML stored in the drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="5f17c-123">子元素</span><span class="sxs-lookup"><span data-stu-id="5f17c-123">Child elements</span></span>

<span data-ttu-id="5f17c-124">无。</span><span class="sxs-lookup"><span data-stu-id="5f17c-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5f17c-125">属性</span><span class="sxs-lookup"><span data-stu-id="5f17c-125">Attributes</span></span>

|<span data-ttu-id="5f17c-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="5f17c-126">**Attribute**</span></span>|<span data-ttu-id="5f17c-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="5f17c-127">**Type**</span></span>|<span data-ttu-id="5f17c-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="5f17c-128">**Required**</span></span>|<span data-ttu-id="5f17c-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f17c-129">**Description**</span></span>|<span data-ttu-id="5f17c-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5f17c-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f17c-131">r: id</span><span class="sxs-lookup"><span data-stu-id="5f17c-131">r:id</span></span>  <br/> |<span data-ttu-id="5f17c-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5f17c-132">xsd:string</span></span>  <br/> <span data-ttu-id="5f17c-133">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="5f17c-133">See Remarks.</span></span>  <br/> |<span data-ttu-id="5f17c-134">必需</span><span class="sxs-lookup"><span data-stu-id="5f17c-134">required</span></span>  <br/> |<span data-ttu-id="5f17c-135">指定与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="5f17c-135">Specifies a relationship to a part.</span></span>  <br/> |<span data-ttu-id="5f17c-136">"删除 #"</span><span class="sxs-lookup"><span data-stu-id="5f17c-136">"rId#"</span></span>  <br/> <span data-ttu-id="5f17c-137">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="5f17c-137">See Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5f17c-138">说明</span><span class="sxs-lookup"><span data-stu-id="5f17c-138">Remarks</span></span>

<span data-ttu-id="5f17c-139">**R: id**属性的值必须是**ST_RelationshipID**类型。</span><span class="sxs-lookup"><span data-stu-id="5f17c-139">The value of the **r:id** attribute must be an **ST_RelationshipID** type.</span></span> <span data-ttu-id="5f17c-140">**ST_RelationshipID**类型是一个 string 类型的值必须是格式为删除的 #，最后一个字符必须数字。</span><span class="sxs-lookup"><span data-stu-id="5f17c-140">The **ST_RelationshipID** type is a string that must be in the format 'rId#', where the final character must be a number.</span></span> <span data-ttu-id="5f17c-141">号码必须是唯一的**Rel**元素的所有同级元素。</span><span class="sxs-lookup"><span data-stu-id="5f17c-141">The number must be unique among all sibling elements of the **Rel** element.</span></span> 
  
<span data-ttu-id="5f17c-142">有关 ST_RelationshipID 类型的详细信息，请参阅[第 1 部分 ISO/IEC 29500 规范](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。</span><span class="sxs-lookup"><span data-stu-id="5f17c-142">For more information about the ST_RelationshipID type, see the [ISO/IEC 29500 Part 1 specification](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).</span></span>
  

