---
title: Rel 元素 （Master_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 151cdd13-d00b-249c-7ebd-1ae9c4042b03
description: 指定相应的主 XML 与部件的关系。
ms.openlocfilehash: 82552eeab746d9675f6175b62c34cef4a9c3c418
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393045"
---
# <a name="rel-element-mastertype-complextype-visio-xml"></a><span data-ttu-id="7732b-103">Rel 元素 （Master_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="7732b-103">Rel element (Master_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="7732b-104">指定相应的主 XML 与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="7732b-104">Specifies a relationship to a part with the corresponding master XML.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="7732b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="7732b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7732b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="7732b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="7732b-107">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="7732b-107">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="7732b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7732b-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="7732b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7732b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="7732b-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="7732b-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="7732b-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="7732b-111">**Document parts**</span></span> <br/> |<span data-ttu-id="7732b-112">pages.xml、 masters.xml、 recordsets.xml、 页 #.xml、 主 #.xml</span><span class="sxs-lookup"><span data-stu-id="7732b-112">pages.xml, masters.xml, recordsets.xml, page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7732b-113">定义</span><span class="sxs-lookup"><span data-stu-id="7732b-113">Definition</span></span>

```XML
< xs:element name="Rel"  type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7732b-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7732b-114">Elements and attributes</span></span>

<span data-ttu-id="7732b-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7732b-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="7732b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7732b-116">Parent elements</span></span>

|<span data-ttu-id="7732b-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="7732b-117">**Element**</span></span>|<span data-ttu-id="7732b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="7732b-118">**Type**</span></span>|<span data-ttu-id="7732b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="7732b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7732b-120">Master</span><span class="sxs-lookup"><span data-stu-id="7732b-120">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7732b-121">Master_Type</span><span class="sxs-lookup"><span data-stu-id="7732b-121">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7732b-122">指定存储在绘图中的主 XML 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="7732b-122">Specifies one instance of master XML stored in the drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="7732b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="7732b-123">Child elements</span></span>

<span data-ttu-id="7732b-124">无。</span><span class="sxs-lookup"><span data-stu-id="7732b-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="7732b-125">属性</span><span class="sxs-lookup"><span data-stu-id="7732b-125">Attributes</span></span>

|<span data-ttu-id="7732b-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="7732b-126">**Attribute**</span></span>|<span data-ttu-id="7732b-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="7732b-127">**Type**</span></span>|<span data-ttu-id="7732b-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="7732b-128">**Required**</span></span>|<span data-ttu-id="7732b-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="7732b-129">**Description**</span></span>|<span data-ttu-id="7732b-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="7732b-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7732b-131">r: id</span><span class="sxs-lookup"><span data-stu-id="7732b-131">r:id</span></span>  <br/> |<span data-ttu-id="7732b-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7732b-132">xsd:string</span></span>  <br/> <span data-ttu-id="7732b-133">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="7732b-133">See Remarks.</span></span>  <br/> |<span data-ttu-id="7732b-134">必需</span><span class="sxs-lookup"><span data-stu-id="7732b-134">required</span></span>  <br/> |<span data-ttu-id="7732b-135">指定与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="7732b-135">Specifies a relationship to a part.</span></span>  <br/> |<span data-ttu-id="7732b-136">"删除 #"</span><span class="sxs-lookup"><span data-stu-id="7732b-136">"rId#"</span></span>  <br/> <span data-ttu-id="7732b-137">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="7732b-137">See Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7732b-138">说明</span><span class="sxs-lookup"><span data-stu-id="7732b-138">Remarks</span></span>

<span data-ttu-id="7732b-139">**R: id**属性的值必须是**ST_RelationshipID**类型。</span><span class="sxs-lookup"><span data-stu-id="7732b-139">The value of the **r:id** attribute must be an **ST_RelationshipID** type.</span></span> <span data-ttu-id="7732b-140">**ST_RelationshipID**类型是一个 string 类型的值必须是格式为删除的 #，最后一个字符必须数字。</span><span class="sxs-lookup"><span data-stu-id="7732b-140">The **ST_RelationshipID** type is a string that must be in the format 'rId#', where the final character must be a number.</span></span> <span data-ttu-id="7732b-141">号码必须是唯一的**Rel**元素的所有同级元素。</span><span class="sxs-lookup"><span data-stu-id="7732b-141">The number must be unique among all sibling elements of the **Rel** element.</span></span> 
  
<span data-ttu-id="7732b-142">有关 ST_RelationshipID 类型的详细信息，请参阅[第 1 部分 ISO/IEC 29500 规范](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。</span><span class="sxs-lookup"><span data-stu-id="7732b-142">For more information about the ST_RelationshipID type, see the [ISO/IEC 29500 Part 1 specification](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).</span></span>
  

