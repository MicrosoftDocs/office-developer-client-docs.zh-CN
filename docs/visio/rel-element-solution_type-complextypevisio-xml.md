---
title: Rel 元素 （Solution_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8438fe4b-f5f7-d4e4-58b7-7ebdc1da197a
description: 指定与此解决方案的 XML 关联的解决方案与部件的关系。
ms.openlocfilehash: e8a1350691e8d29551fb126a2151655175cc068c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400787"
---
# <a name="rel-element-solutiontype-complextype-visio-xml"></a><span data-ttu-id="7503c-103">Rel 元素 （Solution_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="7503c-103">Rel element (Solution_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="7503c-104">指定与此解决方案的 XML 关联的解决方案与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="7503c-104">Specifies a relationship to a part with the solution XML associated with this solution.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="7503c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="7503c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7503c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="7503c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="7503c-107">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="7503c-107">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="7503c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7503c-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="7503c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7503c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="7503c-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="7503c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="7503c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="7503c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="7503c-112">pages.xml、 masters.xml、 recordsets.xml、 页 #.xml、 主 #.xml</span><span class="sxs-lookup"><span data-stu-id="7503c-112">pages.xml, masters.xml, recordsets.xml, page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7503c-113">定义</span><span class="sxs-lookup"><span data-stu-id="7503c-113">Definition</span></span>

```XML
<xs:element name="Rel" type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7503c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7503c-114">Elements and attributes</span></span>

<span data-ttu-id="7503c-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7503c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="7503c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7503c-116">Parent elements</span></span>

|<span data-ttu-id="7503c-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="7503c-117">**Element**</span></span>|<span data-ttu-id="7503c-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="7503c-118">**Type**</span></span>|<span data-ttu-id="7503c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="7503c-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7503c-120">Solution</span><span class="sxs-lookup"><span data-stu-id="7503c-120">Solution</span></span>](solution-element-solutions_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7503c-121">Solution_Type</span><span class="sxs-lookup"><span data-stu-id="7503c-121">Solution_Type</span></span>](solution_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7503c-122">指定 XML 存储在绘图中的解决方案的一个的实例。</span><span class="sxs-lookup"><span data-stu-id="7503c-122">Specifies one instance of solution XML stored in the drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="7503c-123">子元素</span><span class="sxs-lookup"><span data-stu-id="7503c-123">Child elements</span></span>

<span data-ttu-id="7503c-124">无。</span><span class="sxs-lookup"><span data-stu-id="7503c-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="7503c-125">属性</span><span class="sxs-lookup"><span data-stu-id="7503c-125">Attributes</span></span>

|<span data-ttu-id="7503c-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="7503c-126">**Attribute**</span></span>|<span data-ttu-id="7503c-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="7503c-127">**Type**</span></span>|<span data-ttu-id="7503c-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="7503c-128">**Required**</span></span>|<span data-ttu-id="7503c-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="7503c-129">**Description**</span></span>|<span data-ttu-id="7503c-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="7503c-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7503c-131">r: id</span><span class="sxs-lookup"><span data-stu-id="7503c-131">r:id</span></span>  <br/> |<span data-ttu-id="7503c-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7503c-132">xsd:string</span></span>  <br/> <span data-ttu-id="7503c-133">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="7503c-133">See Remarks.</span></span>  <br/> |<span data-ttu-id="7503c-134">必需</span><span class="sxs-lookup"><span data-stu-id="7503c-134">required</span></span>  <br/> |<span data-ttu-id="7503c-135">指定与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="7503c-135">Specifies a relationship to a part.</span></span>  <br/> |<span data-ttu-id="7503c-136">"删除 #"</span><span class="sxs-lookup"><span data-stu-id="7503c-136">"rId#"</span></span>  <br/> <span data-ttu-id="7503c-137">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="7503c-137">See Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7503c-138">说明</span><span class="sxs-lookup"><span data-stu-id="7503c-138">Remarks</span></span>

<span data-ttu-id="7503c-139">**R: id**属性的值必须是**ST_RelationshipID**类型。</span><span class="sxs-lookup"><span data-stu-id="7503c-139">The value of the **r:id** attribute must be an **ST_RelationshipID** type.</span></span> <span data-ttu-id="7503c-140">**ST_RelationshipID**类型是一个 string 类型的值必须是格式为删除的 #，最后一个字符必须数字。</span><span class="sxs-lookup"><span data-stu-id="7503c-140">The **ST_RelationshipID** type is a string that must be in the format 'rId#', where the final character must be a number.</span></span> <span data-ttu-id="7503c-141">号码必须是唯一的**Rel**元素的所有同级元素。</span><span class="sxs-lookup"><span data-stu-id="7503c-141">The number must be unique among all sibling elements of the **Rel** element.</span></span> 
  
<span data-ttu-id="7503c-142">有关 ST_RelationshipID 类型的详细信息，请参阅[第 1 部分 ISO/IEC 29500 规范](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。</span><span class="sxs-lookup"><span data-stu-id="7503c-142">For more information about the ST_RelationshipID type, see the [ISO/IEC 29500 Part 1 specification](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).</span></span>
  

