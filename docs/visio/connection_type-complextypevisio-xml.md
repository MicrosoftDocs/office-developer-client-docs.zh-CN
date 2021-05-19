---
title: 'Connection_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5c0ac13b-70cc-398b-a1a3-e7d8080c8f7b
ms.openlocfilehash: c079a7b1b12dec66d589adc1c6eb869cef0a1ed0
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542504"
---
# <a name="connection_type-complextype-visio-xml"></a><span data-ttu-id="bde83-102">Connection_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="bde83-102">Connection_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="bde83-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="bde83-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bde83-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="bde83-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="bde83-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="bde83-105">**Schema file**</span></span> <br/> |<span data-ttu-id="bde83-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="bde83-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="bde83-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="bde83-107">**Extension base**</span></span> <br/> |<span data-ttu-id="bde83-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="bde83-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="bde83-109">定义</span><span class="sxs-lookup"><span data-stu-id="bde83-109">Definition</span></span>

```XML
          <xs:complexType name="Connection_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="ConnectionRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="bde83-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="bde83-110">Elements and attributes</span></span>

<span data-ttu-id="bde83-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="bde83-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="bde83-112">子元素</span><span class="sxs-lookup"><span data-stu-id="bde83-112">Child elements</span></span>

|<span data-ttu-id="bde83-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="bde83-113">**Element**</span></span>|<span data-ttu-id="bde83-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="bde83-114">**Type**</span></span>|<span data-ttu-id="bde83-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="bde83-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bde83-116">Row</span><span class="sxs-lookup"><span data-stu-id="bde83-116">Row</span></span>](row-element-connection-sectionvisio-xml.md) <br/> |[<span data-ttu-id="bde83-117">ConnectionRow_Type</span><span class="sxs-lookup"><span data-stu-id="bde83-117">ConnectionRow_Type</span></span>](connectionrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="bde83-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="bde83-118">Attributes</span></span>

<span data-ttu-id="bde83-119">无。</span><span class="sxs-lookup"><span data-stu-id="bde83-119">None.</span></span>
  

