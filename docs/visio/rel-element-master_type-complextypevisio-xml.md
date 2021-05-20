---
title: 'Rel 元素 (Master_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 151cdd13-d00b-249c-7ebd-1ae9c4042b03
description: 指定与具有相应主 XML 的部件的关系。
ms.openlocfilehash: 032c1ef4a94bb6acf18587a1257fe82285124e87
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542798"
---
# <a name="rel-element-master_type-complextype-visio-xml"></a><span data-ttu-id="4c7be-103">Rel 元素 (Master_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="4c7be-103">Rel element (Master_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="4c7be-104">指定与具有相应主 XML 的部件的关系。</span><span class="sxs-lookup"><span data-stu-id="4c7be-104">Specifies a relationship to a part with the corresponding master XML.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4c7be-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4c7be-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4c7be-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4c7be-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4c7be-107">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="4c7be-107">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4c7be-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4c7be-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4c7be-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4c7be-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4c7be-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="4c7be-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4c7be-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4c7be-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4c7be-112">pages.xml、masters.xml、recordsets.xml、page#.xml、master#.xml</span><span class="sxs-lookup"><span data-stu-id="4c7be-112">pages.xml, masters.xml, recordsets.xml, page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4c7be-113">定义</span><span class="sxs-lookup"><span data-stu-id="4c7be-113">Definition</span></span>

```XML
< xs:element name="Rel"  type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4c7be-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4c7be-114">Elements and attributes</span></span>

<span data-ttu-id="4c7be-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4c7be-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4c7be-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4c7be-116">Parent elements</span></span>

|<span data-ttu-id="4c7be-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4c7be-117">**Element**</span></span>|<span data-ttu-id="4c7be-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4c7be-118">**Type**</span></span>|<span data-ttu-id="4c7be-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c7be-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4c7be-120">Master</span><span class="sxs-lookup"><span data-stu-id="4c7be-120">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4c7be-121">Master_Type</span><span class="sxs-lookup"><span data-stu-id="4c7be-121">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4c7be-122">指定存储在绘图中的主 XML 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="4c7be-122">Specifies one instance of master XML stored in the drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4c7be-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4c7be-123">Child elements</span></span>

<span data-ttu-id="4c7be-124">无。</span><span class="sxs-lookup"><span data-stu-id="4c7be-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4c7be-125">属性</span><span class="sxs-lookup"><span data-stu-id="4c7be-125">Attributes</span></span>

|<span data-ttu-id="4c7be-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="4c7be-126">**Attribute**</span></span>|<span data-ttu-id="4c7be-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="4c7be-127">**Type**</span></span>|<span data-ttu-id="4c7be-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="4c7be-128">**Required**</span></span>|<span data-ttu-id="4c7be-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="4c7be-129">**Description**</span></span>|<span data-ttu-id="4c7be-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4c7be-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c7be-131">r：id</span><span class="sxs-lookup"><span data-stu-id="4c7be-131">r:id</span></span>  <br/> |<span data-ttu-id="4c7be-132">xsd：string</span><span class="sxs-lookup"><span data-stu-id="4c7be-132">xsd:string</span></span>  <br/> <span data-ttu-id="4c7be-133">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="4c7be-133">See Remarks.</span></span>  <br/> |<span data-ttu-id="4c7be-134">必需</span><span class="sxs-lookup"><span data-stu-id="4c7be-134">required</span></span>  <br/> |<span data-ttu-id="4c7be-135">指定与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="4c7be-135">Specifies a relationship to a part.</span></span>  <br/> |<span data-ttu-id="4c7be-136">"rId#"</span><span class="sxs-lookup"><span data-stu-id="4c7be-136">"rId#"</span></span>  <br/> <span data-ttu-id="4c7be-137">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="4c7be-137">See Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4c7be-138">备注</span><span class="sxs-lookup"><span data-stu-id="4c7be-138">Remarks</span></span>

<span data-ttu-id="4c7be-139">**r：id** 属性的值必须是 **一个ST_RelationshipID** 类型。</span><span class="sxs-lookup"><span data-stu-id="4c7be-139">The value of the **r:id** attribute must be an **ST_RelationshipID** type.</span></span> <span data-ttu-id="4c7be-140">the **ST_RelationshipID** type is a string that must be in the format 'rId#'， where the final character must be a number.</span><span class="sxs-lookup"><span data-stu-id="4c7be-140">The **ST_RelationshipID** type is a string that must be in the format 'rId#', where the final character must be a number.</span></span> <span data-ttu-id="4c7be-141">该数字在 **Rel** 元素的所有同级元素中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4c7be-141">The number must be unique among all sibling elements of the **Rel** element.</span></span> 
  
<span data-ttu-id="4c7be-142">有关类型类型ST_RelationshipID，请参阅 [ISO/IEC 29500 第 1 部分规范](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。</span><span class="sxs-lookup"><span data-stu-id="4c7be-142">For more information about the ST_RelationshipID type, see the [ISO/IEC 29500 Part 1 specification](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).</span></span>
  

