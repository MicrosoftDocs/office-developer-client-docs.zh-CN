---
title: RelCubBezTo_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 004dc563-d089-230f-0055-038b72eebbed
ms.openlocfilehash: 7d18a6e4317736b802a761ccbe62e9f01aa1e15d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542715"
---
# <a name="relcubbeztotype-complextype-visio-xml"></a><span data-ttu-id="64c85-102">RelCubBezTo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="64c85-102">RelCubBezTo_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="64c85-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="64c85-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="64c85-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="64c85-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="64c85-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="64c85-105">**Schema file**</span></span> <br/> |<span data-ttu-id="64c85-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="64c85-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="64c85-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="64c85-107">**Extension base**</span></span> <br/> |<span data-ttu-id="64c85-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="64c85-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="64c85-109">定义</span><span class="sxs-lookup"><span data-stu-id="64c85-109">Definition</span></span>

```XML
          <xs:complexType name="RelCubBezTo_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="64c85-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="64c85-110">Elements and attributes</span></span>

<span data-ttu-id="64c85-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="64c85-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="64c85-112">子元素</span><span class="sxs-lookup"><span data-stu-id="64c85-112">Child elements</span></span>

|<span data-ttu-id="64c85-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="64c85-113">**Element**</span></span>|<span data-ttu-id="64c85-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="64c85-114">**Type**</span></span>|<span data-ttu-id="64c85-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="64c85-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="64c85-116">Cell</span><span class="sxs-lookup"><span data-stu-id="64c85-116">Cell</span></span>](cell-element-relcubbezto-rowvisio-xml.md) <br/> |[<span data-ttu-id="64c85-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="64c85-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="64c85-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="64c85-118">Attributes</span></span>

<span data-ttu-id="64c85-119">无。</span><span class="sxs-lookup"><span data-stu-id="64c85-119">None.</span></span>
  

