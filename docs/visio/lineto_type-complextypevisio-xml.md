---
title: LineTo_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 15859b84-5486-bb8c-e67e-5d0baaf59ee5
ms.openlocfilehash: 5b6dac15b8c66b4efbe32c22398d577feab47746
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780573"
---
# <a name="linetotype-complextype-visio-xml"></a><span data-ttu-id="7816c-102">LineTo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="7816c-102">LineTo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="7816c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="7816c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7816c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7816c-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="7816c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7816c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="7816c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="7816c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="7816c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="7816c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="7816c-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="7816c-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7816c-109">定义</span><span class="sxs-lookup"><span data-stu-id="7816c-109">Definition</span></span>

```XML
          <xs:complexType name="LineTo_Type">
          
          <xs:complexContent>
          <xs:extension base="GeometryRow_Type">
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

## <a name="elements-and-attributes"></a><span data-ttu-id="7816c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7816c-110">Elements and attributes</span></span>

<span data-ttu-id="7816c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7816c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="7816c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7816c-112">Child elements</span></span>

|<span data-ttu-id="7816c-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="7816c-113">**Element**</span></span>|<span data-ttu-id="7816c-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="7816c-114">**Type**</span></span>|<span data-ttu-id="7816c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="7816c-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7816c-116">Cell</span><span class="sxs-lookup"><span data-stu-id="7816c-116">Cell</span></span>](cell-element-lineto-rowvisio-xml.md) <br/> |[<span data-ttu-id="7816c-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="7816c-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="7816c-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="7816c-118">Attributes</span></span>

<span data-ttu-id="7816c-119">无。</span><span class="sxs-lookup"><span data-stu-id="7816c-119">None.</span></span>
  

