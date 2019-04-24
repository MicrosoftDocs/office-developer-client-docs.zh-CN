---
title: FooterMargin_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: db8d1e5b-cd29-f9ff-994a-25c28672db81
ms.openlocfilehash: 69f5ce201bd1859aa716e0967939f0c1e5a5a2c6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346044"
---
# <a name="footermargintype-complextype-visio-xml"></a><span data-ttu-id="7bfd5-102">FooterMargin_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="7bfd5-102">FooterMargin_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="7bfd5-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="7bfd5-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7bfd5-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7bfd5-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="7bfd5-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7bfd5-105">**Schema file**</span></span> <br/> |<span data-ttu-id="7bfd5-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="7bfd5-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="7bfd5-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="7bfd5-107">**Extension base**</span></span> <br/> |<span data-ttu-id="7bfd5-108">xsd: double</span><span class="sxs-lookup"><span data-stu-id="7bfd5-108">xsd:double</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7bfd5-109">定义</span><span class="sxs-lookup"><span data-stu-id="7bfd5-109">Definition</span></span>

```XML
      <xs:complexType name="FooterMargin_Type">
        <xs:complexContent>
        <xs:extension base="xsd:double">
      
    <xs:attribute name="Unit"
  type="xsd:string"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7bfd5-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7bfd5-110">Elements and attributes</span></span>

<span data-ttu-id="7bfd5-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="7bfd5-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="7bfd5-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7bfd5-112">Child elements</span></span>

<span data-ttu-id="7bfd5-113">无。</span><span class="sxs-lookup"><span data-stu-id="7bfd5-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="7bfd5-114">属性</span><span class="sxs-lookup"><span data-stu-id="7bfd5-114">Attributes</span></span>

|<span data-ttu-id="7bfd5-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="7bfd5-115">**Attribute**</span></span>|<span data-ttu-id="7bfd5-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="7bfd5-116">**Type**</span></span>|<span data-ttu-id="7bfd5-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="7bfd5-117">**Required**</span></span>|<span data-ttu-id="7bfd5-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="7bfd5-118">**Description**</span></span>|<span data-ttu-id="7bfd5-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="7bfd5-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7bfd5-120">Unit</span><span class="sxs-lookup"><span data-stu-id="7bfd5-120">Unit</span></span>  <br/> |<span data-ttu-id="7bfd5-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7bfd5-121">xsd:string</span></span>  <br/> |<span data-ttu-id="7bfd5-122">可选</span><span class="sxs-lookup"><span data-stu-id="7bfd5-122">optional</span></span>  <br/> ||<span data-ttu-id="7bfd5-123">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="7bfd5-123">Values of the xsd:string type.</span></span>  <br/> |
   

