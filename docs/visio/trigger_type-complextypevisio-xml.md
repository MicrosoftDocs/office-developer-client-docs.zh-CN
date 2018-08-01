---
title: Trigger_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 50de80d5-c846-1bdc-55e0-c688fe3d364c
ms.openlocfilehash: 38ba2800a32f4f1b4809a5e542fd6b79794bf369
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781554"
---
# <a name="triggertype-complextype-visio-xml"></a><span data-ttu-id="939f9-102">Trigger_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="939f9-102">Trigger_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="939f9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="939f9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="939f9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="939f9-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="939f9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="939f9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="939f9-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="939f9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="939f9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="939f9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="939f9-108">无</span><span class="sxs-lookup"><span data-stu-id="939f9-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="939f9-109">定义</span><span class="sxs-lookup"><span data-stu-id="939f9-109">Definition</span></span>

```XML
          <xs:complexType name="Trigger_Type">
          
          <xs:sequence>
    <xs:element name="RefBy"  type="RefBy_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="939f9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="939f9-110">Elements and attributes</span></span>

<span data-ttu-id="939f9-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="939f9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="939f9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="939f9-112">Child elements</span></span>

|<span data-ttu-id="939f9-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="939f9-113">**Element**</span></span>|<span data-ttu-id="939f9-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="939f9-114">**Type**</span></span>|<span data-ttu-id="939f9-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="939f9-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="939f9-116">RefBy</span><span class="sxs-lookup"><span data-stu-id="939f9-116">RefBy</span></span>](refby-element-trigger_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="939f9-117">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="939f9-117">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="939f9-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="939f9-118">Attributes</span></span>

|<span data-ttu-id="939f9-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="939f9-119">**Attribute**</span></span>|<span data-ttu-id="939f9-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="939f9-120">**Type**</span></span>|<span data-ttu-id="939f9-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="939f9-121">**Required**</span></span>|<span data-ttu-id="939f9-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="939f9-122">**Description**</span></span>|<span data-ttu-id="939f9-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="939f9-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="939f9-124">N</span><span class="sxs-lookup"><span data-stu-id="939f9-124">N</span></span>  <br/> |<span data-ttu-id="939f9-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="939f9-125">xsd:string</span></span>  <br/> |<span data-ttu-id="939f9-126">必需</span><span class="sxs-lookup"><span data-stu-id="939f9-126">required</span></span>  <br/> ||<span data-ttu-id="939f9-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="939f9-127">Values of the xsd:string type.</span></span>  <br/> |
   

