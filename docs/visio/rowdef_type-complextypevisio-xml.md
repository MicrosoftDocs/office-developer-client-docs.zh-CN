---
title: 'RowDef_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 64897258-dd7e-a730-d4f5-d9c217308491
ms.openlocfilehash: 79a01d9fe5edf1de933f05683eca3bfd6e95e4b3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538135"
---
# <a name="rowdef_type-complextype-visio-xml"></a><span data-ttu-id="83e18-102">RowDef_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="83e18-102">RowDef_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="83e18-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="83e18-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="83e18-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="83e18-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="83e18-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="83e18-105">**Schema file**</span></span> <br/> |<span data-ttu-id="83e18-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="83e18-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="83e18-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="83e18-107">**Extension base**</span></span> <br/> |<span data-ttu-id="83e18-108">无</span><span class="sxs-lookup"><span data-stu-id="83e18-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="83e18-109">定义</span><span class="sxs-lookup"><span data-stu-id="83e18-109">Definition</span></span>

```XML
          <xs:complexType name="RowDef_Type">
          
          <xs:sequence>
    <xs:element name="CellDef"  type="CellDef_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="83e18-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="83e18-110">Elements and attributes</span></span>

<span data-ttu-id="83e18-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="83e18-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="83e18-112">子元素</span><span class="sxs-lookup"><span data-stu-id="83e18-112">Child elements</span></span>

|<span data-ttu-id="83e18-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="83e18-113">**Element**</span></span>|<span data-ttu-id="83e18-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="83e18-114">**Type**</span></span>|<span data-ttu-id="83e18-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="83e18-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="83e18-116">CellDef</span><span class="sxs-lookup"><span data-stu-id="83e18-116">CellDef</span></span> <br/> |[<span data-ttu-id="83e18-117">CellDef_Type</span><span class="sxs-lookup"><span data-stu-id="83e18-117">CellDef_Type</span></span>](celldef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="83e18-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="83e18-118">Attributes</span></span>

<span data-ttu-id="83e18-119">无。</span><span class="sxs-lookup"><span data-stu-id="83e18-119">None.</span></span>
  

