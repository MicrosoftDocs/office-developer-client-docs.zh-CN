---
title: Control_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9eba241a-e64d-6bac-6d8e-a049e4febe96
ms.openlocfilehash: 13eb8f24377cb7c1b34d41c6ca963c545c3806e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780011"
---
# <a name="controltype-complextype-visio-xml"></a><span data-ttu-id="8bc75-102">Control_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="8bc75-102">Control_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="8bc75-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="8bc75-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8bc75-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8bc75-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="8bc75-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8bc75-105">**Schema file**</span></span> <br/> |<span data-ttu-id="8bc75-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="8bc75-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="8bc75-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="8bc75-107">**Extension base**</span></span> <br/> |<span data-ttu-id="8bc75-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="8bc75-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8bc75-109">定义</span><span class="sxs-lookup"><span data-stu-id="8bc75-109">Definition</span></span>

```XML
          <xs:complexType name="Control_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="ControlRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8bc75-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8bc75-110">Elements and attributes</span></span>

<span data-ttu-id="8bc75-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="8bc75-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="8bc75-112">子元素</span><span class="sxs-lookup"><span data-stu-id="8bc75-112">Child elements</span></span>

|<span data-ttu-id="8bc75-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="8bc75-113">**Element**</span></span>|<span data-ttu-id="8bc75-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="8bc75-114">**Type**</span></span>|<span data-ttu-id="8bc75-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="8bc75-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8bc75-116">Row</span><span class="sxs-lookup"><span data-stu-id="8bc75-116">Row</span></span>](row-element-controls-sectionvisio-xml.md) <br/> |[<span data-ttu-id="8bc75-117">ControlRow_Type</span><span class="sxs-lookup"><span data-stu-id="8bc75-117">ControlRow_Type</span></span>](controlrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="8bc75-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="8bc75-118">Attributes</span></span>

<span data-ttu-id="8bc75-119">无。</span><span class="sxs-lookup"><span data-stu-id="8bc75-119">None.</span></span>
  

