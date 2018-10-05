---
title: Connects_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 68a85d32-9bf2-2f7c-2797-85ddd593fc37
ms.openlocfilehash: ed5046656554fdd64251601c12e6817d586cd689
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399877"
---
# <a name="connectstype-complextype-visio-xml"></a><span data-ttu-id="1e229-102">Connects_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="1e229-102">Connects_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="1e229-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1e229-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1e229-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1e229-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1e229-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1e229-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1e229-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="1e229-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1e229-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1e229-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1e229-108">无</span><span class="sxs-lookup"><span data-stu-id="1e229-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1e229-109">定义</span><span class="sxs-lookup"><span data-stu-id="1e229-109">Definition</span></span>

```XML
          <xs:complexType name="Connects_Type">
          
          <xs:sequence>
    <xs:element name="Connect"  type="Connect_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1e229-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1e229-110">Elements and attributes</span></span>

<span data-ttu-id="1e229-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1e229-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1e229-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1e229-112">Child elements</span></span>

|<span data-ttu-id="1e229-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="1e229-113">**Element**</span></span>|<span data-ttu-id="1e229-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="1e229-114">**Type**</span></span>|<span data-ttu-id="1e229-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="1e229-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1e229-116">Connect</span><span class="sxs-lookup"><span data-stu-id="1e229-116">Connect</span></span>](connect-element-connects_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1e229-117">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="1e229-117">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="1e229-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="1e229-118">Attributes</span></span>

<span data-ttu-id="1e229-119">无。</span><span class="sxs-lookup"><span data-stu-id="1e229-119">None.</span></span>
  

