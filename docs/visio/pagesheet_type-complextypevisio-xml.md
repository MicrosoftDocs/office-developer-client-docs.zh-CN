---
title: PageSheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f7bce473-9a3d-65f2-8323-1e00db110c71
ms.openlocfilehash: 01112db1465eece9ecf5faf200a1d866ce6e332d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540586"
---
# <a name="pagesheettype-complextype-visio-xml"></a><span data-ttu-id="05fef-102">PageSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="05fef-102">PageSheet_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="05fef-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="05fef-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="05fef-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="05fef-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="05fef-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="05fef-105">**Schema file**</span></span> <br/> |<span data-ttu-id="05fef-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="05fef-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="05fef-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="05fef-107">**Extension base**</span></span> <br/> |<span data-ttu-id="05fef-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="05fef-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="05fef-109">定义</span><span class="sxs-lookup"><span data-stu-id="05fef-109">Definition</span></span>

```XML
      <xs:complexType name="PageSheet_Type">
        <xs:complexContent>
        <xs:extension base="Sheet_Type">
      
    <xs:attribute name="UniqueID"
  type="xsd:string"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="05fef-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="05fef-110">Elements and attributes</span></span>

<span data-ttu-id="05fef-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="05fef-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="05fef-112">子元素</span><span class="sxs-lookup"><span data-stu-id="05fef-112">Child elements</span></span>

<span data-ttu-id="05fef-113">无。</span><span class="sxs-lookup"><span data-stu-id="05fef-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="05fef-114">属性</span><span class="sxs-lookup"><span data-stu-id="05fef-114">Attributes</span></span>

|<span data-ttu-id="05fef-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="05fef-115">**Attribute**</span></span>|<span data-ttu-id="05fef-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="05fef-116">**Type**</span></span>|<span data-ttu-id="05fef-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="05fef-117">**Required**</span></span>|<span data-ttu-id="05fef-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="05fef-118">**Description**</span></span>|<span data-ttu-id="05fef-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="05fef-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05fef-120">UniqueID</span><span class="sxs-lookup"><span data-stu-id="05fef-120">UniqueID</span></span>  <br/> |<span data-ttu-id="05fef-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="05fef-121">xsd:string</span></span>  <br/> |<span data-ttu-id="05fef-122">可选</span><span class="sxs-lookup"><span data-stu-id="05fef-122">optional</span></span>  <br/> ||<span data-ttu-id="05fef-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="05fef-123">Values of the xsd:string type.</span></span>  <br/> |
   

