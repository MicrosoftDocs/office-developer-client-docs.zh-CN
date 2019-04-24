---
title: RelCubBezTo_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 004dc563-d089-230f-0055-038b72eebbed
ms.openlocfilehash: 6ec426ef2c7afd913d904c8ceba938549727c799
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319962"
---
# <a name="relcubbeztotype-complextype-visio-xml"></a><span data-ttu-id="a73f0-102">RelCubBezTo_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="a73f0-102">RelCubBezTo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="a73f0-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="a73f0-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a73f0-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a73f0-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="a73f0-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a73f0-105">**Schema file**</span></span> <br/> |<span data-ttu-id="a73f0-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="a73f0-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="a73f0-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="a73f0-107">**Extension base**</span></span> <br/> |<span data-ttu-id="a73f0-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="a73f0-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a73f0-109">定义</span><span class="sxs-lookup"><span data-stu-id="a73f0-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="a73f0-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a73f0-110">Elements and attributes</span></span>

<span data-ttu-id="a73f0-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="a73f0-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="a73f0-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a73f0-112">Child elements</span></span>

|<span data-ttu-id="a73f0-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="a73f0-113">**Element**</span></span>|<span data-ttu-id="a73f0-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="a73f0-114">**Type**</span></span>|<span data-ttu-id="a73f0-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a73f0-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a73f0-116">Cell</span><span class="sxs-lookup"><span data-stu-id="a73f0-116">Cell</span></span>](cell-element-relcubbezto-rowvisio-xml.md) <br/> |[<span data-ttu-id="a73f0-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="a73f0-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="a73f0-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="a73f0-118">Attributes</span></span>

<span data-ttu-id="a73f0-119">无。</span><span class="sxs-lookup"><span data-stu-id="a73f0-119">None.</span></span>
  

