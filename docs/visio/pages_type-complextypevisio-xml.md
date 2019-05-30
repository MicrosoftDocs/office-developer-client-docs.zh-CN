---
title: Pages_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 13508e59-e29a-ca70-676b-c5b23ca8e3d0
ms.openlocfilehash: 4615f365448b96981088352f9f2d6e98255e4101
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538940"
---
# <a name="pagestype-complextype-visio-xml"></a><span data-ttu-id="a51ec-102">Pages_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="a51ec-102">Pages_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="a51ec-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="a51ec-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a51ec-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a51ec-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="a51ec-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a51ec-105">**Schema file**</span></span> <br/> |<span data-ttu-id="a51ec-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="a51ec-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="a51ec-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="a51ec-107">**Extension base**</span></span> <br/> |<span data-ttu-id="a51ec-108">无</span><span class="sxs-lookup"><span data-stu-id="a51ec-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a51ec-109">定义</span><span class="sxs-lookup"><span data-stu-id="a51ec-109">Definition</span></span>

```XML
          <xs:complexType name="Pages_Type">
          
          <xs:sequence>
    <xs:element name="Page"  type="Page_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a51ec-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a51ec-110">Elements and attributes</span></span>

<span data-ttu-id="a51ec-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="a51ec-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="a51ec-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a51ec-112">Child elements</span></span>

|<span data-ttu-id="a51ec-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="a51ec-113">**Element**</span></span>|<span data-ttu-id="a51ec-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="a51ec-114">**Type**</span></span>|<span data-ttu-id="a51ec-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a51ec-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a51ec-116">Page</span><span class="sxs-lookup"><span data-stu-id="a51ec-116">Page</span></span>](page-element-pages_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a51ec-117">Page_Type</span><span class="sxs-lookup"><span data-stu-id="a51ec-117">Page_Type</span></span>](page_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="a51ec-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="a51ec-118">Attributes</span></span>

<span data-ttu-id="a51ec-119">无。</span><span class="sxs-lookup"><span data-stu-id="a51ec-119">None.</span></span>
  

