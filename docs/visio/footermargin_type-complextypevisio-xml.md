---
title: FooterMargin_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: db8d1e5b-cd29-f9ff-994a-25c28672db81
ms.openlocfilehash: f2cfa7c9d27940308c95318f8a743a4bdd6cb45f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780307"
---
# <a name="footermargintype-complextype-visio-xml"></a><span data-ttu-id="dfb53-102">FooterMargin_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="dfb53-102">FooterMargin_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="dfb53-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="dfb53-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dfb53-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="dfb53-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="dfb53-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="dfb53-105">**Schema file**</span></span> <br/> |<span data-ttu-id="dfb53-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="dfb53-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="dfb53-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="dfb53-107">**Extension base**</span></span> <br/> |<span data-ttu-id="dfb53-108">化</span><span class="sxs-lookup"><span data-stu-id="dfb53-108">xsd:double</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="dfb53-109">定义</span><span class="sxs-lookup"><span data-stu-id="dfb53-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="dfb53-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="dfb53-110">Elements and attributes</span></span>

<span data-ttu-id="dfb53-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="dfb53-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="dfb53-112">子元素</span><span class="sxs-lookup"><span data-stu-id="dfb53-112">Child elements</span></span>

<span data-ttu-id="dfb53-113">无。</span><span class="sxs-lookup"><span data-stu-id="dfb53-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="dfb53-114">属性</span><span class="sxs-lookup"><span data-stu-id="dfb53-114">Attributes</span></span>

|<span data-ttu-id="dfb53-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="dfb53-115">**Attribute**</span></span>|<span data-ttu-id="dfb53-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="dfb53-116">**Type**</span></span>|<span data-ttu-id="dfb53-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="dfb53-117">**Required**</span></span>|<span data-ttu-id="dfb53-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="dfb53-118">**Description**</span></span>|<span data-ttu-id="dfb53-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="dfb53-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dfb53-120">单位</span><span class="sxs-lookup"><span data-stu-id="dfb53-120">Unit</span></span>  <br/> |<span data-ttu-id="dfb53-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="dfb53-121">xsd:string</span></span>  <br/> |<span data-ttu-id="dfb53-122">可选</span><span class="sxs-lookup"><span data-stu-id="dfb53-122">optional</span></span>  <br/> ||<span data-ttu-id="dfb53-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dfb53-123">Values of the xsd:string type.</span></span>  <br/> |
   

