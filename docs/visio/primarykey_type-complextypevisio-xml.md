---
title: PrimaryKey_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3396f11b-f06e-03d9-fc9d-a23e9cfccabd
ms.openlocfilehash: 2d13ac2b6d55fdda752f16af28a0843d5a388f20
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780977"
---
# <a name="primarykeytype-complextype-visio-xml"></a><span data-ttu-id="f28e0-102">PrimaryKey_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f28e0-102">PrimaryKey_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="f28e0-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f28e0-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f28e0-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f28e0-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f28e0-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f28e0-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f28e0-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="f28e0-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f28e0-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f28e0-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f28e0-108">无</span><span class="sxs-lookup"><span data-stu-id="f28e0-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f28e0-109">定义</span><span class="sxs-lookup"><span data-stu-id="f28e0-109">Definition</span></span>

```XML
          <xs:complexType name="PrimaryKey_Type">
          
          <xs:sequence>
    <xs:element name="RowKeyValue"  type="RowKeyValue_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ColumnNameID"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f28e0-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f28e0-110">Elements and attributes</span></span>

<span data-ttu-id="f28e0-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f28e0-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f28e0-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f28e0-112">Child elements</span></span>

|<span data-ttu-id="f28e0-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f28e0-113">**Element**</span></span>|<span data-ttu-id="f28e0-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="f28e0-114">**Type**</span></span>|<span data-ttu-id="f28e0-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f28e0-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f28e0-116">RowKeyValue</span><span class="sxs-lookup"><span data-stu-id="f28e0-116">RowKeyValue</span></span>](rowkeyvalue-element-primarykey_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f28e0-117">RowKeyValue_Type</span><span class="sxs-lookup"><span data-stu-id="f28e0-117">RowKeyValue_Type</span></span>](rowkeyvalue_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="f28e0-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="f28e0-118">Attributes</span></span>

|<span data-ttu-id="f28e0-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="f28e0-119">**Attribute**</span></span>|<span data-ttu-id="f28e0-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="f28e0-120">**Type**</span></span>|<span data-ttu-id="f28e0-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="f28e0-121">**Required**</span></span>|<span data-ttu-id="f28e0-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="f28e0-122">**Description**</span></span>|<span data-ttu-id="f28e0-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f28e0-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f28e0-124">ColumnNameID</span><span class="sxs-lookup"><span data-stu-id="f28e0-124">ColumnNameID</span></span>  <br/> |<span data-ttu-id="f28e0-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f28e0-125">xsd:string</span></span>  <br/> |<span data-ttu-id="f28e0-126">必需</span><span class="sxs-lookup"><span data-stu-id="f28e0-126">required</span></span>  <br/> ||<span data-ttu-id="f28e0-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f28e0-127">Values of the xsd:string type.</span></span>  <br/> |
   

