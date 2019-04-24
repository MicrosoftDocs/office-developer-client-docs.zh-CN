---
title: HeaderMargin_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 756b87f6-aa0e-c643-c733-7db788f63ac8
ms.openlocfilehash: 9bb32471f1384c89e02e9ffdbcceebfc48d2b22e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330049"
---
# <a name="headermargintype-complextype-visio-xml"></a><span data-ttu-id="b20e6-102">HeaderMargin_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="b20e6-102">HeaderMargin_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="b20e6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b20e6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b20e6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b20e6-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b20e6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b20e6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b20e6-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="b20e6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b20e6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b20e6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b20e6-108">xsd: double</span><span class="sxs-lookup"><span data-stu-id="b20e6-108">xsd:double</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b20e6-109">定义</span><span class="sxs-lookup"><span data-stu-id="b20e6-109">Definition</span></span>

```XML
      <xs:complexType name="HeaderMargin_Type">
        <xs:complexContent>
        <xs:extension base="xsd:double">
      
    <xs:attribute name="Unit"
  type="xsd:string"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b20e6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b20e6-110">Elements and attributes</span></span>

<span data-ttu-id="b20e6-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b20e6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b20e6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b20e6-112">Child elements</span></span>

<span data-ttu-id="b20e6-113">无。</span><span class="sxs-lookup"><span data-stu-id="b20e6-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b20e6-114">属性</span><span class="sxs-lookup"><span data-stu-id="b20e6-114">Attributes</span></span>

|<span data-ttu-id="b20e6-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="b20e6-115">**Attribute**</span></span>|<span data-ttu-id="b20e6-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="b20e6-116">**Type**</span></span>|<span data-ttu-id="b20e6-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="b20e6-117">**Required**</span></span>|<span data-ttu-id="b20e6-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="b20e6-118">**Description**</span></span>|<span data-ttu-id="b20e6-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b20e6-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b20e6-120">Unit</span><span class="sxs-lookup"><span data-stu-id="b20e6-120">Unit</span></span>  <br/> |<span data-ttu-id="b20e6-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b20e6-121">xsd:string</span></span>  <br/> |<span data-ttu-id="b20e6-122">可选</span><span class="sxs-lookup"><span data-stu-id="b20e6-122">optional</span></span>  <br/> ||<span data-ttu-id="b20e6-123">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b20e6-123">Values of the xsd:string type.</span></span>  <br/> |
   

