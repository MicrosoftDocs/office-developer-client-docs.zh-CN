---
title: Extensions_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5f516e1a-e789-8085-1cc3-70514910eb26
ms.openlocfilehash: 1da1418e2256f7750ac2e963bac0f78321233c99
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780223"
---
# <a name="extensionstype-complextype-visio-xml"></a><span data-ttu-id="84110-102">Extensions_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="84110-102">Extensions_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="84110-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="84110-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="84110-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="84110-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="84110-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="84110-105">**Schema file**</span></span> <br/> |<span data-ttu-id="84110-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="84110-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="84110-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="84110-107">**Extension base**</span></span> <br/> |<span data-ttu-id="84110-108">无</span><span class="sxs-lookup"><span data-stu-id="84110-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="84110-109">定义</span><span class="sxs-lookup"><span data-stu-id="84110-109">Definition</span></span>

```XML
          <xs:complexType name="Extensions_Type">
          
          <xs:sequence>
    <xs:element name="CellDef"  type="CellDef_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="FunctionDef"  type="FunctionDef_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="SectionDef"  type="SectionDef_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="84110-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="84110-110">Elements and attributes</span></span>

<span data-ttu-id="84110-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="84110-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="84110-112">子元素</span><span class="sxs-lookup"><span data-stu-id="84110-112">Child elements</span></span>

|<span data-ttu-id="84110-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="84110-113">**Element**</span></span>|<span data-ttu-id="84110-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="84110-114">**Type**</span></span>|<span data-ttu-id="84110-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="84110-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="84110-116">CellDef</span><span class="sxs-lookup"><span data-stu-id="84110-116">CellDef</span></span>](http://msdn.microsoft.com/library/8fb193f0-5c88-6891-1cda-f1df486aabfc%28Office.15%29.aspx) <br/> |[<span data-ttu-id="84110-117">CellDef_Type</span><span class="sxs-lookup"><span data-stu-id="84110-117">CellDef_Type</span></span>](celldef_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="84110-118">FunctionDef</span><span class="sxs-lookup"><span data-stu-id="84110-118">FunctionDef</span></span>](http://msdn.microsoft.com/library/dad99181-c14c-cce7-3883-106fe05f20a6%28Office.15%29.aspx) <br/> |[<span data-ttu-id="84110-119">FunctionDef_Type</span><span class="sxs-lookup"><span data-stu-id="84110-119">FunctionDef_Type</span></span>](functiondef_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="84110-120">SectionDef</span><span class="sxs-lookup"><span data-stu-id="84110-120">SectionDef</span></span>](http://msdn.microsoft.com/library/751da480-f387-4c68-6699-8948271c23ac%28Office.15%29.aspx) <br/> |[<span data-ttu-id="84110-121">SectionDef_Type</span><span class="sxs-lookup"><span data-stu-id="84110-121">SectionDef_Type</span></span>](sectiondef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="84110-122">属性</span><span class="sxs-lookup"><span data-stu-id="84110-122">Attributes</span></span>

<span data-ttu-id="84110-123">无。</span><span class="sxs-lookup"><span data-stu-id="84110-123">None.</span></span>
  

