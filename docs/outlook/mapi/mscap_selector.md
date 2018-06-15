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
ms.openlocfilehash: 420b2661e766ecf97a5e9e488e9c18f29cd91329
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19776514"
---
# <a name="mscapselector"></a><span data-ttu-id="8209b-103">MSCAP_SELECTOR</span><span class="sxs-lookup"><span data-stu-id="8209b-103">MSCAP_SELECTOR</span></span>

  
  
<span data-ttu-id="8209b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8209b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8209b-105">指定要返回的存储区的功能。</span><span class="sxs-lookup"><span data-stu-id="8209b-105">Specifies the capabilities to return for a store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="8209b-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="8209b-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="8209b-107">成员</span><span class="sxs-lookup"><span data-stu-id="8209b-107">Members</span></span>

 <span data-ttu-id="8209b-108">*MSCAP_SEL_RESERVED1*</span><span class="sxs-lookup"><span data-stu-id="8209b-108">*MSCAP_SEL_RESERVED1*</span></span> 
  
> <span data-ttu-id="8209b-109">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="8209b-109">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="8209b-110">*MSCAP_SEL_RESERVED2*</span><span class="sxs-lookup"><span data-stu-id="8209b-110">*MSCAP_SEL_RESERVED2*</span></span> 
  
> <span data-ttu-id="8209b-111">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="8209b-111">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="8209b-112">*MSCAP_SEL_FOLDER*</span><span class="sxs-lookup"><span data-stu-id="8209b-112">*MSCAP_SEL_FOLDER*</span></span> 
  
> <span data-ttu-id="8209b-113">有关对存储支持文件夹的功能。</span><span class="sxs-lookup"><span data-stu-id="8209b-113">Capabilities about supporting folders on a store.</span></span>
    
 <span data-ttu-id="8209b-114">*MSCAP_SEL_RESERVED3*</span><span class="sxs-lookup"><span data-stu-id="8209b-114">*MSCAP_SEL_RESERVED3*</span></span> 
  
> <span data-ttu-id="8209b-115">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="8209b-115">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="8209b-116">*MSCAP_SEL_RESTRICTION*</span><span class="sxs-lookup"><span data-stu-id="8209b-116">*MSCAP_SEL_RESTRICTION*</span></span> 
  
> <span data-ttu-id="8209b-117">有关对存储支持限制的功能。</span><span class="sxs-lookup"><span data-stu-id="8209b-117">Capabilities about supporting restrictions on a store.</span></span>
    

