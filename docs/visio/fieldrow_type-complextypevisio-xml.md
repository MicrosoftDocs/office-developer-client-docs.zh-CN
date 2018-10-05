---
title: FieldRow_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3474d268-4435-cb4d-9c66-a30924635e20
ms.openlocfilehash: 5f59ca23fa83d98622624cc20544f9b482ce5378
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400780"
---
# <a name="fieldrowtype-complextype-visio-xml"></a><span data-ttu-id="f4503-102">FieldRow_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f4503-102">FieldRow_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="f4503-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f4503-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f4503-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f4503-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f4503-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f4503-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f4503-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="f4503-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f4503-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f4503-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f4503-108">IndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="f4503-108">IndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f4503-109">定义</span><span class="sxs-lookup"><span data-stu-id="f4503-109">Definition</span></span>

```XML
          <xs:complexType name="FieldRow_Type">
          
          <xs:complexContent>
          <xs:extension base="IndexedRow_Type">
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

## <a name="elements-and-attributes"></a><span data-ttu-id="f4503-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f4503-110">Elements and attributes</span></span>

<span data-ttu-id="f4503-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f4503-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f4503-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f4503-112">Child elements</span></span>

|<span data-ttu-id="f4503-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f4503-113">**Element**</span></span>|<span data-ttu-id="f4503-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="f4503-114">**Type**</span></span>|<span data-ttu-id="f4503-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f4503-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f4503-116">Cell</span><span class="sxs-lookup"><span data-stu-id="f4503-116">Cell</span></span>](cell-element-field-sectionvisio-xml.md) <br/> |[<span data-ttu-id="f4503-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="f4503-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="f4503-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="f4503-118">Attributes</span></span>

<span data-ttu-id="f4503-119">无。</span><span class="sxs-lookup"><span data-stu-id="f4503-119">None.</span></span>
  

