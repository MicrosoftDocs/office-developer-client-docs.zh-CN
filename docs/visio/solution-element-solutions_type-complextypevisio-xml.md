---
title: 'Solution 元素 (Solutions_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 46bf34be-761e-9d44-ab06-83d4c8932cab
description: 指定绘图中存储的解决方案 XML 的一个实例。
ms.openlocfilehash: 028decf0ac9b33ac33dd1e44ed3992ef7eb38aed
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540264"
---
# <a name="solution-element-solutions_type-complextype-visio-xml"></a><span data-ttu-id="1b727-103">Solution 元素 (Solutions_Type complexType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="1b727-103">Solution element (Solutions_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="1b727-104">指定绘图中存储的解决方案 XML 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="1b727-104">Specifies one instance of solution XML stored in the drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="1b727-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="1b727-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1b727-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="1b727-106">**Element type**</span></span> <br/> |[<span data-ttu-id="1b727-107">Solution_Type</span><span class="sxs-lookup"><span data-stu-id="1b727-107">Solution_Type</span></span>](solution_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="1b727-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1b727-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="1b727-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1b727-109">**Schema file**</span></span> <br/> |<span data-ttu-id="1b727-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="1b727-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="1b727-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="1b727-111">**Document parts**</span></span> <br/> |<span data-ttu-id="1b727-112">solutions.xml</span><span class="sxs-lookup"><span data-stu-id="1b727-112">solutions.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1b727-113">定义</span><span class="sxs-lookup"><span data-stu-id="1b727-113">Definition</span></span>

```XML
< xs:element name="Solution"  type="Solution_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1b727-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1b727-114">Elements and attributes</span></span>

<span data-ttu-id="1b727-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1b727-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="1b727-116">父元素</span><span class="sxs-lookup"><span data-stu-id="1b727-116">Parent elements</span></span>

|<span data-ttu-id="1b727-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="1b727-117">**Element**</span></span>|<span data-ttu-id="1b727-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="1b727-118">**Type**</span></span>|<span data-ttu-id="1b727-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="1b727-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1b727-120">解决方案</span><span class="sxs-lookup"><span data-stu-id="1b727-120">Solutions</span></span>](solutions-elementvisio-xml.md) <br/> |[<span data-ttu-id="1b727-121">Solutions_Type</span><span class="sxs-lookup"><span data-stu-id="1b727-121">Solutions_Type</span></span>](solutions_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1b727-122">存储文档中存储的解决方案的属性。</span><span class="sxs-lookup"><span data-stu-id="1b727-122">Stores the properties of the solutions stored in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="1b727-123">子元素</span><span class="sxs-lookup"><span data-stu-id="1b727-123">Child elements</span></span>

|<span data-ttu-id="1b727-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="1b727-124">**Element**</span></span>|<span data-ttu-id="1b727-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="1b727-125">**Type**</span></span>|<span data-ttu-id="1b727-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="1b727-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1b727-127">Rel</span><span class="sxs-lookup"><span data-stu-id="1b727-127">Rel</span></span>](rel-element-solution_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1b727-128">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="1b727-128">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1b727-129">指定与与此解决方案关联的解决方案 XML 的部件的关系。</span><span class="sxs-lookup"><span data-stu-id="1b727-129">Specifies the relationship to a part with the solution XML associated with this solution.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="1b727-130">属性</span><span class="sxs-lookup"><span data-stu-id="1b727-130">Attributes</span></span>

|<span data-ttu-id="1b727-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="1b727-131">**Attribute**</span></span>|<span data-ttu-id="1b727-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="1b727-132">**Type**</span></span>|<span data-ttu-id="1b727-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="1b727-133">**Required**</span></span>|<span data-ttu-id="1b727-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="1b727-134">**Description**</span></span>|<span data-ttu-id="1b727-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1b727-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1b727-136">名称</span><span class="sxs-lookup"><span data-stu-id="1b727-136">Name</span></span>  <br/> |<span data-ttu-id="1b727-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="1b727-137">xsd:string</span></span>  <br/> |<span data-ttu-id="1b727-138">必需</span><span class="sxs-lookup"><span data-stu-id="1b727-138">required</span></span>  <br/> |<span data-ttu-id="1b727-139">解决方案的名称。</span><span class="sxs-lookup"><span data-stu-id="1b727-139">The name of the solution.</span></span>  <br/> |<span data-ttu-id="1b727-140">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1b727-140">Values of the xsd:string type.</span></span>  <br/> |
   

