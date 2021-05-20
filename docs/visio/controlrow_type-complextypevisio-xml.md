---
title: 'ControlRow_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7f9ee251-e685-e56c-3c8a-cb727ad62064
ms.openlocfilehash: a6bd54f425e211716ce7dc9a7206a3d079383d5d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538667"
---
# <a name="controlrow_type-complextype-visio-xml"></a><span data-ttu-id="533b3-102">ControlRow_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="533b3-102">ControlRow_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="533b3-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="533b3-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="533b3-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="533b3-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="533b3-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="533b3-105">**Schema file**</span></span> <br/> |<span data-ttu-id="533b3-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="533b3-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="533b3-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="533b3-107">**Extension base**</span></span> <br/> |<span data-ttu-id="533b3-108">NamedIndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="533b3-108">NamedIndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="533b3-109">定义</span><span class="sxs-lookup"><span data-stu-id="533b3-109">Definition</span></span>

```XML
          <xs:complexType name="ControlRow_Type">
          
          <xs:complexContent>
          <xs:extension base="NamedIndexedRow_Type">
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

## <a name="elements-and-attributes"></a><span data-ttu-id="533b3-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="533b3-110">Elements and attributes</span></span>

<span data-ttu-id="533b3-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="533b3-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="533b3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="533b3-112">Child elements</span></span>

|<span data-ttu-id="533b3-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="533b3-113">**Element**</span></span>|<span data-ttu-id="533b3-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="533b3-114">**Type**</span></span>|<span data-ttu-id="533b3-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="533b3-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="533b3-116">Cell</span><span class="sxs-lookup"><span data-stu-id="533b3-116">Cell</span></span>](cell-element-controls-rowvisio-xml.md) <br/> |[<span data-ttu-id="533b3-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="533b3-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="533b3-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="533b3-118">Attributes</span></span>

<span data-ttu-id="533b3-119">无。</span><span class="sxs-lookup"><span data-stu-id="533b3-119">None.</span></span>
  

