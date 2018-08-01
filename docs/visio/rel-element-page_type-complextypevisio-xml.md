---
title: Rel 元素 （Page_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d61b1b97-c360-4d9d-217f-e6f45f760e42
description: 指定相应的网页 XML 与部件的关系。
ms.openlocfilehash: 9fc42527d311faa66b0b4041a0f978818ee84595
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781040"
---
# <a name="rel-element-pagetype-complextype-visio-xml"></a><span data-ttu-id="c43b3-103">Rel 元素 （Page_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c43b3-103">Rel element (Page_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="c43b3-104">指定相应的网页 XML 与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="c43b3-104">Specifies a relationship to a part with the corresponding page XML.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c43b3-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c43b3-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c43b3-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c43b3-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c43b3-107">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="c43b3-107">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c43b3-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c43b3-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c43b3-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c43b3-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c43b3-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="c43b3-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c43b3-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c43b3-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c43b3-112">pages.xml、 masters.xml、 recordsets.xml、 页 #.xml、 主 #.xml</span><span class="sxs-lookup"><span data-stu-id="c43b3-112">pages.xml, masters.xml, recordsets.xml, page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c43b3-113">定义</span><span class="sxs-lookup"><span data-stu-id="c43b3-113">Definition</span></span>

```XML
< xs:element name="Rel" type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c43b3-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c43b3-114">Elements and attributes</span></span>

<span data-ttu-id="c43b3-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c43b3-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c43b3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c43b3-116">Parent elements</span></span>

|<span data-ttu-id="c43b3-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c43b3-117">**Element**</span></span>|<span data-ttu-id="c43b3-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c43b3-118">**Type**</span></span>|<span data-ttu-id="c43b3-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c43b3-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c43b3-120">网页</span><span class="sxs-lookup"><span data-stu-id="c43b3-120">Page</span></span>](page-element-pages_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c43b3-121">Page_Type</span><span class="sxs-lookup"><span data-stu-id="c43b3-121">Page_Type</span></span>](page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c43b3-122">指定 XML 存储在绘图页上的一个的实例。</span><span class="sxs-lookup"><span data-stu-id="c43b3-122">Specifies one instance of page XML stored in the drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c43b3-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c43b3-123">Child elements</span></span>

<span data-ttu-id="c43b3-124">无。</span><span class="sxs-lookup"><span data-stu-id="c43b3-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c43b3-125">属性</span><span class="sxs-lookup"><span data-stu-id="c43b3-125">Attributes</span></span>

|<span data-ttu-id="c43b3-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="c43b3-126">**Attribute**</span></span>|<span data-ttu-id="c43b3-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="c43b3-127">**Type**</span></span>|<span data-ttu-id="c43b3-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="c43b3-128">**Required**</span></span>|<span data-ttu-id="c43b3-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="c43b3-129">**Description**</span></span>|<span data-ttu-id="c43b3-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c43b3-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c43b3-131">r: id</span><span class="sxs-lookup"><span data-stu-id="c43b3-131">r:id</span></span>  <br/> |<span data-ttu-id="c43b3-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c43b3-132">xsd:string</span></span>  <br/> <span data-ttu-id="c43b3-133">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="c43b3-133">See Remarks.</span></span>  <br/> |<span data-ttu-id="c43b3-134">必需</span><span class="sxs-lookup"><span data-stu-id="c43b3-134">required</span></span>  <br/> |<span data-ttu-id="c43b3-135">指定与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="c43b3-135">Specifies a relationship to a part.</span></span>  <br/> |<span data-ttu-id="c43b3-136">"删除 #"</span><span class="sxs-lookup"><span data-stu-id="c43b3-136">"rId#"</span></span>  <br/> <span data-ttu-id="c43b3-137">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="c43b3-137">See Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c43b3-138">说明</span><span class="sxs-lookup"><span data-stu-id="c43b3-138">Remarks</span></span>

<span data-ttu-id="c43b3-139">**R: id**属性的值必须是**ST_RelationshipID**类型。</span><span class="sxs-lookup"><span data-stu-id="c43b3-139">The value of the **r:id** attribute must be an **ST_RelationshipID** type.</span></span> <span data-ttu-id="c43b3-140">**ST_RelationshipID**类型是一个 string 类型的值必须是格式为删除的 #，最后一个字符必须数字。</span><span class="sxs-lookup"><span data-stu-id="c43b3-140">The **ST_RelationshipID** type is a string that must be in the format 'rId#', where the final character must be a number.</span></span> <span data-ttu-id="c43b3-141">号码必须是唯一的**Rel**元素的所有同级元素。</span><span class="sxs-lookup"><span data-stu-id="c43b3-141">The number must be unique among all sibling elements of the **Rel** element.</span></span> 
  
<span data-ttu-id="c43b3-142">有关 ST_RelationshipID 类型的详细信息，请参阅[第 1 部分 ISO/IEC 29500 规范](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。</span><span class="sxs-lookup"><span data-stu-id="c43b3-142">For more information about the ST_RelationshipID type, see the [ISO/IEC 29500 Part 1 specification](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).</span></span>
  

