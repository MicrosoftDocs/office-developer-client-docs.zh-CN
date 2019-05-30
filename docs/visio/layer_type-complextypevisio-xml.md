---
title: Layer_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f92ac1cc-fad2-dab9-5507-838c006ed633
ms.openlocfilehash: 1614a2eb8606144d28fc0422d9fc2c44c48910d1
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541286"
---
# <a name="layertype-complextype-visio-xml"></a><span data-ttu-id="20193-102">Layer_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="20193-102">Layer_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="20193-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="20193-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="20193-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="20193-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="20193-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="20193-105">**Schema file**</span></span> <br/> |<span data-ttu-id="20193-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="20193-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="20193-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="20193-107">**Extension base**</span></span> <br/> |<span data-ttu-id="20193-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="20193-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="20193-109">定义</span><span class="sxs-lookup"><span data-stu-id="20193-109">Definition</span></span>

```XML
          <xs:complexType name="Layer_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="LayerRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="20193-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="20193-110">Elements and attributes</span></span>

<span data-ttu-id="20193-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="20193-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="20193-112">子元素</span><span class="sxs-lookup"><span data-stu-id="20193-112">Child elements</span></span>

|<span data-ttu-id="20193-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="20193-113">**Element**</span></span>|<span data-ttu-id="20193-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="20193-114">**Type**</span></span>|<span data-ttu-id="20193-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="20193-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="20193-116">Row</span><span class="sxs-lookup"><span data-stu-id="20193-116">Row</span></span>](row-element-layer-sectionvisio-xml.md) <br/> |[<span data-ttu-id="20193-117">LayerRow_Type</span><span class="sxs-lookup"><span data-stu-id="20193-117">LayerRow_Type</span></span>](layerrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="20193-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="20193-118">Attributes</span></span>

<span data-ttu-id="20193-119">无。</span><span class="sxs-lookup"><span data-stu-id="20193-119">None.</span></span>
  

