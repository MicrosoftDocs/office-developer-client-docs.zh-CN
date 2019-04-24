---
title: Validation_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1bc106ec-879a-0a4b-8c04-a5734eb0097a
ms.openlocfilehash: 6f751db1566e39d919fd0a456d3aab72559ceeba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332793"
---
# <a name="validationtype-complextype-visio-xml"></a><span data-ttu-id="5da18-102">Validation_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="5da18-102">Validation_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="5da18-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5da18-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5da18-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5da18-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5da18-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5da18-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5da18-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="5da18-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5da18-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5da18-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5da18-108">无</span><span class="sxs-lookup"><span data-stu-id="5da18-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5da18-109">定义</span><span class="sxs-lookup"><span data-stu-id="5da18-109">Definition</span></span>

```XML
          <xs:complexType name="Validation_Type">
          
          <xs:sequence>
    <xs:element name="ValidationProperties"  type="ValidationProperties_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="RuleSets"  type="RuleSets_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Issues"  type="Issues_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5da18-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5da18-110">Elements and attributes</span></span>

<span data-ttu-id="5da18-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="5da18-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5da18-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5da18-112">Child elements</span></span>

|<span data-ttu-id="5da18-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="5da18-113">**Element**</span></span>|<span data-ttu-id="5da18-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="5da18-114">**Type**</span></span>|<span data-ttu-id="5da18-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="5da18-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5da18-116">Issues</span><span class="sxs-lookup"><span data-stu-id="5da18-116">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5da18-117">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="5da18-117">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="5da18-118">RuleSets</span><span class="sxs-lookup"><span data-stu-id="5da18-118">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5da18-119">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="5da18-119">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="5da18-120">ValidationProperties</span><span class="sxs-lookup"><span data-stu-id="5da18-120">ValidationProperties</span></span>](validationproperties-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5da18-121">ValidationProperties_Type</span><span class="sxs-lookup"><span data-stu-id="5da18-121">ValidationProperties_Type</span></span>](validationproperties_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="5da18-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="5da18-122">Attributes</span></span>

<span data-ttu-id="5da18-123">无。</span><span class="sxs-lookup"><span data-stu-id="5da18-123">None.</span></span>
  

