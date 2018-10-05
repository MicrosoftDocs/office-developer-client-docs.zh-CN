---
title: RelLineTo_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e5504166-653d-15d2-75eb-9b36f376b788
ms.openlocfilehash: ca4a270b77fee05957ff04798de1dff1512e837d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396244"
---
# <a name="rellinetotype-complextype-visio-xml"></a><span data-ttu-id="028fc-102">RelLineTo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="028fc-102">RelLineTo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="028fc-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="028fc-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="028fc-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="028fc-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="028fc-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="028fc-105">**Schema file**</span></span> <br/> |<span data-ttu-id="028fc-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="028fc-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="028fc-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="028fc-107">**Extension base**</span></span> <br/> |<span data-ttu-id="028fc-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="028fc-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="028fc-109">定义</span><span class="sxs-lookup"><span data-stu-id="028fc-109">Definition</span></span>

```XML
          <xs:complexType name="RelLineTo_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="028fc-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="028fc-110">Elements and attributes</span></span>

<span data-ttu-id="028fc-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="028fc-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="028fc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="028fc-112">Child elements</span></span>

|<span data-ttu-id="028fc-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="028fc-113">**Element**</span></span>|<span data-ttu-id="028fc-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="028fc-114">**Type**</span></span>|<span data-ttu-id="028fc-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="028fc-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="028fc-116">Cell</span><span class="sxs-lookup"><span data-stu-id="028fc-116">Cell</span></span>](cell-element-rellineto-rowvisio-xml.md) <br/> |[<span data-ttu-id="028fc-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="028fc-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="028fc-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="028fc-118">Attributes</span></span>

<span data-ttu-id="028fc-119">无。</span><span class="sxs-lookup"><span data-stu-id="028fc-119">None.</span></span>
  

