---
title: 'ConnectionRow_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 14a92d20-78fb-0043-7360-7dfda52fb9c7
ms.openlocfilehash: ad8f4f877153b871b897be7da5d5e09a5ff070fb
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538730"
---
# <a name="connectionrow_type-complextype-visio-xml"></a><span data-ttu-id="bd0cd-102">ConnectionRow_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="bd0cd-102">ConnectionRow_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="bd0cd-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="bd0cd-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bd0cd-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="bd0cd-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="bd0cd-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="bd0cd-105">**Schema file**</span></span> <br/> |<span data-ttu-id="bd0cd-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="bd0cd-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="bd0cd-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="bd0cd-107">**Extension base**</span></span> <br/> |<span data-ttu-id="bd0cd-108">NamedIndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="bd0cd-108">NamedIndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="bd0cd-109">定义</span><span class="sxs-lookup"><span data-stu-id="bd0cd-109">Definition</span></span>

```XML
          <xs:complexType name="ConnectionRow_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="bd0cd-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="bd0cd-110">Elements and attributes</span></span>

<span data-ttu-id="bd0cd-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="bd0cd-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="bd0cd-112">子元素</span><span class="sxs-lookup"><span data-stu-id="bd0cd-112">Child elements</span></span>

|<span data-ttu-id="bd0cd-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="bd0cd-113">**Element**</span></span>|<span data-ttu-id="bd0cd-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="bd0cd-114">**Type**</span></span>|<span data-ttu-id="bd0cd-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="bd0cd-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bd0cd-116">Cell</span><span class="sxs-lookup"><span data-stu-id="bd0cd-116">Cell</span></span>](cell-element-connection-rowvisio-xml.md) <br/> |[<span data-ttu-id="bd0cd-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="bd0cd-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="bd0cd-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="bd0cd-118">Attributes</span></span>

<span data-ttu-id="bd0cd-119">无。</span><span class="sxs-lookup"><span data-stu-id="bd0cd-119">None.</span></span>
  

