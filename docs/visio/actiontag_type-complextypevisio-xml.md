---
title: ActionTag_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1bcc17e7-d59d-d392-f299-78d7665202fc
ms.openlocfilehash: a30290ee9dbb86c7af75820bd767bb95ce4add21
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283056"
---
# <a name="actiontagtype-complextype-visio-xml"></a><span data-ttu-id="ca732-102">ActionTag_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="ca732-102">ActionTag_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="ca732-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ca732-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ca732-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ca732-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ca732-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ca732-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ca732-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="ca732-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ca732-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ca732-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ca732-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="ca732-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ca732-109">定义</span><span class="sxs-lookup"><span data-stu-id="ca732-109">Definition</span></span>

```XML
          <xs:complexType name="ActionTag_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="ActionTagRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ca732-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ca732-110">Elements and attributes</span></span>

<span data-ttu-id="ca732-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="ca732-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ca732-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ca732-112">Child elements</span></span>

|<span data-ttu-id="ca732-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="ca732-113">**Element**</span></span>|<span data-ttu-id="ca732-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="ca732-114">**Type**</span></span>|<span data-ttu-id="ca732-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ca732-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ca732-116">Row</span><span class="sxs-lookup"><span data-stu-id="ca732-116">Row</span></span>](row-element-action-tag-sectionvisio-xml.md) <br/> |[<span data-ttu-id="ca732-117">ActionTagRow_Type</span><span class="sxs-lookup"><span data-stu-id="ca732-117">ActionTagRow_Type</span></span>](actiontagrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="ca732-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="ca732-118">Attributes</span></span>

<span data-ttu-id="ca732-119">无。</span><span class="sxs-lookup"><span data-stu-id="ca732-119">None.</span></span>
  

