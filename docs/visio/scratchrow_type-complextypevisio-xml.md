---
title: ScratchRow_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 35ed6fc0-d737-a931-fddb-7bbb770c8d37
ms.openlocfilehash: 74f106f34596ca4ff2c200e0127155f4df54da28
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391463"
---
# <a name="scratchrowtype-complextype-visio-xml"></a><span data-ttu-id="e991c-102">ScratchRow_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="e991c-102">ScratchRow_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="e991c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e991c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e991c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e991c-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e991c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e991c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e991c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="e991c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e991c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e991c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e991c-108">IndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="e991c-108">IndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e991c-109">定义</span><span class="sxs-lookup"><span data-stu-id="e991c-109">Definition</span></span>

```XML
          <xs:complexType name="ScratchRow_Type">
          
          <xs:complexContent>
          <xs:extension base="IndexedRow_Type">
          <xs:sequence>
    <xs:element name="Cell"  type="Cell_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e991c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e991c-110">Elements and attributes</span></span>

<span data-ttu-id="e991c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="e991c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e991c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e991c-112">Child elements</span></span>

|<span data-ttu-id="e991c-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="e991c-113">**Element**</span></span>|<span data-ttu-id="e991c-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="e991c-114">**Type**</span></span>|<span data-ttu-id="e991c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e991c-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e991c-116">Cell</span><span class="sxs-lookup"><span data-stu-id="e991c-116">Cell</span></span>](cell-element-scratch-sectionvisio-xml.md) <br/> |[<span data-ttu-id="e991c-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="e991c-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="e991c-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="e991c-118">Attributes</span></span>

<span data-ttu-id="e991c-119">无。</span><span class="sxs-lookup"><span data-stu-id="e991c-119">None.</span></span>
  

