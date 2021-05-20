---
title: 'Connects_Type复杂类型 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 68a85d32-9bf2-2f7c-2797-85ddd593fc37
ms.openlocfilehash: d9a3283e9ac16af8997d7e9d632e067ecec7423d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538695"
---
# <a name="connects_type-complextype-visio-xml"></a><span data-ttu-id="0b5f4-102">Connects_Type复杂类型 (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="0b5f4-102">Connects_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="0b5f4-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="0b5f4-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0b5f4-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0b5f4-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="0b5f4-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0b5f4-105">**Schema file**</span></span> <br/> |<span data-ttu-id="0b5f4-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="0b5f4-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="0b5f4-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="0b5f4-107">**Extension base**</span></span> <br/> |<span data-ttu-id="0b5f4-108">无</span><span class="sxs-lookup"><span data-stu-id="0b5f4-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0b5f4-109">定义</span><span class="sxs-lookup"><span data-stu-id="0b5f4-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="0b5f4-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0b5f4-110">Elements and attributes</span></span>

<span data-ttu-id="0b5f4-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0b5f4-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="0b5f4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0b5f4-112">Child elements</span></span>

|<span data-ttu-id="0b5f4-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="0b5f4-113">**Element**</span></span>|<span data-ttu-id="0b5f4-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="0b5f4-114">**Type**</span></span>|<span data-ttu-id="0b5f4-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="0b5f4-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0b5f4-116">Connect</span><span class="sxs-lookup"><span data-stu-id="0b5f4-116">Connect</span></span>](connect-element-connects_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0b5f4-117">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="0b5f4-117">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="0b5f4-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="0b5f4-118">Attributes</span></span>

<span data-ttu-id="0b5f4-119">无。</span><span class="sxs-lookup"><span data-stu-id="0b5f4-119">None.</span></span>
  

