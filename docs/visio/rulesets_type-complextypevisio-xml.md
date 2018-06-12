---
title: RuleSets_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9bd05541-7cd8-321b-8dd6-fa885c269057
ms.openlocfilehash: 795864810c5d79f6328339009ddc84410caa4e62
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781197"
---
# <a name="rulesetstype-complextype-visio-xml"></a><span data-ttu-id="a9a15-102">RuleSets_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="a9a15-102">RuleSets_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="a9a15-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="a9a15-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a9a15-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a9a15-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="a9a15-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a9a15-105">**Schema file**</span></span> <br/> |<span data-ttu-id="a9a15-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="a9a15-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="a9a15-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="a9a15-107">**Extension base**</span></span> <br/> |<span data-ttu-id="a9a15-108">无</span><span class="sxs-lookup"><span data-stu-id="a9a15-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a9a15-109">定义</span><span class="sxs-lookup"><span data-stu-id="a9a15-109">Definition</span></span>

```XML
          <xs:complexType name="RuleSets_Type">
          
          <xs:sequence>
    <xs:element name="RuleSet"  type="RuleSet_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a9a15-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a9a15-110">Elements and attributes</span></span>

<span data-ttu-id="a9a15-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="a9a15-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="a9a15-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a9a15-112">Child elements</span></span>

|<span data-ttu-id="a9a15-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="a9a15-113">**Element**</span></span>|<span data-ttu-id="a9a15-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="a9a15-114">**Type**</span></span>|<span data-ttu-id="a9a15-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9a15-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a9a15-116">规则集</span><span class="sxs-lookup"><span data-stu-id="a9a15-116">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a9a15-117">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="a9a15-117">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="a9a15-118">属性</span><span class="sxs-lookup"><span data-stu-id="a9a15-118">Attributes</span></span>

<span data-ttu-id="a9a15-119">无。</span><span class="sxs-lookup"><span data-stu-id="a9a15-119">None.</span></span>
  

