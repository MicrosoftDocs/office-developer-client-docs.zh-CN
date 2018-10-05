---
title: Issues_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f326e227-f68e-27d6-268e-1ae935516dbc
ms.openlocfilehash: 42482db0c4542398381bc02ec5b21a8b80fac62f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397231"
---
# <a name="issuestype-complextype-visio-xml"></a><span data-ttu-id="ff990-102">Issues_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ff990-102">Issues_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="ff990-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ff990-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ff990-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ff990-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ff990-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ff990-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ff990-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="ff990-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ff990-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ff990-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ff990-108">无</span><span class="sxs-lookup"><span data-stu-id="ff990-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ff990-109">定义</span><span class="sxs-lookup"><span data-stu-id="ff990-109">Definition</span></span>

```XML
          <xs:complexType name="Issues_Type">
          
          <xs:sequence>
    <xs:element name="Issue"  type="Issue_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ff990-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ff990-110">Elements and attributes</span></span>

<span data-ttu-id="ff990-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ff990-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ff990-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ff990-112">Child elements</span></span>

|<span data-ttu-id="ff990-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="ff990-113">**Element**</span></span>|<span data-ttu-id="ff990-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="ff990-114">**Type**</span></span>|<span data-ttu-id="ff990-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ff990-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ff990-116">问题</span><span class="sxs-lookup"><span data-stu-id="ff990-116">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ff990-117">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="ff990-117">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="ff990-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="ff990-118">Attributes</span></span>

<span data-ttu-id="ff990-119">无。</span><span class="sxs-lookup"><span data-stu-id="ff990-119">None.</span></span>
  

