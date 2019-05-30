---
title: StyleSheets_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2603bc5-86bd-df29-43c2-25a39419ad1e
ms.openlocfilehash: 845580f2842c098cfb16776b9ab1d5d513ef8e22
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538884"
---
# <a name="stylesheetstype-complextype-visio-xml"></a><span data-ttu-id="1a95b-102">StyleSheets_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="1a95b-102">StyleSheets_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="1a95b-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1a95b-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1a95b-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1a95b-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1a95b-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1a95b-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1a95b-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="1a95b-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1a95b-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1a95b-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1a95b-108">无</span><span class="sxs-lookup"><span data-stu-id="1a95b-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1a95b-109">定义</span><span class="sxs-lookup"><span data-stu-id="1a95b-109">Definition</span></span>

```XML
          <xs:complexType name="StyleSheets_Type">
          
          <xs:sequence>
    <xs:element name="StyleSheet"  type="StyleSheet_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1a95b-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1a95b-110">Elements and attributes</span></span>

<span data-ttu-id="1a95b-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="1a95b-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1a95b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1a95b-112">Child elements</span></span>

|<span data-ttu-id="1a95b-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="1a95b-113">**Element**</span></span>|<span data-ttu-id="1a95b-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="1a95b-114">**Type**</span></span>|<span data-ttu-id="1a95b-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="1a95b-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1a95b-116">单</span><span class="sxs-lookup"><span data-stu-id="1a95b-116">StyleSheet</span></span>](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1a95b-117">StyleSheet_Type</span><span class="sxs-lookup"><span data-stu-id="1a95b-117">StyleSheet_Type</span></span>](stylesheet_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="1a95b-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="1a95b-118">Attributes</span></span>

<span data-ttu-id="1a95b-119">无。</span><span class="sxs-lookup"><span data-stu-id="1a95b-119">None.</span></span>
  

