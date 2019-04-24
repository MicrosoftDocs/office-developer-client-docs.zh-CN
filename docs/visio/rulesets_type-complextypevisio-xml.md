---
title: RuleSets_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9bd05541-7cd8-321b-8dd6-fa885c269057
ms.openlocfilehash: 41172a4f15b0d9038fd0ffb0c0a7d8c3d4078798
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319038"
---
# <a name="rulesetstype-complextype-visio-xml"></a><span data-ttu-id="a1fb6-102">RuleSets_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="a1fb6-102">RuleSets_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="a1fb6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="a1fb6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a1fb6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a1fb6-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="a1fb6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a1fb6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="a1fb6-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="a1fb6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="a1fb6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="a1fb6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="a1fb6-108">无</span><span class="sxs-lookup"><span data-stu-id="a1fb6-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a1fb6-109">定义</span><span class="sxs-lookup"><span data-stu-id="a1fb6-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="a1fb6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a1fb6-110">Elements and attributes</span></span>

<span data-ttu-id="a1fb6-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="a1fb6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a1fb6-112">Child elements</span></span>

|<span data-ttu-id="a1fb6-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="a1fb6-113">**Element**</span></span>|<span data-ttu-id="a1fb6-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="a1fb6-114">**Type**</span></span>|<span data-ttu-id="a1fb6-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a1fb6-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a1fb6-116">RuleSet</span><span class="sxs-lookup"><span data-stu-id="a1fb6-116">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a1fb6-117">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="a1fb6-117">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="a1fb6-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="a1fb6-118">Attributes</span></span>

<span data-ttu-id="a1fb6-119">无。</span><span class="sxs-lookup"><span data-stu-id="a1fb6-119">None.</span></span>
  

