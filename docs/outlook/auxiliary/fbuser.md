---
title: FBUser
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal649b5400-8dc5-cc5c-3455-f462e2d31689
ms.assetid: ''
description: 标识用户可能也可能没有可用的忙/闲数据。
ms.openlocfilehash: 2511a94678f9ef8f2cb6be868db4f718d92ecb6d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387900"
---
# <a name="fbuser"></a><span data-ttu-id="fc60a-103">FBUser</span><span class="sxs-lookup"><span data-stu-id="fc60a-103">FBUser</span></span>

<span data-ttu-id="fc60a-104">标识用户可能也可能没有可用的忙/闲数据。</span><span class="sxs-lookup"><span data-stu-id="fc60a-104">Identifies a user who may or may not have free/busy data available.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="fc60a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="fc60a-105">Quick info</span></span>

```cpp
typedef struct tagFBUser 
{ 
   ULONG m_cbEid; 
   LPENTRYID m_lpEid; 
   ULONG m_ulReserved; 
   LPWSTR m_pwszReserved; 
} FBUser;

```

## <a name="members"></a><span data-ttu-id="fc60a-106">Members</span><span class="sxs-lookup"><span data-stu-id="fc60a-106">Members</span></span>

<span data-ttu-id="fc60a-107">_m_cbEid_</span><span class="sxs-lookup"><span data-stu-id="fc60a-107">_m_cbEid_</span></span>
  
> <span data-ttu-id="fc60a-108">邮件用户表示[IMailUser](https://docs.microsoft.com/previous-versions/windows/desktop/wab/-wab-imailuser-deleteprops)接口的条目 ID 的长度。</span><span class="sxs-lookup"><span data-stu-id="fc60a-108">The length of the entry ID of the mail user as represented by the [IMailUser](https://docs.microsoft.com/previous-versions/windows/desktop/wab/-wab-imailuser-deleteprops) interface.</span></span> 
    
<span data-ttu-id="fc60a-109">_m_lpEid_</span><span class="sxs-lookup"><span data-stu-id="fc60a-109">_m_lpEid_</span></span>
  
> <span data-ttu-id="fc60a-110">邮件用户表示**IMailUser**接口的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="fc60a-110">The entry ID of the mail user as represented by the **IMailUser** interface.</span></span> 
    
<span data-ttu-id="fc60a-111">_m_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="fc60a-111">_m_ulReserved_</span></span>
  
> <span data-ttu-id="fc60a-112">此参数仅供 Outlook 内部使用，不支持。</span><span class="sxs-lookup"><span data-stu-id="fc60a-112">This parameter is reserved for Outlook internal use and is not supported.</span></span>
    
<span data-ttu-id="fc60a-113">_m_pwszReserved_</span><span class="sxs-lookup"><span data-stu-id="fc60a-113">_m_pwszReserved_</span></span>
  
> <span data-ttu-id="fc60a-114">此参数仅供 Outlook 内部使用，不支持。</span><span class="sxs-lookup"><span data-stu-id="fc60a-114">This parameter is reserved for Outlook internal use and is not supported.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fc60a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc60a-115">See also</span></span>

- [<span data-ttu-id="fc60a-116">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="fc60a-116">About the Free/Busy API</span></span>](about-the-free-busy-api.md)  
- [<span data-ttu-id="fc60a-117">IFreeBusySupport</span><span class="sxs-lookup"><span data-stu-id="fc60a-117">IFreeBusySupport</span></span>](ifreebusysupport.md)

