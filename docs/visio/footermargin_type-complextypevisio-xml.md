---
title: FooterMargin_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: db8d1e5b-cd29-f9ff-994a-25c28672db81
ms.openlocfilehash: f5838855a5c21b699c7a81849b9afc40790f3d01
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538639"
---
# <a name="footermargintype-complextype-visio-xml"></a><span data-ttu-id="1be31-102">FooterMargin_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="1be31-102">FooterMargin_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="1be31-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1be31-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1be31-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1be31-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1be31-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1be31-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1be31-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="1be31-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1be31-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1be31-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1be31-108">xsd: double</span><span class="sxs-lookup"><span data-stu-id="1be31-108">xsd:double</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1be31-109">定义</span><span class="sxs-lookup"><span data-stu-id="1be31-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="1be31-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1be31-110">Elements and attributes</span></span>

<span data-ttu-id="1be31-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="1be31-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1be31-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1be31-112">Child elements</span></span>

<span data-ttu-id="1be31-113">无。</span><span class="sxs-lookup"><span data-stu-id="1be31-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1be31-114">属性</span><span class="sxs-lookup"><span data-stu-id="1be31-114">Attributes</span></span>

|<span data-ttu-id="1be31-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="1be31-115">**Attribute**</span></span>|<span data-ttu-id="1be31-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="1be31-116">**Type**</span></span>|<span data-ttu-id="1be31-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="1be31-117">**Required**</span></span>|<span data-ttu-id="1be31-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="1be31-118">**Description**</span></span>|<span data-ttu-id="1be31-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1be31-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1be31-120">Unit</span><span class="sxs-lookup"><span data-stu-id="1be31-120">Unit</span></span>  <br/> |<span data-ttu-id="1be31-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="1be31-121">xsd:string</span></span>  <br/> |<span data-ttu-id="1be31-122">可选</span><span class="sxs-lookup"><span data-stu-id="1be31-122">optional</span></span>  <br/> ||<span data-ttu-id="1be31-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1be31-123">Values of the xsd:string type.</span></span>  <br/> |
   

