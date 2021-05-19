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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417201"
---
# <a name="mscap_selector"></a><span data-ttu-id="c8fca-103">MSCAP_SELECTOR</span><span class="sxs-lookup"><span data-stu-id="c8fca-103">MSCAP_SELECTOR</span></span>

  
  
<span data-ttu-id="c8fca-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8fca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8fca-105">指定为存储区返回的功能。</span><span class="sxs-lookup"><span data-stu-id="c8fca-105">Specifies the capabilities to return for a store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="c8fca-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="c8fca-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="c8fca-107">成员</span><span class="sxs-lookup"><span data-stu-id="c8fca-107">Members</span></span>

 <span data-ttu-id="c8fca-108">*MSCAP_SEL_RESERVED1*</span><span class="sxs-lookup"><span data-stu-id="c8fca-108">*MSCAP_SEL_RESERVED1*</span></span> 
  
> <span data-ttu-id="c8fca-109">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="c8fca-109">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="c8fca-110">*MSCAP_SEL_RESERVED2*</span><span class="sxs-lookup"><span data-stu-id="c8fca-110">*MSCAP_SEL_RESERVED2*</span></span> 
  
> <span data-ttu-id="c8fca-111">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="c8fca-111">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="c8fca-112">*MSCAP_SEL_FOLDER*</span><span class="sxs-lookup"><span data-stu-id="c8fca-112">*MSCAP_SEL_FOLDER*</span></span> 
  
> <span data-ttu-id="c8fca-113">有关在存储区上支持文件夹的功能。</span><span class="sxs-lookup"><span data-stu-id="c8fca-113">Capabilities about supporting folders on a store.</span></span>
    
 <span data-ttu-id="c8fca-114">*MSCAP_SEL_RESERVED3*</span><span class="sxs-lookup"><span data-stu-id="c8fca-114">*MSCAP_SEL_RESERVED3*</span></span> 
  
> <span data-ttu-id="c8fca-115">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="c8fca-115">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="c8fca-116">*MSCAP_SEL_RESTRICTION*</span><span class="sxs-lookup"><span data-stu-id="c8fca-116">*MSCAP_SEL_RESTRICTION*</span></span> 
  
> <span data-ttu-id="c8fca-117">有关对存储区的支持限制的功能。</span><span class="sxs-lookup"><span data-stu-id="c8fca-117">Capabilities about supporting restrictions on a store.</span></span>
    

