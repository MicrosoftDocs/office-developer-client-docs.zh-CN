---
title: MSCAP_SELECTOR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f28ac144-f5ac-fd83-2b72-8d6e5fd74b6e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9c5d8ab5bbac91250f3b8c552ad891c62134526e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338673"
---
# <a name="mscapselector"></a><span data-ttu-id="d251c-103">MSCAP_SELECTOR</span><span class="sxs-lookup"><span data-stu-id="d251c-103">MSCAP_SELECTOR</span></span>

  
  
<span data-ttu-id="d251c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d251c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d251c-105">指定要为存储区返回的功能。</span><span class="sxs-lookup"><span data-stu-id="d251c-105">Specifies the capabilities to return for a store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d251c-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="d251c-106">Quick info</span></span>

```cpp
typedef enum 
{ 
    MSCAP_SEL_RESERVED1 = 0, 
    MSCAP_SEL_RESERVED2, 
    MSCAP_SEL_FOLDER, 
    MSCAP_SEL_RESERVED3, 
    MSCAP_SEL_RESTRICTION, 
} MSCAP_SELECTOR;
```

## <a name="members"></a><span data-ttu-id="d251c-107">成员</span><span class="sxs-lookup"><span data-stu-id="d251c-107">Members</span></span>

 <span data-ttu-id="d251c-108">*MSCAP_SEL_RESERVED1*</span><span class="sxs-lookup"><span data-stu-id="d251c-108">*MSCAP_SEL_RESERVED1*</span></span> 
  
> <span data-ttu-id="d251c-109">此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="d251c-109">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="d251c-110">*MSCAP_SEL_RESERVED2*</span><span class="sxs-lookup"><span data-stu-id="d251c-110">*MSCAP_SEL_RESERVED2*</span></span> 
  
> <span data-ttu-id="d251c-111">此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="d251c-111">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="d251c-112">*MSCAP_SEL_FOLDER*</span><span class="sxs-lookup"><span data-stu-id="d251c-112">*MSCAP_SEL_FOLDER*</span></span> 
  
> <span data-ttu-id="d251c-113">有关在 store 上支持文件夹的功能。</span><span class="sxs-lookup"><span data-stu-id="d251c-113">Capabilities about supporting folders on a store.</span></span>
    
 <span data-ttu-id="d251c-114">*MSCAP_SEL_RESERVED3*</span><span class="sxs-lookup"><span data-stu-id="d251c-114">*MSCAP_SEL_RESERVED3*</span></span> 
  
> <span data-ttu-id="d251c-115">此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="d251c-115">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="d251c-116">*MSCAP_SEL_RESTRICTION*</span><span class="sxs-lookup"><span data-stu-id="d251c-116">*MSCAP_SEL_RESTRICTION*</span></span> 
  
> <span data-ttu-id="d251c-117">有关对存储区的支持限制的功能。</span><span class="sxs-lookup"><span data-stu-id="d251c-117">Capabilities about supporting restrictions on a store.</span></span>
    

