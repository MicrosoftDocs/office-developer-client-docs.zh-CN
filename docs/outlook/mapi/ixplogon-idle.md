---
title: IXPLogonIdle
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.Idle
api_type:
- COM
ms.assetid: 8f600db6-f6a6-44f9-aef7-c1309f61eb12
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 12aa8b79e38320d9767a6c333cb0197ea5669862
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578009"
---
# <a name="ixplogonidle"></a><span data-ttu-id="7ab3f-103">IXPLogon::Idle</span><span class="sxs-lookup"><span data-stu-id="7ab3f-103">IXPLogon::Idle</span></span>

  
  
<span data-ttu-id="7ab3f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ab3f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ab3f-105">指示系统空闲，启用传输提供程序执行低优先级操作。</span><span class="sxs-lookup"><span data-stu-id="7ab3f-105">Indicates that the system is idle, enabling the transport provider to perform low-priority operations.</span></span>
  
```cpp
HRESULT Idle(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="7ab3f-106">参数</span><span class="sxs-lookup"><span data-stu-id="7ab3f-106">Parameters</span></span>

 <span data-ttu-id="7ab3f-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7ab3f-107">_ulFlags_</span></span>
  
> <span data-ttu-id="7ab3f-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="7ab3f-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7ab3f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7ab3f-109">Return value</span></span>

<span data-ttu-id="7ab3f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ab3f-110">S_OK</span></span> 
  
> <span data-ttu-id="7ab3f-111">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="7ab3f-111">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7ab3f-112">注解</span><span class="sxs-lookup"><span data-stu-id="7ab3f-112">Remarks</span></span>

<span data-ttu-id="7ab3f-113">MAPI 后台处理程序定期调用**IXPLogon::Idle**方法中，如果请求，期间系统时通过对打开当前会话的[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)方法的调用中传递 XP_LOGON_SP 标志处于空闲状态的时间。</span><span class="sxs-lookup"><span data-stu-id="7ab3f-113">The MAPI spooler periodically calls the **IXPLogon::Idle** method, if requested, during times when the system is idle by passing the XP_LOGON_SP flag in the call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method that opened the current session.</span></span> <span data-ttu-id="7ab3f-114">有时系统空闲时，传输提供程序可以执行后台操作的链接不适当期间其他呼叫，或需要定期发生。</span><span class="sxs-lookup"><span data-stu-id="7ab3f-114">At times when the system is idle, the transport provider can perform background operations that are not appropriate during other calls, or that need to occur on a regular basis.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7ab3f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ab3f-115">See also</span></span>



[<span data-ttu-id="7ab3f-116">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="7ab3f-116">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="7ab3f-117">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7ab3f-117">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

