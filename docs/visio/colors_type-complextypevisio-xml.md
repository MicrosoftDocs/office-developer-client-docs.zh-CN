---
title: 'Colors_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09f997b5-1f3c-ddff-41f2-af84960266ff
ms.openlocfilehash: bddcb93451bfb6d1b519720040a9e3875dc2ec5c
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540138"
---
# <a name="colors_type-complextype-visio-xml"></a><span data-ttu-id="19e78-102">Colors_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="19e78-102">Colors_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="19e78-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="19e78-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="19e78-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="19e78-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="19e78-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="19e78-105">**Schema file**</span></span> <br/> |<span data-ttu-id="19e78-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="19e78-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="19e78-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="19e78-107">**Extension base**</span></span> <br/> |<span data-ttu-id="19e78-108">无</span><span class="sxs-lookup"><span data-stu-id="19e78-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="19e78-109">定义</span><span class="sxs-lookup"><span data-stu-id="19e78-109">Definition</span></span>

```XML
          <xs:complexType name="Colors_Type">
          
          <xs:sequence>
    <xs:element name="ColorEntry"  type="ColorEntry_Type"
     minOccurs="1"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="19e78-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="19e78-110">Elements and attributes</span></span>

<span data-ttu-id="19e78-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="19e78-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="19e78-112">子元素</span><span class="sxs-lookup"><span data-stu-id="19e78-112">Child elements</span></span>

|<span data-ttu-id="19e78-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="19e78-113">**Element**</span></span>|<span data-ttu-id="19e78-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="19e78-114">**Type**</span></span>|<span data-ttu-id="19e78-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="19e78-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="19e78-116">ColorEntry</span><span class="sxs-lookup"><span data-stu-id="19e78-116">ColorEntry</span></span>](colorentry-element-colors_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="19e78-117">ColorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="19e78-117">ColorEntry_Type</span></span>](colorentry_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="19e78-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="19e78-118">Attributes</span></span>

<span data-ttu-id="19e78-119">无。</span><span class="sxs-lookup"><span data-stu-id="19e78-119">None.</span></span>
  

