---
title: attDate 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22801641-752c-4c81-be90-02039eaa4277
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b7c1ce8d0338a2bda63a276628bdd6e8be3b8eb1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318065"
---
# <a name="attdate-attributes"></a><span data-ttu-id="bd17d-103">attDate 属性</span><span class="sxs-lookup"><span data-stu-id="bd17d-103">attDate Attributes</span></span>

  
  
<span data-ttu-id="bd17d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bd17d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bd17d-105">与日期和时间相关的所有 MAPI 属性都映射到具有**attDate**前缀的 TNEF 属性。</span><span class="sxs-lookup"><span data-stu-id="bd17d-105">All MAPI properties relating to dates and times are mapped to TNEF attributes that have the **attDate** prefix.</span></span> <span data-ttu-id="bd17d-106">它们都编码为**DTR**结构。</span><span class="sxs-lookup"><span data-stu-id="bd17d-106">These are all encoded as **DTR** structures.</span></span> <span data-ttu-id="bd17d-107">附件属性的日期和时间也被编码为**DTR**结构。</span><span class="sxs-lookup"><span data-stu-id="bd17d-107">The dates and times for attachment attributes are encoded as **DTR** structures as well.</span></span> 
  
<span data-ttu-id="bd17d-108">与日期和时间相关的所有 MAPI 属性都映射到具有**attDate**前缀的 TNEF 属性。</span><span class="sxs-lookup"><span data-stu-id="bd17d-108">All MAPI properties relating to dates and times are mapped to TNEF attributes that have the **attDate** prefix.</span></span> <span data-ttu-id="bd17d-109">它们都编码为**DTR**结构。</span><span class="sxs-lookup"><span data-stu-id="bd17d-109">These are all encoded as **DTR** structures.</span></span> <span data-ttu-id="bd17d-110">附件属性的日期和时间也被编码为**DTR**结构。</span><span class="sxs-lookup"><span data-stu-id="bd17d-110">The dates and times for attachment attributes are encoded as **DTR** structures as well.</span></span> 
  
<span data-ttu-id="bd17d-111">**DTR**结构非常类似于在 Win32 头文件中定义的**SYSTEMTIME**结构。</span><span class="sxs-lookup"><span data-stu-id="bd17d-111">A **DTR** structure is very similar to the **SYSTEMTIME** structure defined in the Win32 header files.</span></span> <span data-ttu-id="bd17d-112">**DTR**结构在 TNEF 流中编码为**sizeof (DTR)** 字节, 从结构的第一个成员开始。</span><span class="sxs-lookup"><span data-stu-id="bd17d-112">The **DTR** structure is encoded in the TNEF stream as **sizeof(DTR)** bytes starting with the first member of the structure.</span></span> <span data-ttu-id="bd17d-113">**DTR**结构是在 TNEF 中定义的。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="bd17d-113">The **DTR** structure is defined in the TNEF.H header file.</span></span> 
  

