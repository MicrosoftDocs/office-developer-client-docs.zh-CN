---
title: MoveTo_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4cd3e605-9ac1-14f5-f4e1-992c9100b1b2
ms.openlocfilehash: f3c3ba2bfc789661f57c3d21634b5c876bc11f44
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393906"
---
# <a name="movetotype-complextype-visio-xml"></a><span data-ttu-id="0e1c9-102">MoveTo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="0e1c9-102">MoveTo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="0e1c9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="0e1c9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0e1c9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0e1c9-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="0e1c9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0e1c9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="0e1c9-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="0e1c9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="0e1c9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="0e1c9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="0e1c9-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="0e1c9-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0e1c9-109">定义</span><span class="sxs-lookup"><span data-stu-id="0e1c9-109">Definition</span></span>

```XML
          <xs:complexType name="MoveTo_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="0e1c9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0e1c9-110">Elements and attributes</span></span>

<span data-ttu-id="0e1c9-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0e1c9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="0e1c9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0e1c9-112">Child elements</span></span>

|<span data-ttu-id="0e1c9-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="0e1c9-113">**Element**</span></span>|<span data-ttu-id="0e1c9-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="0e1c9-114">**Type**</span></span>|<span data-ttu-id="0e1c9-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="0e1c9-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0e1c9-116">Cell</span><span class="sxs-lookup"><span data-stu-id="0e1c9-116">Cell</span></span>](cell-element-moveto-rowvisio-xml.md) <br/> |[<span data-ttu-id="0e1c9-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="0e1c9-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="0e1c9-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="0e1c9-118">Attributes</span></span>

<span data-ttu-id="0e1c9-119">无。</span><span class="sxs-lookup"><span data-stu-id="0e1c9-119">None.</span></span>
  

