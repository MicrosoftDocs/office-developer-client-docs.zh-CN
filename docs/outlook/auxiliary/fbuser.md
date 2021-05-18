---
title: FBUser
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal649b5400-8dc5-cc5c-3455-f462e2d31689
ms.assetid: ''
description: 标识可能或可能没有可用的忙/闲数据的用户。
ms.openlocfilehash: 2511a94678f9ef8f2cb6be868db4f718d92ecb6d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317659"
---
# <a name="fbuser"></a><span data-ttu-id="7891c-103">FBUser</span><span class="sxs-lookup"><span data-stu-id="7891c-103">FBUser</span></span>

<span data-ttu-id="7891c-104">标识可能或可能没有可用的忙/闲数据的用户。</span><span class="sxs-lookup"><span data-stu-id="7891c-104">Identifies a user who may or may not have free/busy data available.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7891c-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="7891c-105">Quick info</span></span>

```cpp
typedef struct tagFBUser 
{ 
   ULONG m_cbEid; 
   LPENTRYID m_lpEid; 
   ULONG m_ulReserved; 
   LPWSTR m_pwszReserved; 
} FBUser;

```

## <a name="members"></a><span data-ttu-id="7891c-106">成员</span><span class="sxs-lookup"><span data-stu-id="7891c-106">Members</span></span>

<span data-ttu-id="7891c-107">_m_cbEid_</span><span class="sxs-lookup"><span data-stu-id="7891c-107">_m_cbEid_</span></span>
  
> <span data-ttu-id="7891c-108">由 [IMailUser](https://docs.microsoft.com/previous-versions/windows/desktop/wab/-wab-imailuser-deleteprops) 接口表示的邮件用户的条目 ID 的长度。</span><span class="sxs-lookup"><span data-stu-id="7891c-108">The length of the entry ID of the mail user as represented by the [IMailUser](https://docs.microsoft.com/previous-versions/windows/desktop/wab/-wab-imailuser-deleteprops) interface.</span></span> 
    
<span data-ttu-id="7891c-109">_m_lpEid_</span><span class="sxs-lookup"><span data-stu-id="7891c-109">_m_lpEid_</span></span>
  
> <span data-ttu-id="7891c-110">由 **IMailUser** 接口表示的邮件用户的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="7891c-110">The entry ID of the mail user as represented by the **IMailUser** interface.</span></span> 
    
<span data-ttu-id="7891c-111">_m_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="7891c-111">_m_ulReserved_</span></span>
  
> <span data-ttu-id="7891c-112">此参数仅供Outlook内部使用，不受支持。</span><span class="sxs-lookup"><span data-stu-id="7891c-112">This parameter is reserved for Outlook internal use and is not supported.</span></span>
    
<span data-ttu-id="7891c-113">_m_pwszReserved_</span><span class="sxs-lookup"><span data-stu-id="7891c-113">_m_pwszReserved_</span></span>
  
> <span data-ttu-id="7891c-114">此参数仅供Outlook内部使用，不受支持。</span><span class="sxs-lookup"><span data-stu-id="7891c-114">This parameter is reserved for Outlook internal use and is not supported.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7891c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7891c-115">See also</span></span>

- [<span data-ttu-id="7891c-116">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="7891c-116">About the Free/Busy API</span></span>](about-the-free-busy-api.md)  
- [<span data-ttu-id="7891c-117">IFreeBusySupport</span><span class="sxs-lookup"><span data-stu-id="7891c-117">IFreeBusySupport</span></span>](ifreebusysupport.md)

