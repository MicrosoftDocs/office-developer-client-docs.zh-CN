---
title: 'StyleSheets_Type COMPLEXType (Visio XML) '
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
# <a name="stylesheets_type-complextype-visio-xml"></a><span data-ttu-id="516fb-102">StyleSheets_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="516fb-102">StyleSheets_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="516fb-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="516fb-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="516fb-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="516fb-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="516fb-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="516fb-105">**Schema file**</span></span> <br/> |<span data-ttu-id="516fb-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="516fb-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="516fb-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="516fb-107">**Extension base**</span></span> <br/> |<span data-ttu-id="516fb-108">无</span><span class="sxs-lookup"><span data-stu-id="516fb-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="516fb-109">定义</span><span class="sxs-lookup"><span data-stu-id="516fb-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="516fb-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="516fb-110">Elements and attributes</span></span>

<span data-ttu-id="516fb-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="516fb-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="516fb-112">子元素</span><span class="sxs-lookup"><span data-stu-id="516fb-112">Child elements</span></span>

|<span data-ttu-id="516fb-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="516fb-113">**Element**</span></span>|<span data-ttu-id="516fb-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="516fb-114">**Type**</span></span>|<span data-ttu-id="516fb-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="516fb-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="516fb-116">StyleSheet</span><span class="sxs-lookup"><span data-stu-id="516fb-116">StyleSheet</span></span>](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="516fb-117">StyleSheet_Type</span><span class="sxs-lookup"><span data-stu-id="516fb-117">StyleSheet_Type</span></span>](stylesheet_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="516fb-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="516fb-118">Attributes</span></span>

<span data-ttu-id="516fb-119">无。</span><span class="sxs-lookup"><span data-stu-id="516fb-119">None.</span></span>
  

