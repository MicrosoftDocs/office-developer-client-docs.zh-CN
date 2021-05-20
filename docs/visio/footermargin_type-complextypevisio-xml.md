---
title: 'FooterMargin_Type COMPLEXType (Visio XML) '
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
# <a name="footermargin_type-complextype-visio-xml"></a><span data-ttu-id="f52ad-102">FooterMargin_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="f52ad-102">FooterMargin_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="f52ad-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f52ad-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f52ad-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f52ad-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f52ad-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f52ad-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f52ad-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="f52ad-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f52ad-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f52ad-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f52ad-108">xsd：double</span><span class="sxs-lookup"><span data-stu-id="f52ad-108">xsd:double</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f52ad-109">定义</span><span class="sxs-lookup"><span data-stu-id="f52ad-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="f52ad-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f52ad-110">Elements and attributes</span></span>

<span data-ttu-id="f52ad-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f52ad-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f52ad-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f52ad-112">Child elements</span></span>

<span data-ttu-id="f52ad-113">无。</span><span class="sxs-lookup"><span data-stu-id="f52ad-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="f52ad-114">属性</span><span class="sxs-lookup"><span data-stu-id="f52ad-114">Attributes</span></span>

|<span data-ttu-id="f52ad-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="f52ad-115">**Attribute**</span></span>|<span data-ttu-id="f52ad-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="f52ad-116">**Type**</span></span>|<span data-ttu-id="f52ad-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="f52ad-117">**Required**</span></span>|<span data-ttu-id="f52ad-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="f52ad-118">**Description**</span></span>|<span data-ttu-id="f52ad-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f52ad-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f52ad-120">Unit</span><span class="sxs-lookup"><span data-stu-id="f52ad-120">Unit</span></span>  <br/> |<span data-ttu-id="f52ad-121">xsd：string</span><span class="sxs-lookup"><span data-stu-id="f52ad-121">xsd:string</span></span>  <br/> |<span data-ttu-id="f52ad-122">可选</span><span class="sxs-lookup"><span data-stu-id="f52ad-122">optional</span></span>  <br/> ||<span data-ttu-id="f52ad-123">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f52ad-123">Values of the xsd:string type.</span></span>  <br/> |
   

