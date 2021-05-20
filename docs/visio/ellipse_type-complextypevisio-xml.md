---
title: 'Ellipse_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c67dc78e-6639-e32f-4909-945001659d30
ms.openlocfilehash: d5e73eeb0dd4b4ead485b1bcd99585a2cd766c51
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539910"
---
# <a name="ellipse_type-complextype-visio-xml"></a><span data-ttu-id="f2651-102">Ellipse_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="f2651-102">Ellipse_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="f2651-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f2651-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f2651-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f2651-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f2651-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f2651-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f2651-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="f2651-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f2651-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f2651-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f2651-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="f2651-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f2651-109">定义</span><span class="sxs-lookup"><span data-stu-id="f2651-109">Definition</span></span>

```XML
          <xs:complexType name="Ellipse_Type">
          
          <xs:complexContent>
          <xs:extension base="GeometryRow_Type">
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

## <a name="elements-and-attributes"></a><span data-ttu-id="f2651-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f2651-110">Elements and attributes</span></span>

<span data-ttu-id="f2651-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f2651-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f2651-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f2651-112">Child elements</span></span>

|<span data-ttu-id="f2651-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f2651-113">**Element**</span></span>|<span data-ttu-id="f2651-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="f2651-114">**Type**</span></span>|<span data-ttu-id="f2651-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f2651-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f2651-116">Cell</span><span class="sxs-lookup"><span data-stu-id="f2651-116">Cell</span></span>](cell-element-ellipse-rowvisio-xml.md) <br/> |[<span data-ttu-id="f2651-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="f2651-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="f2651-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="f2651-118">Attributes</span></span>

<span data-ttu-id="f2651-119">无。</span><span class="sxs-lookup"><span data-stu-id="f2651-119">None.</span></span>
  

