---
title: 属性标识符和类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 39a5c97c-5ac8-47a8-b193-a4b3ba6a02a5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: caba60b7059d1c1f8f0440aeb55abb88801fbc9a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437215"
---
# <a name="property-identifiers-and-types"></a><span data-ttu-id="5cb75-103">属性标识符和类型</span><span class="sxs-lookup"><span data-stu-id="5cb75-103">Property Identifiers and Types</span></span>

  
  
<span data-ttu-id="5cb75-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5cb75-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5cb75-105">所有 MAPI 属性都由属性标记表示。</span><span class="sxs-lookup"><span data-stu-id="5cb75-105">All MAPI properties are represented by property tags.</span></span> <span data-ttu-id="5cb75-106">属性标记是一个 32 位无符号整数值，包含高顺序 16 位中的属性标识符和低顺序 16 位的属性类型。</span><span class="sxs-lookup"><span data-stu-id="5cb75-106">A property tag is a 32-bit unsigned integer value that contains the property's identifier in the high order 16 bits and the property's type in the low order 16 bits.</span></span> <span data-ttu-id="5cb75-107">MAPI 定义的所有属性的属性标记都包含在 mapitags.h 头文件中。</span><span class="sxs-lookup"><span data-stu-id="5cb75-107">Property tags for all of the properties defined by MAPI are included in the mapitags.h header file.</span></span>
  
<span data-ttu-id="5cb75-108">属性标识符用于指示属性用于什么以及谁负责它。</span><span class="sxs-lookup"><span data-stu-id="5cb75-108">Property identifiers are used to indicate what a property is used for and who is responsible for it.</span></span> <span data-ttu-id="5cb75-109">属性标识符按 MAPI 划分到范围中;其中标识符属于范围，指示其使用和所有权。</span><span class="sxs-lookup"><span data-stu-id="5cb75-109">Property identifiers are divided by MAPI into ranges; where an identifier falls in the range indicates its use and ownership.</span></span> 
  
<span data-ttu-id="5cb75-110">属性类型用于指示属性数据的格式。</span><span class="sxs-lookup"><span data-stu-id="5cb75-110">Property types are used to indicate the format of the property's data.</span></span> <span data-ttu-id="5cb75-111">MAPI 定义所有有效类型。</span><span class="sxs-lookup"><span data-stu-id="5cb75-111">MAPI defines all of the valid types.</span></span> <span data-ttu-id="5cb75-112">创建新属性的客户端和服务提供商必须使用其中一种类型。</span><span class="sxs-lookup"><span data-stu-id="5cb75-112">Clients and service providers creating new properties must use one of these types.</span></span> <span data-ttu-id="5cb75-113">所有属性类型都包含在 mapidefs.h 头文件中。</span><span class="sxs-lookup"><span data-stu-id="5cb75-113">All of the property types are included in the mapidefs.h header file.</span></span>
  

