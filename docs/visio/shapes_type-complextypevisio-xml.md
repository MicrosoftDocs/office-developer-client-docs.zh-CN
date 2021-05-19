---
title: 'Shapes_Type complexType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7ef84fa3-6fb8-c570-a5ee-3c1c9dddb86c
ms.openlocfilehash: 798af3d68df6c430fffb318e5e19c83aea441ca0
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542084"
---
# <a name="shapes_type-complextype-visio-xml"></a><span data-ttu-id="4bc64-102">Shapes_Type complexType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="4bc64-102">Shapes_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="4bc64-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="4bc64-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4bc64-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4bc64-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="4bc64-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4bc64-105">**Schema file**</span></span> <br/> |<span data-ttu-id="4bc64-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="4bc64-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="4bc64-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="4bc64-107">**Extension base**</span></span> <br/> |<span data-ttu-id="4bc64-108">无</span><span class="sxs-lookup"><span data-stu-id="4bc64-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4bc64-109">定义</span><span class="sxs-lookup"><span data-stu-id="4bc64-109">Definition</span></span>

```XML
          <xs:complexType name="Shapes_Type">
          
          <xs:sequence>
    <xs:element name="Shape"  type="ShapeSheet_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4bc64-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4bc64-110">Elements and attributes</span></span>

<span data-ttu-id="4bc64-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4bc64-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="4bc64-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4bc64-112">Child elements</span></span>

|<span data-ttu-id="4bc64-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="4bc64-113">**Element**</span></span>|<span data-ttu-id="4bc64-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="4bc64-114">**Type**</span></span>|<span data-ttu-id="4bc64-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="4bc64-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4bc64-116">Shape</span><span class="sxs-lookup"><span data-stu-id="4bc64-116">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4bc64-117">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="4bc64-117">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="4bc64-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="4bc64-118">Attributes</span></span>

<span data-ttu-id="4bc64-119">无。</span><span class="sxs-lookup"><span data-stu-id="4bc64-119">None.</span></span>
  

