---
title: NURBSTo_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f7ae8a1d-5bb7-a92f-79d6-5a358d879c32
ms.openlocfilehash: 47c8c552fb50c29ecf2f89325c1a818e61d60d1f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391757"
---
# <a name="nurbstotype-complextype-visio-xml"></a><span data-ttu-id="526b9-102">NURBSTo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="526b9-102">NURBSTo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="526b9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="526b9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="526b9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="526b9-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="526b9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="526b9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="526b9-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="526b9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="526b9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="526b9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="526b9-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="526b9-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="526b9-109">定义</span><span class="sxs-lookup"><span data-stu-id="526b9-109">Definition</span></span>

```XML
          <xs:complexType name="NURBSTo_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="526b9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="526b9-110">Elements and attributes</span></span>

<span data-ttu-id="526b9-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="526b9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="526b9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="526b9-112">Child elements</span></span>

|<span data-ttu-id="526b9-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="526b9-113">**Element**</span></span>|<span data-ttu-id="526b9-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="526b9-114">**Type**</span></span>|<span data-ttu-id="526b9-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="526b9-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="526b9-116">Cell</span><span class="sxs-lookup"><span data-stu-id="526b9-116">Cell</span></span>](cell-element-nurbsto-rowvisio-xml.md) <br/> |[<span data-ttu-id="526b9-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="526b9-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="526b9-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="526b9-118">Attributes</span></span>

<span data-ttu-id="526b9-119">无。</span><span class="sxs-lookup"><span data-stu-id="526b9-119">None.</span></span>
  

