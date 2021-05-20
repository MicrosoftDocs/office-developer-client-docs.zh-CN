---
title: 'Rel 元素 (ForeignData_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7ed604ef-e001-f379-92c3-391a18f22bb3
description: 指定形状和包含与形状关联的图像数据的文档部件之间的关系。
ms.openlocfilehash: 5836fd306670600f65eda1f3a998ef4c5479114b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542805"
---
# <a name="rel-element-foreigndata_type-complextype-visio-xml"></a><span data-ttu-id="1aa00-103">Rel 元素 (ForeignData_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="1aa00-103">Rel element (ForeignData_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="1aa00-104">指定形状和包含与形状关联的图像数据的文档部件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="1aa00-104">Specifies a relationship between a shape and a document part that contains the image data associated with the shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="1aa00-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="1aa00-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1aa00-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="1aa00-106">**Element type**</span></span> <br/> |[<span data-ttu-id="1aa00-107">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="1aa00-107">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="1aa00-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1aa00-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="1aa00-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1aa00-109">**Schema file**</span></span> <br/> |<span data-ttu-id="1aa00-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="1aa00-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="1aa00-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="1aa00-111">**Document parts**</span></span> <br/> |<span data-ttu-id="1aa00-112">pages.xml、masters.xml、recordsets.xml、page#.xml、master#.xml</span><span class="sxs-lookup"><span data-stu-id="1aa00-112">pages.xml, masters.xml, recordsets.xml, page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1aa00-113">定义</span><span class="sxs-lookup"><span data-stu-id="1aa00-113">Definition</span></span>

```XML
< xs:element name="Rel" type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1aa00-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1aa00-114">Elements and attributes</span></span>

<span data-ttu-id="1aa00-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1aa00-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="1aa00-116">父元素</span><span class="sxs-lookup"><span data-stu-id="1aa00-116">Parent elements</span></span>

|<span data-ttu-id="1aa00-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="1aa00-117">**Element**</span></span>|<span data-ttu-id="1aa00-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="1aa00-118">**Type**</span></span>|<span data-ttu-id="1aa00-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="1aa00-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1aa00-120">ForeignData</span><span class="sxs-lookup"><span data-stu-id="1aa00-120">ForeignData</span></span>](foreigndata-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1aa00-121">ForeignData_Type</span><span class="sxs-lookup"><span data-stu-id="1aa00-121">ForeignData_Type</span></span>](foreigndata_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1aa00-122">指定绘图中存储的图像数据的一个实例。</span><span class="sxs-lookup"><span data-stu-id="1aa00-122">Specifies one instance of image data stored in the drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="1aa00-123">子元素</span><span class="sxs-lookup"><span data-stu-id="1aa00-123">Child elements</span></span>

<span data-ttu-id="1aa00-124">无。</span><span class="sxs-lookup"><span data-stu-id="1aa00-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1aa00-125">属性</span><span class="sxs-lookup"><span data-stu-id="1aa00-125">Attributes</span></span>

|<span data-ttu-id="1aa00-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="1aa00-126">**Attribute**</span></span>|<span data-ttu-id="1aa00-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="1aa00-127">**Type**</span></span>|<span data-ttu-id="1aa00-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="1aa00-128">**Required**</span></span>|<span data-ttu-id="1aa00-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="1aa00-129">**Description**</span></span>|<span data-ttu-id="1aa00-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1aa00-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1aa00-131">r：id</span><span class="sxs-lookup"><span data-stu-id="1aa00-131">r:id</span></span>  <br/> |<span data-ttu-id="1aa00-132">xsd：string</span><span class="sxs-lookup"><span data-stu-id="1aa00-132">xsd:string</span></span>  <br/> <span data-ttu-id="1aa00-133">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="1aa00-133">See Remarks.</span></span>  <br/> |<span data-ttu-id="1aa00-134">必需</span><span class="sxs-lookup"><span data-stu-id="1aa00-134">required</span></span>  <br/> |<span data-ttu-id="1aa00-135">指定与部件的关系。</span><span class="sxs-lookup"><span data-stu-id="1aa00-135">Specifies a relationship to a part.</span></span>  <br/> |<span data-ttu-id="1aa00-136">"rId#"</span><span class="sxs-lookup"><span data-stu-id="1aa00-136">"rId#"</span></span>  <br/> <span data-ttu-id="1aa00-137">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="1aa00-137">See Remarks.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1aa00-138">备注</span><span class="sxs-lookup"><span data-stu-id="1aa00-138">Remarks</span></span>

<span data-ttu-id="1aa00-139">**r：id** 属性的值必须是 **一个ST_RelationshipID** 类型。</span><span class="sxs-lookup"><span data-stu-id="1aa00-139">The value of the **r:id** attribute must be an **ST_RelationshipID** type.</span></span> <span data-ttu-id="1aa00-140">the **ST_RelationshipID** type is a string that must be in the format 'rId#'， where the final character must be a number.</span><span class="sxs-lookup"><span data-stu-id="1aa00-140">The **ST_RelationshipID** type is a string that must be in the format 'rId#', where the final character must be a number.</span></span> <span data-ttu-id="1aa00-141">该数字在 **Rel** 元素的所有同级元素中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1aa00-141">The number must be unique among all sibling elements of the **Rel** element.</span></span> 
  
<span data-ttu-id="1aa00-142">有关类型类型ST_RelationshipID，请参阅 [ISO/IEC 29500 第 1 部分规范](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。</span><span class="sxs-lookup"><span data-stu-id="1aa00-142">For more information about the ST_RelationshipID type, see the [ISO/IEC 29500 Part 1 specification](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).</span></span>
  

