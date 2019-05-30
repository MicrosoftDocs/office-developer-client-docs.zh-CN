---
title: RowKeyValue_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e4c971f4-e3e3-11be-6b3f-45565e56cb23
ms.openlocfilehash: e629a3a38927b7497d8d4f50299dc6be1b51c37b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541720"
---
# <a name="rowkeyvaluetype-complextype-visio-xml"></a><span data-ttu-id="cb978-102">RowKeyValue_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="cb978-102">RowKeyValue_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="cb978-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="cb978-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="cb978-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="cb978-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="cb978-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="cb978-105">**Schema file**</span></span> <br/> |<span data-ttu-id="cb978-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="cb978-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="cb978-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="cb978-107">**Extension base**</span></span> <br/> |<span data-ttu-id="cb978-108">无</span><span class="sxs-lookup"><span data-stu-id="cb978-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="cb978-109">定义</span><span class="sxs-lookup"><span data-stu-id="cb978-109">Definition</span></span>

```XML
      <xs:complexType name="RowKeyValue_Type">
    <xs:attribute name="RowID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="Value"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="cb978-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="cb978-110">Elements and attributes</span></span>

<span data-ttu-id="cb978-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="cb978-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="cb978-112">子元素</span><span class="sxs-lookup"><span data-stu-id="cb978-112">Child elements</span></span>

<span data-ttu-id="cb978-113">无。</span><span class="sxs-lookup"><span data-stu-id="cb978-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="cb978-114">属性</span><span class="sxs-lookup"><span data-stu-id="cb978-114">Attributes</span></span>

|<span data-ttu-id="cb978-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="cb978-115">**Attribute**</span></span>|<span data-ttu-id="cb978-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="cb978-116">**Type**</span></span>|<span data-ttu-id="cb978-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="cb978-117">**Required**</span></span>|<span data-ttu-id="cb978-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="cb978-118">**Description**</span></span>|<span data-ttu-id="cb978-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="cb978-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb978-120">RowID</span><span class="sxs-lookup"><span data-stu-id="cb978-120">RowID</span></span>  <br/> |<span data-ttu-id="cb978-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="cb978-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="cb978-122">必需</span><span class="sxs-lookup"><span data-stu-id="cb978-122">required</span></span>  <br/> ||<span data-ttu-id="cb978-123">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cb978-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="cb978-124">值</span><span class="sxs-lookup"><span data-stu-id="cb978-124">Value</span></span>  <br/> |<span data-ttu-id="cb978-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cb978-125">xsd:string</span></span>  <br/> |<span data-ttu-id="cb978-126">必需</span><span class="sxs-lookup"><span data-stu-id="cb978-126">required</span></span>  <br/> ||<span data-ttu-id="cb978-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cb978-127">Values of the xsd:string type.</span></span>  <br/> |
   

