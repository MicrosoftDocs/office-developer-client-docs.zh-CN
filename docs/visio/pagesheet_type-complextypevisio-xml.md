---
title: 'PageSheet_Type XML (Visio complexType) '
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
# <a name="pagesheet_type-complextype-visio-xml"></a><span data-ttu-id="7e922-102">PageSheet_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="7e922-102">PageSheet_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="7e922-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="7e922-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7e922-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7e922-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="7e922-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7e922-105">**Schema file**</span></span> <br/> |<span data-ttu-id="7e922-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="7e922-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="7e922-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="7e922-107">**Extension base**</span></span> <br/> |<span data-ttu-id="7e922-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="7e922-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7e922-109">定义</span><span class="sxs-lookup"><span data-stu-id="7e922-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="7e922-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7e922-110">Elements and attributes</span></span>

<span data-ttu-id="7e922-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7e922-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="7e922-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7e922-112">Child elements</span></span>

<span data-ttu-id="7e922-113">无。</span><span class="sxs-lookup"><span data-stu-id="7e922-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="7e922-114">属性</span><span class="sxs-lookup"><span data-stu-id="7e922-114">Attributes</span></span>

|<span data-ttu-id="7e922-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="7e922-115">**Attribute**</span></span>|<span data-ttu-id="7e922-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="7e922-116">**Type**</span></span>|<span data-ttu-id="7e922-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="7e922-117">**Required**</span></span>|<span data-ttu-id="7e922-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="7e922-118">**Description**</span></span>|<span data-ttu-id="7e922-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="7e922-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e922-120">UniqueID</span><span class="sxs-lookup"><span data-stu-id="7e922-120">UniqueID</span></span>  <br/> |<span data-ttu-id="7e922-121">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7e922-121">xsd:string</span></span>  <br/> |<span data-ttu-id="7e922-122">可选</span><span class="sxs-lookup"><span data-stu-id="7e922-122">optional</span></span>  <br/> ||<span data-ttu-id="7e922-123">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="7e922-123">Values of the xsd:string type.</span></span>  <br/> |
   

