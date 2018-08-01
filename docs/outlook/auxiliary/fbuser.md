---
title: FBUser
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal649b5400-8dc5-cc5c-3455-f462e2d31689
ms.assetid: ''
description: 标识用户可能也可能没有可用的忙/闲数据。
ms.openlocfilehash: e83689e28f5fb6e1eae28d760bb57f5ad3796f8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774176"
---
# <a name="fbuser"></a><span data-ttu-id="78ecb-103">FBUser</span><span class="sxs-lookup"><span data-stu-id="78ecb-103">FBUser</span></span>

<span data-ttu-id="78ecb-104">标识用户可能也可能没有可用的忙/闲数据。</span><span class="sxs-lookup"><span data-stu-id="78ecb-104">Identifies a user who may or may not have free/busy data available.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="78ecb-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="78ecb-105">Quick info</span></span>

```cpp
typedef struct tagFBUser 
{ 
   ULONG m_cbEid; 
   LPENTRYID m_lpEid; 
   ULONG m_ulReserved; 
   LPWSTR m_pwszReserved; 
} FBUser;

```

## <a name="members"></a><span data-ttu-id="78ecb-106">Members</span><span class="sxs-lookup"><span data-stu-id="78ecb-106">Members</span></span>

<span data-ttu-id="78ecb-107">_m_cbEid_</span><span class="sxs-lookup"><span data-stu-id="78ecb-107">_m_cbEid_</span></span>
  
> <span data-ttu-id="78ecb-108">邮件用户表示[IMailUser](http://msdn.microsoft.com/library/wab._wab_IMailUser%28Office.15%29.aspx)接口的条目 ID 的长度。</span><span class="sxs-lookup"><span data-stu-id="78ecb-108">The length of the entry ID of the mail user as represented by the [IMailUser](http://msdn.microsoft.com/library/wab._wab_IMailUser%28Office.15%29.aspx) interface.</span></span> 
    
<span data-ttu-id="78ecb-109">_m_lpEid_</span><span class="sxs-lookup"><span data-stu-id="78ecb-109">_m_lpEid_</span></span>
  
> <span data-ttu-id="78ecb-110">邮件用户表示**IMailUser**接口的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="78ecb-110">The entry ID of the mail user as represented by the **IMailUser** interface.</span></span> 
    
<span data-ttu-id="78ecb-111">_m_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="78ecb-111">_m_ulReserved_</span></span>
  
> <span data-ttu-id="78ecb-112">此参数仅供 Outlook 内部使用，不支持。</span><span class="sxs-lookup"><span data-stu-id="78ecb-112">This parameter is reserved for Outlook internal use and is not supported.</span></span>
    
<span data-ttu-id="78ecb-113">_m_pwszReserved_</span><span class="sxs-lookup"><span data-stu-id="78ecb-113">_m_pwszReserved_</span></span>
  
> <span data-ttu-id="78ecb-114">此参数仅供 Outlook 内部使用，不支持。</span><span class="sxs-lookup"><span data-stu-id="78ecb-114">This parameter is reserved for Outlook internal use and is not supported.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="78ecb-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78ecb-115">See also</span></span>

- [<span data-ttu-id="78ecb-116">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="78ecb-116">About the Free/Busy API</span></span>](about-the-free-busy-api.md)  
- [<span data-ttu-id="78ecb-117">IFreeBusySupport</span><span class="sxs-lookup"><span data-stu-id="78ecb-117">IFreeBusySupport</span></span>](ifreebusysupport.md)

