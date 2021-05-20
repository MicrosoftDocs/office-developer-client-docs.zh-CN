---
title: 'Issues_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f326e227-f68e-27d6-268e-1ae935516dbc
ms.openlocfilehash: 160afddb1352a93050496a9b3497a3e3b6f2e585
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538107"
---
# <a name="issues_type-complextype-visio-xml"></a><span data-ttu-id="71a64-102">Issues_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="71a64-102">Issues_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="71a64-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="71a64-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="71a64-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="71a64-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="71a64-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="71a64-105">**Schema file**</span></span> <br/> |<span data-ttu-id="71a64-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="71a64-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="71a64-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="71a64-107">**Extension base**</span></span> <br/> |<span data-ttu-id="71a64-108">无</span><span class="sxs-lookup"><span data-stu-id="71a64-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="71a64-109">定义</span><span class="sxs-lookup"><span data-stu-id="71a64-109">Definition</span></span>

```XML
          <xs:complexType name="Issues_Type">
          
          <xs:sequence>
    <xs:element name="Issue"  type="Issue_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="71a64-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="71a64-110">Elements and attributes</span></span>

<span data-ttu-id="71a64-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="71a64-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="71a64-112">子元素</span><span class="sxs-lookup"><span data-stu-id="71a64-112">Child elements</span></span>

|<span data-ttu-id="71a64-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="71a64-113">**Element**</span></span>|<span data-ttu-id="71a64-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="71a64-114">**Type**</span></span>|<span data-ttu-id="71a64-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="71a64-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="71a64-116">问题</span><span class="sxs-lookup"><span data-stu-id="71a64-116">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="71a64-117">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="71a64-117">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="71a64-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="71a64-118">Attributes</span></span>

<span data-ttu-id="71a64-119">无。</span><span class="sxs-lookup"><span data-stu-id="71a64-119">None.</span></span>
  

