---
title: PublishSettings_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: cf14299e-8d21-0eed-bbd7-ad33d4f03533
ms.openlocfilehash: eaa4bba1c5772b11fdbd2ec1c975f475e1c5d57a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360010"
---
# <a name="publishsettingstype-complextype-visio-xml"></a><span data-ttu-id="3e9d9-102">PublishSettings_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="3e9d9-102">PublishSettings_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="3e9d9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="3e9d9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3e9d9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3e9d9-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="3e9d9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3e9d9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="3e9d9-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="3e9d9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="3e9d9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3e9d9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="3e9d9-108">无</span><span class="sxs-lookup"><span data-stu-id="3e9d9-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3e9d9-109">定义</span><span class="sxs-lookup"><span data-stu-id="3e9d9-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="3e9d9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3e9d9-110">Elements and attributes</span></span>

<span data-ttu-id="3e9d9-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="3e9d9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3e9d9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3e9d9-112">Child elements</span></span>

|<span data-ttu-id="3e9d9-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="3e9d9-113">**Element**</span></span>|<span data-ttu-id="3e9d9-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="3e9d9-114">**Type**</span></span>|<span data-ttu-id="3e9d9-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="3e9d9-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3e9d9-116">PublishedPage</span><span class="sxs-lookup"><span data-stu-id="3e9d9-116">PublishedPage</span></span>](publishedpage-element-publishsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3e9d9-117">PublishedPage_Type</span><span class="sxs-lookup"><span data-stu-id="3e9d9-117">PublishedPage_Type</span></span>](publishedpage_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="3e9d9-118">RefreshableData</span><span class="sxs-lookup"><span data-stu-id="3e9d9-118">RefreshableData</span></span>](refreshabledata-element-publishsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3e9d9-119">RefreshableData_Type</span><span class="sxs-lookup"><span data-stu-id="3e9d9-119">RefreshableData_Type</span></span>](refreshabledata_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="3e9d9-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="3e9d9-120">Attributes</span></span>

<span data-ttu-id="3e9d9-121">无。</span><span class="sxs-lookup"><span data-stu-id="3e9d9-121">None.</span></span>
  

