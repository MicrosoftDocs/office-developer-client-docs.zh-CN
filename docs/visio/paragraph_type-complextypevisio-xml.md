---
title: 'Paragraph_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 23409c92-5e66-1e11-54a0-677d18e4e03a
ms.openlocfilehash: fd7c5233b89bc92ed449d3d8d2767daa23ea8071
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540593"
---
# <a name="paragraph_type-complextype-visio-xml"></a><span data-ttu-id="2e804-102">Paragraph_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="2e804-102">Paragraph_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="2e804-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2e804-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2e804-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2e804-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2e804-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2e804-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2e804-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="2e804-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2e804-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2e804-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2e804-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="2e804-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2e804-109">定义</span><span class="sxs-lookup"><span data-stu-id="2e804-109">Definition</span></span>

```XML
          <xs:complexType name="Paragraph_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="ParagraphRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2e804-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2e804-110">Elements and attributes</span></span>

<span data-ttu-id="2e804-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2e804-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2e804-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2e804-112">Child elements</span></span>

|<span data-ttu-id="2e804-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="2e804-113">**Element**</span></span>|<span data-ttu-id="2e804-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="2e804-114">**Type**</span></span>|<span data-ttu-id="2e804-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e804-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2e804-116">Row</span><span class="sxs-lookup"><span data-stu-id="2e804-116">Row</span></span>](row-element-paragraph-sectionvisio-xml.md) <br/> |[<span data-ttu-id="2e804-117">ParagraphRow_Type</span><span class="sxs-lookup"><span data-stu-id="2e804-117">ParagraphRow_Type</span></span>](paragraphrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="2e804-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="2e804-118">Attributes</span></span>

<span data-ttu-id="2e804-119">无。</span><span class="sxs-lookup"><span data-stu-id="2e804-119">None.</span></span>
  

