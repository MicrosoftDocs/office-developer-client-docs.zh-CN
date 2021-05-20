---
title: 'CharacterRow_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 61c99712-d451-408a-de15-fb088605b07c
ms.openlocfilehash: 3d54921ca571ff3ba4643b2e1d18ee9d7d1bc8c3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540194"
---
# <a name="characterrow_type-complextype-visio-xml"></a><span data-ttu-id="83ebe-102">CharacterRow_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="83ebe-102">CharacterRow_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="83ebe-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="83ebe-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="83ebe-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="83ebe-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="83ebe-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="83ebe-105">**Schema file**</span></span> <br/> |<span data-ttu-id="83ebe-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="83ebe-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="83ebe-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="83ebe-107">**Extension base**</span></span> <br/> |<span data-ttu-id="83ebe-108">IndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="83ebe-108">IndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="83ebe-109">定义</span><span class="sxs-lookup"><span data-stu-id="83ebe-109">Definition</span></span>

```XML
          <xs:complexType name="CharacterRow_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="83ebe-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="83ebe-110">Elements and attributes</span></span>

<span data-ttu-id="83ebe-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="83ebe-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="83ebe-112">子元素</span><span class="sxs-lookup"><span data-stu-id="83ebe-112">Child elements</span></span>

|<span data-ttu-id="83ebe-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="83ebe-113">**Element**</span></span>|<span data-ttu-id="83ebe-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="83ebe-114">**Type**</span></span>|<span data-ttu-id="83ebe-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="83ebe-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="83ebe-116">Cell</span><span class="sxs-lookup"><span data-stu-id="83ebe-116">Cell</span></span>](cell-element-character-sectionvisio-xml.md) <br/> |[<span data-ttu-id="83ebe-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="83ebe-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="83ebe-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="83ebe-118">Attributes</span></span>

<span data-ttu-id="83ebe-119">无。</span><span class="sxs-lookup"><span data-stu-id="83ebe-119">None.</span></span>
  

