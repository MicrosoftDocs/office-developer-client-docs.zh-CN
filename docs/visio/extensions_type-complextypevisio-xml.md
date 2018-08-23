---
title: Extensions_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5f516e1a-e789-8085-1cc3-70514910eb26
ms.openlocfilehash: 670c060cc6f12c664eb615fffb8ec1234891f2b5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592134"
---
# <a name="extensionstype-complextype-visio-xml"></a><span data-ttu-id="ef9ed-102">Extensions_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ef9ed-102">Extensions_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="ef9ed-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ef9ed-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ef9ed-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ef9ed-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ef9ed-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ef9ed-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ef9ed-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="ef9ed-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ef9ed-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ef9ed-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ef9ed-108">无</span><span class="sxs-lookup"><span data-stu-id="ef9ed-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ef9ed-109">定义</span><span class="sxs-lookup"><span data-stu-id="ef9ed-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="ef9ed-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ef9ed-110">Elements and attributes</span></span>

<span data-ttu-id="ef9ed-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ef9ed-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ef9ed-112">Child elements</span></span>

|<span data-ttu-id="ef9ed-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="ef9ed-113">**Element**</span></span>|<span data-ttu-id="ef9ed-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="ef9ed-114">**Type**</span></span>|<span data-ttu-id="ef9ed-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ef9ed-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ef9ed-116">CellDef</span><span class="sxs-lookup"><span data-stu-id="ef9ed-116">CellDef</span></span> <br/> |[<span data-ttu-id="ef9ed-117">CellDef_Type</span><span class="sxs-lookup"><span data-stu-id="ef9ed-117">CellDef_Type</span></span>](celldef_type-complextypevisio-xml.md) <br/> ||
|<span data-ttu-id="ef9ed-118">FunctionDef</span><span class="sxs-lookup"><span data-stu-id="ef9ed-118">FunctionDef</span></span> <br/> |[<span data-ttu-id="ef9ed-119">FunctionDef_Type</span><span class="sxs-lookup"><span data-stu-id="ef9ed-119">FunctionDef_Type</span></span>](functiondef_type-complextypevisio-xml.md) <br/> ||
|<span data-ttu-id="ef9ed-120">SectionDef</span><span class="sxs-lookup"><span data-stu-id="ef9ed-120">SectionDef</span></span> <br/> |[<span data-ttu-id="ef9ed-121">SectionDef_Type</span><span class="sxs-lookup"><span data-stu-id="ef9ed-121">SectionDef_Type</span></span>](sectiondef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="ef9ed-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="ef9ed-122">Attributes</span></span>

<span data-ttu-id="ef9ed-123">无。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-123">None.</span></span>
  

