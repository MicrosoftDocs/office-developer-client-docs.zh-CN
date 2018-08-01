---
title: IABLogonLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.Logoff
api_type:
- COM
ms.assetid: a36465e2-7be9-4bd6-8091-685f0a045aa9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e441e84e0bddff2e5a989849dbcf593320340d2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775219"
---
# <a name="iablogonlogoff"></a><span data-ttu-id="f9d03-103">IABLogon::Logoff</span><span class="sxs-lookup"><span data-stu-id="f9d03-103">IABLogon::Logoff</span></span>

  
  
<span data-ttu-id="f9d03-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f9d03-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f9d03-105">启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="f9d03-105">Initiates the logoff process.</span></span>
  
```cpp
HRESULT Logoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="f9d03-106">参数</span><span class="sxs-lookup"><span data-stu-id="f9d03-106">Parameters</span></span>

 <span data-ttu-id="f9d03-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f9d03-107">_ulFlags_</span></span>
  
> <span data-ttu-id="f9d03-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="f9d03-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f9d03-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f9d03-109">Return value</span></span>

<span data-ttu-id="f9d03-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9d03-110">S_OK</span></span> 
  
> <span data-ttu-id="f9d03-111">注销过程已成功启动。</span><span class="sxs-lookup"><span data-stu-id="f9d03-111">The logoff process was successfully initiated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f9d03-112">说明</span><span class="sxs-lookup"><span data-stu-id="f9d03-112">Remarks</span></span>

<span data-ttu-id="f9d03-113">客户端调用[IMAPISession::Logoff](imapisession-logoff.md)方法来结束会话时，通常被启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="f9d03-113">The logoff process is typically started when a client calls the [IMAPISession::Logoff](imapisession-logoff.md) method to end a session.</span></span> <span data-ttu-id="f9d03-114">MAPI 然后调用每个通讯簿提供程序的**IABLogon::Logoff**方法来启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="f9d03-114">MAPI then calls each address book provider's **IABLogon::Logoff** method to start the logoff process.</span></span> 
  
<span data-ttu-id="f9d03-115">**IABLogon::Logoff**方法将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f9d03-115">The **IABLogon::Logoff** method does the following:</span></span> 
  
- <span data-ttu-id="f9d03-116">释放所有打开的对象，如任何子对象或状态对象。</span><span class="sxs-lookup"><span data-stu-id="f9d03-116">Releases all open objects, such as any subobjects or the status object.</span></span>
    
- <span data-ttu-id="f9d03-117">释放提供程序的支持对象。</span><span class="sxs-lookup"><span data-stu-id="f9d03-117">Releases the provider's support object.</span></span>
    
<span data-ttu-id="f9d03-118">通讯簿提供程序的注销过程的详细信息，请参阅[关机的情况下 Service Provider](shutting-down-a-service-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d03-118">For more information about the logoff process of address book providers, see [Shutting Down a Service Provider](shutting-down-a-service-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9d03-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9d03-119">See also</span></span>



[<span data-ttu-id="f9d03-120">IABProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="f9d03-120">IABProvider::Logon</span></span>](iabprovider-logon.md)
  
[<span data-ttu-id="f9d03-121">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f9d03-121">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

