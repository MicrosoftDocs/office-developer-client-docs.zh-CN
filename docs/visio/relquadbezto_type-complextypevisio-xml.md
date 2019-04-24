---
title: RelQuadBezTo_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 558c7315-5025-484b-446e-333890bc1c3a
ms.openlocfilehash: d584891576967f3e452402667f0adaad5c87843f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320165"
---
# <a name="relquadbeztotype-complextype-visio-xml"></a><span data-ttu-id="ff187-102">RelQuadBezTo_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="ff187-102">RelQuadBezTo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="ff187-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ff187-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ff187-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ff187-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ff187-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ff187-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ff187-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="ff187-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ff187-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ff187-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ff187-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="ff187-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ff187-109">定义</span><span class="sxs-lookup"><span data-stu-id="ff187-109">Definition</span></span>

```XML
          <xs:complexType name="RelQuadBezTo_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="ff187-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ff187-110">Elements and attributes</span></span>

<span data-ttu-id="ff187-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="ff187-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ff187-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ff187-112">Child elements</span></span>

|<span data-ttu-id="ff187-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="ff187-113">**Element**</span></span>|<span data-ttu-id="ff187-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="ff187-114">**Type**</span></span>|<span data-ttu-id="ff187-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ff187-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ff187-116">Cell</span><span class="sxs-lookup"><span data-stu-id="ff187-116">Cell</span></span>](cell-element-relquadbezto-rowvisio-xml.md) <br/> |[<span data-ttu-id="ff187-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="ff187-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="ff187-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="ff187-118">Attributes</span></span>

<span data-ttu-id="ff187-119">无。</span><span class="sxs-lookup"><span data-stu-id="ff187-119">None.</span></span>
  

