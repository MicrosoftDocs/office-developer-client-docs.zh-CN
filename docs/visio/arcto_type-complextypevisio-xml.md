---
title: ArcTo_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c30c80eb-6327-ebc3-7ea4-8b2fc7525cc0
ms.openlocfilehash: 73a89d7535a81700a875f68905de844f876a6181
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390147"
---
# <a name="arctotype-complextype-visio-xml"></a><span data-ttu-id="7e81e-102">ArcTo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="7e81e-102">ArcTo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="7e81e-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="7e81e-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7e81e-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7e81e-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="7e81e-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7e81e-105">**Schema file**</span></span> <br/> |<span data-ttu-id="7e81e-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="7e81e-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="7e81e-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="7e81e-107">**Extension base**</span></span> <br/> |<span data-ttu-id="7e81e-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="7e81e-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7e81e-109">定义</span><span class="sxs-lookup"><span data-stu-id="7e81e-109">Definition</span></span>

```XML
          <xs:complexType name="ArcTo_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="7e81e-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7e81e-110">Elements and attributes</span></span>

<span data-ttu-id="7e81e-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7e81e-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="7e81e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7e81e-112">Child elements</span></span>

|<span data-ttu-id="7e81e-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="7e81e-113">**Element**</span></span>|<span data-ttu-id="7e81e-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="7e81e-114">**Type**</span></span>|<span data-ttu-id="7e81e-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="7e81e-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7e81e-116">Cell</span><span class="sxs-lookup"><span data-stu-id="7e81e-116">Cell</span></span>](cell-element-arcto-rowvisio-xml.md) <br/> |[<span data-ttu-id="7e81e-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="7e81e-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="7e81e-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="7e81e-118">Attributes</span></span>

<span data-ttu-id="7e81e-119">无。</span><span class="sxs-lookup"><span data-stu-id="7e81e-119">None.</span></span>
  

