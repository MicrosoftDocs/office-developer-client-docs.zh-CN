---
title: UserRow_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae2e014b-2e53-c317-0bfa-9a0cb1e09588
ms.openlocfilehash: 54edb9a1396582eae87db8735c4f75bd9597f1f3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399667"
---
# <a name="userrowtype-complextype-visio-xml"></a><span data-ttu-id="ddfcc-102">UserRow_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ddfcc-102">UserRow_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="ddfcc-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ddfcc-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ddfcc-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ddfcc-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ddfcc-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ddfcc-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ddfcc-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="ddfcc-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ddfcc-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ddfcc-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ddfcc-108">NamedRow_Type</span><span class="sxs-lookup"><span data-stu-id="ddfcc-108">NamedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ddfcc-109">定义</span><span class="sxs-lookup"><span data-stu-id="ddfcc-109">Definition</span></span>

```XML
          <xs:complexType name="UserRow_Type">
          
          <xs:complexContent>
          <xs:extension base="NamedRow_Type">
          <xs:all>
    <xs:element name="Cell"  type="Cell_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:all>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ddfcc-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ddfcc-110">Elements and attributes</span></span>

<span data-ttu-id="ddfcc-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ddfcc-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ddfcc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ddfcc-112">Child elements</span></span>

|<span data-ttu-id="ddfcc-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="ddfcc-113">**Element**</span></span>|<span data-ttu-id="ddfcc-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="ddfcc-114">**Type**</span></span>|<span data-ttu-id="ddfcc-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ddfcc-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ddfcc-116">Cell</span><span class="sxs-lookup"><span data-stu-id="ddfcc-116">Cell</span></span>](cell-element-user-defined-cells-sectionvisio-xml.md) <br/> |[<span data-ttu-id="ddfcc-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="ddfcc-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="ddfcc-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="ddfcc-118">Attributes</span></span>

<span data-ttu-id="ddfcc-119">无。</span><span class="sxs-lookup"><span data-stu-id="ddfcc-119">None.</span></span>
  

