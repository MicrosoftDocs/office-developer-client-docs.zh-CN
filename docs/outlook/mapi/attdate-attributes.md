---
title: attDate Attributes
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22801641-752c-4c81-be90-02039eaa4277
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ff0cc6b1c17b2ed83d7b0ec0921904763da8624b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567011"
---
# <a name="attdate-attributes"></a><span data-ttu-id="6778d-103">attDate Attributes</span><span class="sxs-lookup"><span data-stu-id="6778d-103">attDate Attributes</span></span>

  
  
<span data-ttu-id="6778d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6778d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6778d-105">所有与日期和时间的 MAPI 属性映射到具有**attDate**前缀的 TNEF 属性。</span><span class="sxs-lookup"><span data-stu-id="6778d-105">All MAPI properties relating to dates and times are mapped to TNEF attributes that have the **attDate** prefix.</span></span> <span data-ttu-id="6778d-106">这些是所有编码为**DTR**结构。</span><span class="sxs-lookup"><span data-stu-id="6778d-106">These are all encoded as **DTR** structures.</span></span> <span data-ttu-id="6778d-107">日期和时间附件属性被编码为以及**DTR**结构。</span><span class="sxs-lookup"><span data-stu-id="6778d-107">The dates and times for attachment attributes are encoded as **DTR** structures as well.</span></span> 
  
<span data-ttu-id="6778d-108">所有与日期和时间的 MAPI 属性映射到具有**attDate**前缀的 TNEF 属性。</span><span class="sxs-lookup"><span data-stu-id="6778d-108">All MAPI properties relating to dates and times are mapped to TNEF attributes that have the **attDate** prefix.</span></span> <span data-ttu-id="6778d-109">这些是所有编码为**DTR**结构。</span><span class="sxs-lookup"><span data-stu-id="6778d-109">These are all encoded as **DTR** structures.</span></span> <span data-ttu-id="6778d-110">日期和时间附件属性被编码为以及**DTR**结构。</span><span class="sxs-lookup"><span data-stu-id="6778d-110">The dates and times for attachment attributes are encoded as **DTR** structures as well.</span></span> 
  
<span data-ttu-id="6778d-111">**DTR**结构是非常类似于在 Win32 头文件中定义的**SYSTEMTIME**结构。</span><span class="sxs-lookup"><span data-stu-id="6778d-111">A **DTR** structure is very similar to the **SYSTEMTIME** structure defined in the Win32 header files.</span></span> <span data-ttu-id="6778d-112">**DTR**结构 TNEF 用于将 stream 中编码为**sizeof(DTR)** 字节开头结构中的第一个成员。</span><span class="sxs-lookup"><span data-stu-id="6778d-112">The **DTR** structure is encoded in the TNEF stream as **sizeof(DTR)** bytes starting with the first member of the structure.</span></span> <span data-ttu-id="6778d-113">**DTR**结构 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="6778d-113">The **DTR** structure is defined in the TNEF.H header file.</span></span> 
  

