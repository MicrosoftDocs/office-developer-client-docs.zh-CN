---
title: 'FaceNames_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 234bbe07-004e-0604-144c-376d7b06994b
ms.openlocfilehash: 70ca3c5717ef6f85899a9be2ab4299dcefbd8fa0
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542420"
---
# <a name="facenames_type-complextype-visio-xml"></a><span data-ttu-id="2e501-102">FaceNames_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="2e501-102">FaceNames_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="2e501-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2e501-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2e501-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2e501-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2e501-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2e501-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2e501-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="2e501-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2e501-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2e501-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2e501-108">无</span><span class="sxs-lookup"><span data-stu-id="2e501-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2e501-109">定义</span><span class="sxs-lookup"><span data-stu-id="2e501-109">Definition</span></span>

```XML
          <xs:complexType name="FaceNames_Type">
          
          <xs:sequence>
    <xs:element name="FaceName"  type="FaceName_Type"
     minOccurs="1"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2e501-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2e501-110">Elements and attributes</span></span>

<span data-ttu-id="2e501-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2e501-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2e501-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2e501-112">Child elements</span></span>

|<span data-ttu-id="2e501-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="2e501-113">**Element**</span></span>|<span data-ttu-id="2e501-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="2e501-114">**Type**</span></span>|<span data-ttu-id="2e501-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e501-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2e501-116">FaceName</span><span class="sxs-lookup"><span data-stu-id="2e501-116">FaceName</span></span>](facename-element-facenames_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2e501-117">FaceName_Type</span><span class="sxs-lookup"><span data-stu-id="2e501-117">FaceName_Type</span></span>](facename_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="2e501-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="2e501-118">Attributes</span></span>

<span data-ttu-id="2e501-119">无。</span><span class="sxs-lookup"><span data-stu-id="2e501-119">None.</span></span>
  

