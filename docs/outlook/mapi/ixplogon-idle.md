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
ms.openlocfilehash: 75607550f1d6085a670ad997238994400e08f7bd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776122"
---
# <a name="ixplogonidle"></a><span data-ttu-id="6e91c-103">IXPLogon::Idle</span><span class="sxs-lookup"><span data-stu-id="6e91c-103">IXPLogon::Idle</span></span>

  
  
<span data-ttu-id="6e91c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6e91c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6e91c-105">指示系统空闲，启用传输提供程序执行低优先级操作。</span><span class="sxs-lookup"><span data-stu-id="6e91c-105">Indicates that the system is idle, enabling the transport provider to perform low-priority operations.</span></span>
  
```cpp
HRESULT Idle(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="6e91c-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e91c-106">Parameters</span></span>

 <span data-ttu-id="6e91c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6e91c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="6e91c-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="6e91c-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6e91c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6e91c-109">Return value</span></span>

<span data-ttu-id="6e91c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e91c-110">S_OK</span></span> 
  
> <span data-ttu-id="6e91c-111">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="6e91c-111">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6e91c-112">说明</span><span class="sxs-lookup"><span data-stu-id="6e91c-112">Remarks</span></span>

<span data-ttu-id="6e91c-113">MAPI 后台处理程序定期调用**IXPLogon::Idle**方法中，如果请求，期间系统时通过对打开当前会话的[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)方法的调用中传递 XP_LOGON_SP 标志处于空闲状态的时间。</span><span class="sxs-lookup"><span data-stu-id="6e91c-113">The MAPI spooler periodically calls the **IXPLogon::Idle** method, if requested, during times when the system is idle by passing the XP_LOGON_SP flag in the call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method that opened the current session.</span></span> <span data-ttu-id="6e91c-114">有时系统空闲时，传输提供程序可以执行后台操作的链接不适当期间其他呼叫，或需要定期发生。</span><span class="sxs-lookup"><span data-stu-id="6e91c-114">At times when the system is idle, the transport provider can perform background operations that are not appropriate during other calls, or that need to occur on a regular basis.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e91c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e91c-115">See also</span></span>



[<span data-ttu-id="6e91c-116">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="6e91c-116">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="6e91c-117">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6e91c-117">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

