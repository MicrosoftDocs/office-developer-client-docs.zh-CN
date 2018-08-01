---
title: FillGradient_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 82545cdc-890d-1b2f-9c8f-4740f32d0ed7
ms.openlocfilehash: 15500f9ffa8375a8b34a09cd9bd72efa7ad82768
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780235"
---
# <a name="fillgradienttype-complextype-visio-xml"></a><span data-ttu-id="be52c-102">FillGradient_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="be52c-102">FillGradient_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="be52c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="be52c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="be52c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="be52c-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="be52c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="be52c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="be52c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="be52c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="be52c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="be52c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="be52c-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="be52c-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="be52c-109">定义</span><span class="sxs-lookup"><span data-stu-id="be52c-109">Definition</span></span>

```XML
          <xs:complexType name="FillGradient_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="FillGradientRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="be52c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="be52c-110">Elements and attributes</span></span>

<span data-ttu-id="be52c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="be52c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="be52c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="be52c-112">Child elements</span></span>

|<span data-ttu-id="be52c-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="be52c-113">**Element**</span></span>|<span data-ttu-id="be52c-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="be52c-114">**Type**</span></span>|<span data-ttu-id="be52c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="be52c-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="be52c-116">Row</span><span class="sxs-lookup"><span data-stu-id="be52c-116">Row</span></span>](row-element-fill-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="be52c-117">FillGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="be52c-117">FillGradientRow_Type</span></span>](fillgradientrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="be52c-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="be52c-118">Attributes</span></span>

<span data-ttu-id="be52c-119">无。</span><span class="sxs-lookup"><span data-stu-id="be52c-119">None.</span></span>
  

