---
title: PublishSettings_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: cf14299e-8d21-0eed-bbd7-ad33d4f03533
ms.openlocfilehash: 6e9974d35b904581d43f481a02b8a3adee811730
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780999"
---
# <a name="publishsettingstype-complextype-visio-xml"></a><span data-ttu-id="99db2-102">PublishSettings_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="99db2-102">PublishSettings_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="99db2-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="99db2-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="99db2-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="99db2-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="99db2-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="99db2-105">**Schema file**</span></span> <br/> |<span data-ttu-id="99db2-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="99db2-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="99db2-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="99db2-107">**Extension base**</span></span> <br/> |<span data-ttu-id="99db2-108">无</span><span class="sxs-lookup"><span data-stu-id="99db2-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="99db2-109">定义</span><span class="sxs-lookup"><span data-stu-id="99db2-109">Definition</span></span>

```XML
          <xs:complexType name="PublishSettings_Type">
          
          <xs:sequence>
    <xs:element name="PublishedPage"  type="PublishedPage_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="RefreshableData"  type="RefreshableData_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="99db2-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="99db2-110">Elements and attributes</span></span>

<span data-ttu-id="99db2-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="99db2-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="99db2-112">子元素</span><span class="sxs-lookup"><span data-stu-id="99db2-112">Child elements</span></span>

|<span data-ttu-id="99db2-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="99db2-113">**Element**</span></span>|<span data-ttu-id="99db2-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="99db2-114">**Type**</span></span>|<span data-ttu-id="99db2-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="99db2-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="99db2-116">PublishedPage</span><span class="sxs-lookup"><span data-stu-id="99db2-116">PublishedPage</span></span>](publishedpage-element-publishsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="99db2-117">PublishedPage_Type</span><span class="sxs-lookup"><span data-stu-id="99db2-117">PublishedPage_Type</span></span>](publishedpage_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="99db2-118">RefreshableData</span><span class="sxs-lookup"><span data-stu-id="99db2-118">RefreshableData</span></span>](refreshabledata-element-publishsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="99db2-119">RefreshableData_Type</span><span class="sxs-lookup"><span data-stu-id="99db2-119">RefreshableData_Type</span></span>](refreshabledata_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="99db2-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="99db2-120">Attributes</span></span>

<span data-ttu-id="99db2-121">无。</span><span class="sxs-lookup"><span data-stu-id="99db2-121">None.</span></span>
  

