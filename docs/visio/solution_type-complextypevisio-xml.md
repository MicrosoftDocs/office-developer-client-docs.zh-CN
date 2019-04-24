---
title: Solution_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e41f5028-7173-986e-d381-5c02d05e4407
ms.openlocfilehash: a0cebb9b2d6d1f37b6104f0f7dca3c4624857288
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334361"
---
# <a name="solutiontype-complextype-visio-xml"></a><span data-ttu-id="da35a-102">Solution_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="da35a-102">Solution_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="da35a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="da35a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="da35a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="da35a-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="da35a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="da35a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="da35a-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="da35a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="da35a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="da35a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="da35a-108">无</span><span class="sxs-lookup"><span data-stu-id="da35a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="da35a-109">定义</span><span class="sxs-lookup"><span data-stu-id="da35a-109">Definition</span></span>

```XML
          <xs:complexType name="Solution_Type">
          
          <xs:sequence>
    <xs:element name="Rel"  type="Rel_Type"
     minOccurs="1"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="da35a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="da35a-110">Elements and attributes</span></span>

<span data-ttu-id="da35a-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="da35a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="da35a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="da35a-112">Child elements</span></span>

|<span data-ttu-id="da35a-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="da35a-113">**Element**</span></span>|<span data-ttu-id="da35a-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="da35a-114">**Type**</span></span>|<span data-ttu-id="da35a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="da35a-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="da35a-116">相对</span><span class="sxs-lookup"><span data-stu-id="da35a-116">Rel</span></span>](rel-element-solution_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="da35a-117">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="da35a-117">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="da35a-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="da35a-118">Attributes</span></span>

<span data-ttu-id="da35a-119">无。</span><span class="sxs-lookup"><span data-stu-id="da35a-119">None.</span></span>
  

