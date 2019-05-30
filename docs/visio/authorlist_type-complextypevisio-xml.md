---
title: AuthorList_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fc1e059b-7705-8b30-aeab-f56707086416
ms.openlocfilehash: 5df48bcc69f0bd4aa818f265d0c7db1986165b3e
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537897"
---
# <a name="authorlisttype-complextype-visio-xml"></a><span data-ttu-id="5eb24-102">AuthorList_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5eb24-102">AuthorList_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="5eb24-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5eb24-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5eb24-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5eb24-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5eb24-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5eb24-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5eb24-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="5eb24-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5eb24-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5eb24-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5eb24-108">无</span><span class="sxs-lookup"><span data-stu-id="5eb24-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5eb24-109">定义</span><span class="sxs-lookup"><span data-stu-id="5eb24-109">Definition</span></span>

```XML
          <xs:complexType name="AuthorList_Type">
          
          <xs:sequence>
    <xs:element name="AuthorEntry"  type="AuthorEntry_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5eb24-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5eb24-110">Elements and attributes</span></span>

<span data-ttu-id="5eb24-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="5eb24-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5eb24-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5eb24-112">Child elements</span></span>

|<span data-ttu-id="5eb24-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="5eb24-113">**Element**</span></span>|<span data-ttu-id="5eb24-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="5eb24-114">**Type**</span></span>|<span data-ttu-id="5eb24-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="5eb24-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5eb24-116">AuthorEntry</span><span class="sxs-lookup"><span data-stu-id="5eb24-116">AuthorEntry</span></span>](authorentry-element-authorlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5eb24-117">AuthorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="5eb24-117">AuthorEntry_Type</span></span>](authorentry_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="5eb24-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="5eb24-118">Attributes</span></span>

<span data-ttu-id="5eb24-119">无。</span><span class="sxs-lookup"><span data-stu-id="5eb24-119">None.</span></span>
  

