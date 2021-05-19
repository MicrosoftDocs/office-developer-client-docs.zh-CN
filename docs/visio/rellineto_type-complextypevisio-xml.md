---
title: 'RelLineTo_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e5504166-653d-15d2-75eb-9b36f376b788
ms.openlocfilehash: 8681bf819a36a8c41171d558fb48b73fc1aeb87b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542707"
---
# <a name="rellineto_type-complextype-visio-xml"></a><span data-ttu-id="4a784-102">RelLineTo_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="4a784-102">RelLineTo_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="4a784-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="4a784-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4a784-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4a784-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="4a784-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4a784-105">**Schema file**</span></span> <br/> |<span data-ttu-id="4a784-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="4a784-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="4a784-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="4a784-107">**Extension base**</span></span> <br/> |<span data-ttu-id="4a784-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="4a784-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4a784-109">定义</span><span class="sxs-lookup"><span data-stu-id="4a784-109">Definition</span></span>

```XML
          <xs:complexType name="RelLineTo_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="4a784-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4a784-110">Elements and attributes</span></span>

<span data-ttu-id="4a784-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4a784-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="4a784-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4a784-112">Child elements</span></span>

|<span data-ttu-id="4a784-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="4a784-113">**Element**</span></span>|<span data-ttu-id="4a784-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="4a784-114">**Type**</span></span>|<span data-ttu-id="4a784-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="4a784-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4a784-116">Cell</span><span class="sxs-lookup"><span data-stu-id="4a784-116">Cell</span></span>](cell-element-rellineto-rowvisio-xml.md) <br/> |[<span data-ttu-id="4a784-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="4a784-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="4a784-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="4a784-118">Attributes</span></span>

<span data-ttu-id="4a784-119">无。</span><span class="sxs-lookup"><span data-stu-id="4a784-119">None.</span></span>
  

