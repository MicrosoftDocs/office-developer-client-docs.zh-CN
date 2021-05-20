---
title: 'Masters_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: beb489ab-d43c-51ad-d089-69c87d658a59
ms.openlocfilehash: 8f1c660899e9109d946d41426b09e03d73ee76dd
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538079"
---
# <a name="masters_type-complextype-visio-xml"></a><span data-ttu-id="c6991-102">Masters_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="c6991-102">Masters_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="c6991-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="c6991-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c6991-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c6991-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="c6991-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c6991-105">**Schema file**</span></span> <br/> |<span data-ttu-id="c6991-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="c6991-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="c6991-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="c6991-107">**Extension base**</span></span> <br/> |<span data-ttu-id="c6991-108">无</span><span class="sxs-lookup"><span data-stu-id="c6991-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c6991-109">定义</span><span class="sxs-lookup"><span data-stu-id="c6991-109">Definition</span></span>

```XML
          <xs:complexType name="Masters_Type">
          
          <xs:sequence>
    <xs:element name="Master"  type="Master_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="MasterShortcut"  type="MasterShortcut_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c6991-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c6991-110">Elements and attributes</span></span>

<span data-ttu-id="c6991-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c6991-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="c6991-112">子元素</span><span class="sxs-lookup"><span data-stu-id="c6991-112">Child elements</span></span>

|<span data-ttu-id="c6991-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="c6991-113">**Element**</span></span>|<span data-ttu-id="c6991-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="c6991-114">**Type**</span></span>|<span data-ttu-id="c6991-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="c6991-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c6991-116">Master</span><span class="sxs-lookup"><span data-stu-id="c6991-116">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c6991-117">Master_Type</span><span class="sxs-lookup"><span data-stu-id="c6991-117">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="c6991-118">MasterShortcut</span><span class="sxs-lookup"><span data-stu-id="c6991-118">MasterShortcut</span></span>](mastershortcut-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c6991-119">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="c6991-119">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="c6991-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="c6991-120">Attributes</span></span>

<span data-ttu-id="c6991-121">无。</span><span class="sxs-lookup"><span data-stu-id="c6991-121">None.</span></span>
  

