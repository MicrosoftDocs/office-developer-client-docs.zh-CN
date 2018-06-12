---
title: Solutions_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 74978183-8513-b359-0501-6094e072ac8e
ms.openlocfilehash: 69c5bf92bb9f72e9969f9687b42b9d583eb2a523
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781414"
---
# <a name="solutionstype-complextype-visio-xml"></a><span data-ttu-id="21930-102">Solutions_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="21930-102">Solutions_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="21930-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="21930-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="21930-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="21930-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="21930-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="21930-105">**Schema file**</span></span> <br/> |<span data-ttu-id="21930-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="21930-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="21930-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="21930-107">**Extension base**</span></span> <br/> |<span data-ttu-id="21930-108">无</span><span class="sxs-lookup"><span data-stu-id="21930-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="21930-109">定义</span><span class="sxs-lookup"><span data-stu-id="21930-109">Definition</span></span>

```XML
          <xs:complexType name="Solutions_Type">
          
          <xs:sequence>
    <xs:element name="Solution"  type="Solution_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="21930-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="21930-110">Elements and attributes</span></span>

<span data-ttu-id="21930-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="21930-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="21930-112">子元素</span><span class="sxs-lookup"><span data-stu-id="21930-112">Child elements</span></span>

|<span data-ttu-id="21930-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="21930-113">**Element**</span></span>|<span data-ttu-id="21930-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="21930-114">**Type**</span></span>|<span data-ttu-id="21930-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="21930-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="21930-116">Solution</span><span class="sxs-lookup"><span data-stu-id="21930-116">Solution</span></span>](solution-element-solutions_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="21930-117">Solution_Type</span><span class="sxs-lookup"><span data-stu-id="21930-117">Solution_Type</span></span>](solution_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="21930-118">属性</span><span class="sxs-lookup"><span data-stu-id="21930-118">Attributes</span></span>

<span data-ttu-id="21930-119">无。</span><span class="sxs-lookup"><span data-stu-id="21930-119">None.</span></span>
  

