---
title: 属性标识符和类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 39a5c97c-5ac8-47a8-b193-a4b3ba6a02a5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 423992e0485e8e3092cfc4126164576906d51149
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567060"
---
# <a name="property-identifiers-and-types"></a><span data-ttu-id="d0e72-103">属性标识符和类型</span><span class="sxs-lookup"><span data-stu-id="d0e72-103">Property Identifiers and Types</span></span>

  
  
<span data-ttu-id="d0e72-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d0e72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d0e72-105">由属性标记表示所有 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="d0e72-105">All MAPI properties are represented by property tags.</span></span> <span data-ttu-id="d0e72-106">属性标记是一个 32 位无符号的整数值，包含该属性的标识符的高顺序 16 位和 low 中的该属性的类型排序 16 位。</span><span class="sxs-lookup"><span data-stu-id="d0e72-106">A property tag is a 32-bit unsigned integer value that contains the property's identifier in the high order 16 bits and the property's type in the low order 16 bits.</span></span> <span data-ttu-id="d0e72-107">Mapitags.h 标头文件中包含的所有属性定义的 MAPI 属性标记。</span><span class="sxs-lookup"><span data-stu-id="d0e72-107">Property tags for all of the properties defined by MAPI are included in the mapitags.h header file.</span></span>
  
<span data-ttu-id="d0e72-108">属性标识符用于指示属性用于以及由谁来负责它。</span><span class="sxs-lookup"><span data-stu-id="d0e72-108">Property identifiers are used to indicate what a property is used for and who is responsible for it.</span></span> <span data-ttu-id="d0e72-109">属性标识符可以分为若干通过 MAPI 范围;标识符属于范围中的其中指示其使用情况和所有权。</span><span class="sxs-lookup"><span data-stu-id="d0e72-109">Property identifiers are divided by MAPI into ranges; where an identifier falls in the range indicates its use and ownership.</span></span> 
  
<span data-ttu-id="d0e72-110">属性类型用于指示该属性的数据的格式。</span><span class="sxs-lookup"><span data-stu-id="d0e72-110">Property types are used to indicate the format of the property's data.</span></span> <span data-ttu-id="d0e72-111">MAPI 定义的所有有效的类型。</span><span class="sxs-lookup"><span data-stu-id="d0e72-111">MAPI defines all of the valid types.</span></span> <span data-ttu-id="d0e72-112">客户端和创建新属性的服务提供商必须使用这些类型之一。</span><span class="sxs-lookup"><span data-stu-id="d0e72-112">Clients and service providers creating new properties must use one of these types.</span></span> <span data-ttu-id="d0e72-113">Mapidefs.h 头文件中包含的所有属性类型。</span><span class="sxs-lookup"><span data-stu-id="d0e72-113">All of the property types are included in the mapidefs.h header file.</span></span>
  

