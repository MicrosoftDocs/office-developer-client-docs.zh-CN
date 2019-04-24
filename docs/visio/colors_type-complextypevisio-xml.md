---
title: Colors_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09f997b5-1f3c-ddff-41f2-af84960266ff
ms.openlocfilehash: e447ceb6fc0e6b79ec6e62b5f3b73a32cec589d9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359022"
---
# <a name="colorstype-complextype-visio-xml"></a><span data-ttu-id="b6635-102">Colors_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="b6635-102">Colors_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="b6635-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b6635-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b6635-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b6635-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b6635-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b6635-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b6635-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="b6635-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b6635-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b6635-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b6635-108">无</span><span class="sxs-lookup"><span data-stu-id="b6635-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b6635-109">定义</span><span class="sxs-lookup"><span data-stu-id="b6635-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="b6635-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b6635-110">Elements and attributes</span></span>

<span data-ttu-id="b6635-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b6635-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b6635-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b6635-112">Child elements</span></span>

|<span data-ttu-id="b6635-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="b6635-113">**Element**</span></span>|<span data-ttu-id="b6635-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="b6635-114">**Type**</span></span>|<span data-ttu-id="b6635-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="b6635-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b6635-116">ColorEntry</span><span class="sxs-lookup"><span data-stu-id="b6635-116">ColorEntry</span></span>](colorentry-element-colors_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b6635-117">ColorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="b6635-117">ColorEntry_Type</span></span>](colorentry_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="b6635-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="b6635-118">Attributes</span></span>

<span data-ttu-id="b6635-119">无。</span><span class="sxs-lookup"><span data-stu-id="b6635-119">None.</span></span>
  

