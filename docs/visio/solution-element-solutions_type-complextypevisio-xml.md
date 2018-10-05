---
title: Solution 元素 （Solutions_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 46bf34be-761e-9d44-ab06-83d4c8932cab
description: 指定 XML 存储在绘图中的解决方案的一个的实例。
ms.openlocfilehash: bb3cd512ff6109467c9d6465ba72c764d83abf96
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397196"
---
# <a name="solution-element-solutionstype-complextype-visio-xml"></a><span data-ttu-id="edced-103">Solution 元素 （Solutions_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="edced-103">Solution element (Solutions_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="edced-104">指定 XML 存储在绘图中的解决方案的一个的实例。</span><span class="sxs-lookup"><span data-stu-id="edced-104">Specifies one instance of solution XML stored in the drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="edced-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="edced-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="edced-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="edced-106">**Element type**</span></span> <br/> |[<span data-ttu-id="edced-107">Solution_Type</span><span class="sxs-lookup"><span data-stu-id="edced-107">Solution_Type</span></span>](solution_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="edced-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="edced-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="edced-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="edced-109">**Schema file**</span></span> <br/> |<span data-ttu-id="edced-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="edced-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="edced-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="edced-111">**Document parts**</span></span> <br/> |<span data-ttu-id="edced-112">solutions.xml</span><span class="sxs-lookup"><span data-stu-id="edced-112">solutions.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="edced-113">定义</span><span class="sxs-lookup"><span data-stu-id="edced-113">Definition</span></span>

```XML
< xs:element name="Solution"  type="Solution_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="edced-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="edced-114">Elements and attributes</span></span>

<span data-ttu-id="edced-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="edced-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="edced-116">父元素</span><span class="sxs-lookup"><span data-stu-id="edced-116">Parent elements</span></span>

|<span data-ttu-id="edced-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="edced-117">**Element**</span></span>|<span data-ttu-id="edced-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="edced-118">**Type**</span></span>|<span data-ttu-id="edced-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="edced-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="edced-120">解决方案</span><span class="sxs-lookup"><span data-stu-id="edced-120">Solutions</span></span>](solutions-elementvisio-xml.md) <br/> |[<span data-ttu-id="edced-121">Solutions_Type</span><span class="sxs-lookup"><span data-stu-id="edced-121">Solutions_Type</span></span>](solutions_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="edced-122">存储在文档中存储的解决方案的属性。</span><span class="sxs-lookup"><span data-stu-id="edced-122">Stores the properties of the solutions stored in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="edced-123">子元素</span><span class="sxs-lookup"><span data-stu-id="edced-123">Child elements</span></span>

|<span data-ttu-id="edced-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="edced-124">**Element**</span></span>|<span data-ttu-id="edced-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="edced-125">**Type**</span></span>|<span data-ttu-id="edced-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="edced-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="edced-127">Rel</span><span class="sxs-lookup"><span data-stu-id="edced-127">Rel</span></span>](rel-element-solution_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="edced-128">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="edced-128">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="edced-129">解决方案与此解决方案关联的 XML 中指定到部件的关系。</span><span class="sxs-lookup"><span data-stu-id="edced-129">Specifies the relationship to a part with the solution XML associated with this solution.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="edced-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="edced-130">Attributes</span></span>

|<span data-ttu-id="edced-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="edced-131">**Attribute**</span></span>|<span data-ttu-id="edced-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="edced-132">**Type**</span></span>|<span data-ttu-id="edced-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="edced-133">**Required**</span></span>|<span data-ttu-id="edced-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="edced-134">**Description**</span></span>|<span data-ttu-id="edced-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="edced-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="edced-136">名称</span><span class="sxs-lookup"><span data-stu-id="edced-136">Name</span></span>  <br/> |<span data-ttu-id="edced-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="edced-137">xsd:string</span></span>  <br/> |<span data-ttu-id="edced-138">必需</span><span class="sxs-lookup"><span data-stu-id="edced-138">required</span></span>  <br/> |<span data-ttu-id="edced-139">解决方案的名称。</span><span class="sxs-lookup"><span data-stu-id="edced-139">The name of the solution.</span></span>  <br/> |<span data-ttu-id="edced-140">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="edced-140">Values of the xsd:string type.</span></span>  <br/> |
   

