---
title: Tabs_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b97155ce-f0d2-e35c-bc58-e288f653ce2c
ms.openlocfilehash: f3c484fe8656d97484dd136175506bf60f0e299b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538842"
---
# <a name="tabstype-complextype-visio-xml"></a><span data-ttu-id="f72a3-102">Tabs_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f72a3-102">Tabs_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="f72a3-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f72a3-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f72a3-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f72a3-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f72a3-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f72a3-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f72a3-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="f72a3-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f72a3-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f72a3-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f72a3-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="f72a3-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f72a3-109">定义</span><span class="sxs-lookup"><span data-stu-id="f72a3-109">Definition</span></span>

```XML
          <xs:complexType name="Tabs_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="TabsRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f72a3-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f72a3-110">Elements and attributes</span></span>

<span data-ttu-id="f72a3-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="f72a3-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f72a3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f72a3-112">Child elements</span></span>

|<span data-ttu-id="f72a3-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f72a3-113">**Element**</span></span>|<span data-ttu-id="f72a3-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="f72a3-114">**Type**</span></span>|<span data-ttu-id="f72a3-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f72a3-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f72a3-116">Row</span><span class="sxs-lookup"><span data-stu-id="f72a3-116">Row</span></span>](row-element-tabs-sectionvisio-xml.md) <br/> |[<span data-ttu-id="f72a3-117">TabsRow_Type</span><span class="sxs-lookup"><span data-stu-id="f72a3-117">TabsRow_Type</span></span>](tabsrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="f72a3-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="f72a3-118">Attributes</span></span>

<span data-ttu-id="f72a3-119">无。</span><span class="sxs-lookup"><span data-stu-id="f72a3-119">None.</span></span>
  

