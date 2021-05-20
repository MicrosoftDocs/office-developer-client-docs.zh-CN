---
title: 'Solutions_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 74978183-8513-b359-0501-6094e072ac8e
ms.openlocfilehash: b68955d2ed161d1ec0952b4a1b9d657fe0de81fc
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540229"
---
# <a name="solutions_type-complextype-visio-xml"></a><span data-ttu-id="119a2-102">Solutions_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="119a2-102">Solutions_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="119a2-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="119a2-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="119a2-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="119a2-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="119a2-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="119a2-105">**Schema file**</span></span> <br/> |<span data-ttu-id="119a2-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="119a2-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="119a2-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="119a2-107">**Extension base**</span></span> <br/> |<span data-ttu-id="119a2-108">无</span><span class="sxs-lookup"><span data-stu-id="119a2-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="119a2-109">定义</span><span class="sxs-lookup"><span data-stu-id="119a2-109">Definition</span></span>

```XML
          <xs:complexType name="Solutions_Type">
          
          <xs:sequence>
    <xs:element name="Solution"  type="Solution_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="119a2-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="119a2-110">Elements and attributes</span></span>

<span data-ttu-id="119a2-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="119a2-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="119a2-112">子元素</span><span class="sxs-lookup"><span data-stu-id="119a2-112">Child elements</span></span>

|<span data-ttu-id="119a2-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="119a2-113">**Element**</span></span>|<span data-ttu-id="119a2-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="119a2-114">**Type**</span></span>|<span data-ttu-id="119a2-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="119a2-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="119a2-116">Solution</span><span class="sxs-lookup"><span data-stu-id="119a2-116">Solution</span></span>](solution-element-solutions_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="119a2-117">Solution_Type</span><span class="sxs-lookup"><span data-stu-id="119a2-117">Solution_Type</span></span>](solution_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="119a2-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="119a2-118">Attributes</span></span>

<span data-ttu-id="119a2-119">无。</span><span class="sxs-lookup"><span data-stu-id="119a2-119">None.</span></span>
  

