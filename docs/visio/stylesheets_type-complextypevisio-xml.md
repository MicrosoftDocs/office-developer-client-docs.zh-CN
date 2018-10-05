---
title: StyleSheets_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2603bc5-86bd-df29-43c2-25a39419ad1e
ms.openlocfilehash: 1992f0e31ae972320f80f99d94164fbd1dbc6d45
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395740"
---
# <a name="stylesheetstype-complextype-visio-xml"></a><span data-ttu-id="b9eb9-102">StyleSheets_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b9eb9-102">StyleSheets_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="b9eb9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b9eb9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b9eb9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b9eb9-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b9eb9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b9eb9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b9eb9-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="b9eb9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b9eb9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b9eb9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b9eb9-108">无</span><span class="sxs-lookup"><span data-stu-id="b9eb9-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b9eb9-109">定义</span><span class="sxs-lookup"><span data-stu-id="b9eb9-109">Definition</span></span>

```XML
          <xs:complexType name="StyleSheets_Type">
          
          <xs:sequence>
    <xs:element name="StyleSheet"  type="StyleSheet_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b9eb9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b9eb9-110">Elements and attributes</span></span>

<span data-ttu-id="b9eb9-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b9eb9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b9eb9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b9eb9-112">Child elements</span></span>

|<span data-ttu-id="b9eb9-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="b9eb9-113">**Element**</span></span>|<span data-ttu-id="b9eb9-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="b9eb9-114">**Type**</span></span>|<span data-ttu-id="b9eb9-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="b9eb9-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b9eb9-116">样式表</span><span class="sxs-lookup"><span data-stu-id="b9eb9-116">StyleSheet</span></span>](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b9eb9-117">StyleSheet_Type</span><span class="sxs-lookup"><span data-stu-id="b9eb9-117">StyleSheet_Type</span></span>](stylesheet_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="b9eb9-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="b9eb9-118">Attributes</span></span>

<span data-ttu-id="b9eb9-119">无。</span><span class="sxs-lookup"><span data-stu-id="b9eb9-119">None.</span></span>
  

