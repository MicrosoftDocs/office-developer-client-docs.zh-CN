---
title: SplineKnot_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 114d5460-c5fd-0e31-def4-f943b93bd1ae
ms.openlocfilehash: 6f5bd2c07f4eba0ee2dc2eff26245db2cf221075
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538905"
---
# <a name="splineknottype-complextype-visio-xml"></a><span data-ttu-id="91c17-102">SplineKnot_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="91c17-102">SplineKnot_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="91c17-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="91c17-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="91c17-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="91c17-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="91c17-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="91c17-105">**Schema file**</span></span> <br/> |<span data-ttu-id="91c17-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="91c17-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="91c17-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="91c17-107">**Extension base**</span></span> <br/> |<span data-ttu-id="91c17-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="91c17-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="91c17-109">定义</span><span class="sxs-lookup"><span data-stu-id="91c17-109">Definition</span></span>

```XML
          <xs:complexType name="SplineKnot_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="91c17-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="91c17-110">Elements and attributes</span></span>

<span data-ttu-id="91c17-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="91c17-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="91c17-112">子元素</span><span class="sxs-lookup"><span data-stu-id="91c17-112">Child elements</span></span>

|<span data-ttu-id="91c17-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="91c17-113">**Element**</span></span>|<span data-ttu-id="91c17-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="91c17-114">**Type**</span></span>|<span data-ttu-id="91c17-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="91c17-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="91c17-116">Cell</span><span class="sxs-lookup"><span data-stu-id="91c17-116">Cell</span></span>](cell-element-splineknot-rowvisio-xml.md) <br/> |[<span data-ttu-id="91c17-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="91c17-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="91c17-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="91c17-118">Attributes</span></span>

<span data-ttu-id="91c17-119">无。</span><span class="sxs-lookup"><span data-stu-id="91c17-119">None.</span></span>
  

