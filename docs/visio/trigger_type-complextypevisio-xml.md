---
title: Trigger_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 50de80d5-c846-1bdc-55e0-c688fe3d364c
ms.openlocfilehash: e34ef122a6f0a08168f838fdaeb130d68349ecb8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396328"
---
# <a name="triggertype-complextype-visio-xml"></a><span data-ttu-id="337d6-102">Trigger_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="337d6-102">Trigger_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="337d6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="337d6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="337d6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="337d6-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="337d6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="337d6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="337d6-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="337d6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="337d6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="337d6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="337d6-108">无</span><span class="sxs-lookup"><span data-stu-id="337d6-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="337d6-109">定义</span><span class="sxs-lookup"><span data-stu-id="337d6-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="337d6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="337d6-110">Elements and attributes</span></span>

<span data-ttu-id="337d6-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="337d6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="337d6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="337d6-112">Child elements</span></span>

|<span data-ttu-id="337d6-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="337d6-113">**Element**</span></span>|<span data-ttu-id="337d6-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="337d6-114">**Type**</span></span>|<span data-ttu-id="337d6-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="337d6-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="337d6-116">RefBy</span><span class="sxs-lookup"><span data-stu-id="337d6-116">RefBy</span></span>](refby-element-trigger_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="337d6-117">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="337d6-117">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="337d6-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="337d6-118">Attributes</span></span>

|<span data-ttu-id="337d6-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="337d6-119">**Attribute**</span></span>|<span data-ttu-id="337d6-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="337d6-120">**Type**</span></span>|<span data-ttu-id="337d6-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="337d6-121">**Required**</span></span>|<span data-ttu-id="337d6-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="337d6-122">**Description**</span></span>|<span data-ttu-id="337d6-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="337d6-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="337d6-124">N</span><span class="sxs-lookup"><span data-stu-id="337d6-124">N</span></span>  <br/> |<span data-ttu-id="337d6-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="337d6-125">xsd:string</span></span>  <br/> |<span data-ttu-id="337d6-126">必需</span><span class="sxs-lookup"><span data-stu-id="337d6-126">required</span></span>  <br/> ||<span data-ttu-id="337d6-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="337d6-127">Values of the xsd:string type.</span></span>  <br/> |
   

