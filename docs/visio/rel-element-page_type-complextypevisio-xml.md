---
title: Rel 元素 （Page_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d61b1b97-c360-4d9d-217f-e6f45f760e42
description: 指定相应的网页 XML 与部件的关系。
ms.openlocfilehash: 7a45764817175f670cdb009157e21a1a25f31cc5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398904"
---
# <a name="rel-element-pagetype-complextype-visio-xml"></a><span data-ttu-id="6404a-103">Rel 元素 （Page_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="6404a-103">Rel element (Page_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="6404a-104">指定相应的网页 XML 与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="6404a-104">Specifies a relationship to a part with the corresponding page XML.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="6404a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="6404a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6404a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="6404a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="6404a-107">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="6404a-107">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="6404a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6404a-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="6404a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6404a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="6404a-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="6404a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="6404a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="6404a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="6404a-112">pages.xml、 masters.xml、 recordsets.xml、 页 #.xml、 主 #.xml</span><span class="sxs-lookup"><span data-stu-id="6404a-112">pages.xml, masters.xml, recordsets.xml, page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6404a-113">定义</span><span class="sxs-lookup"><span data-stu-id="6404a-113">Definition</span></span>

```XML
< xs:element name="Rel" type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6404a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6404a-114">Elements and attributes</span></span>

<span data-ttu-id="6404a-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6404a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="6404a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6404a-116">Parent elements</span></span>

|<span data-ttu-id="6404a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="6404a-117">**Element**</span></span>|<span data-ttu-id="6404a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="6404a-118">**Type**</span></span>|<span data-ttu-id="6404a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6404a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6404a-120">网页</span><span class="sxs-lookup"><span data-stu-id="6404a-120">Page</span></span>](page-element-pages_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6404a-121">Page_Type</span><span class="sxs-lookup"><span data-stu-id="6404a-121">Page_Type</span></span>](page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="6404a-122">指定 XML 存储在绘图页上的一个的实例。</span><span class="sxs-lookup"><span data-stu-id="6404a-122">Specifies one instance of page XML stored in the drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="6404a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6404a-123">Child elements</span></span>

<span data-ttu-id="6404a-124">无。</span><span class="sxs-lookup"><span data-stu-id="6404a-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6404a-125">属性</span><span class="sxs-lookup"><span data-stu-id="6404a-125">Attributes</span></span>

|<span data-ttu-id="6404a-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="6404a-126">**Attribute**</span></span>|<span data-ttu-id="6404a-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="6404a-127">**Type**</span></span>|<span data-ttu-id="6404a-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="6404a-128">**Required**</span></span>|<span data-ttu-id="6404a-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="6404a-129">**Description**</span></span>|<span data-ttu-id="6404a-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6404a-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6404a-131">r: id</span><span class="sxs-lookup"><span data-stu-id="6404a-131">r:id</span></span>  <br/> |<span data-ttu-id="6404a-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6404a-132">xsd:string</span></span>  <br/> <span data-ttu-id="6404a-133">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="6404a-133">See Remarks.</span></span>  <br/> |<span data-ttu-id="6404a-134">必需</span><span class="sxs-lookup"><span data-stu-id="6404a-134">required</span></span>  <br/> |<span data-ttu-id="6404a-135">指定与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="6404a-135">Specifies a relationship to a part.</span></span>  <br/> |<span data-ttu-id="6404a-136">"删除 #"</span><span class="sxs-lookup"><span data-stu-id="6404a-136">"rId#"</span></span>  <br/> <span data-ttu-id="6404a-137">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="6404a-137">See Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6404a-138">说明</span><span class="sxs-lookup"><span data-stu-id="6404a-138">Remarks</span></span>

<span data-ttu-id="6404a-139">**R: id**属性的值必须是**ST_RelationshipID**类型。</span><span class="sxs-lookup"><span data-stu-id="6404a-139">The value of the **r:id** attribute must be an **ST_RelationshipID** type.</span></span> <span data-ttu-id="6404a-140">**ST_RelationshipID**类型是一个 string 类型的值必须是格式为删除的 #，最后一个字符必须数字。</span><span class="sxs-lookup"><span data-stu-id="6404a-140">The **ST_RelationshipID** type is a string that must be in the format 'rId#', where the final character must be a number.</span></span> <span data-ttu-id="6404a-141">号码必须是唯一的**Rel**元素的所有同级元素。</span><span class="sxs-lookup"><span data-stu-id="6404a-141">The number must be unique among all sibling elements of the **Rel** element.</span></span> 
  
<span data-ttu-id="6404a-142">有关 ST_RelationshipID 类型的详细信息，请参阅[第 1 部分 ISO/IEC 29500 规范](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。</span><span class="sxs-lookup"><span data-stu-id="6404a-142">For more information about the ST_RelationshipID type, see the [ISO/IEC 29500 Part 1 specification](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).</span></span>
  

