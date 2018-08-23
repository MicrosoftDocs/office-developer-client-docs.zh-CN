---
title: MSCAP_SELECTOR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f28ac144-f5ac-fd83-2b72-8d6e5fd74b6e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8c23788d64fe3703c7c46998cade0bd40d2f3dd2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588123"
---
# <a name="mscapselector"></a><span data-ttu-id="b074f-103">MSCAP_SELECTOR</span><span class="sxs-lookup"><span data-stu-id="b074f-103">MSCAP_SELECTOR</span></span>

  
  
<span data-ttu-id="b074f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b074f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b074f-105">指定要返回的存储区的功能。</span><span class="sxs-lookup"><span data-stu-id="b074f-105">Specifies the capabilities to return for a store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b074f-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="b074f-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="b074f-107">Members</span><span class="sxs-lookup"><span data-stu-id="b074f-107">Members</span></span>

 <span data-ttu-id="b074f-108">*MSCAP_SEL_RESERVED1*</span><span class="sxs-lookup"><span data-stu-id="b074f-108">*MSCAP_SEL_RESERVED1*</span></span> 
  
> <span data-ttu-id="b074f-109">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="b074f-109">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="b074f-110">*MSCAP_SEL_RESERVED2*</span><span class="sxs-lookup"><span data-stu-id="b074f-110">*MSCAP_SEL_RESERVED2*</span></span> 
  
> <span data-ttu-id="b074f-111">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="b074f-111">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="b074f-112">*MSCAP_SEL_FOLDER*</span><span class="sxs-lookup"><span data-stu-id="b074f-112">*MSCAP_SEL_FOLDER*</span></span> 
  
> <span data-ttu-id="b074f-113">有关对存储支持文件夹的功能。</span><span class="sxs-lookup"><span data-stu-id="b074f-113">Capabilities about supporting folders on a store.</span></span>
    
 <span data-ttu-id="b074f-114">*MSCAP_SEL_RESERVED3*</span><span class="sxs-lookup"><span data-stu-id="b074f-114">*MSCAP_SEL_RESERVED3*</span></span> 
  
> <span data-ttu-id="b074f-115">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="b074f-115">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="b074f-116">*MSCAP_SEL_RESTRICTION*</span><span class="sxs-lookup"><span data-stu-id="b074f-116">*MSCAP_SEL_RESTRICTION*</span></span> 
  
> <span data-ttu-id="b074f-117">有关对存储支持限制的功能。</span><span class="sxs-lookup"><span data-stu-id="b074f-117">Capabilities about supporting restrictions on a store.</span></span>
    

