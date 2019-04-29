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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ceca6a2dbe5f80f8a3499e509db8d5e6c35d72d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436046"
---
# <a name="ixplogonidle"></a><span data-ttu-id="baa89-103">IXPLogon::Idle</span><span class="sxs-lookup"><span data-stu-id="baa89-103">IXPLogon::Idle</span></span>

  
  
<span data-ttu-id="baa89-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="baa89-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="baa89-105">指示系统处于空闲状态, 使传输提供程序能够执行低优先级操作。</span><span class="sxs-lookup"><span data-stu-id="baa89-105">Indicates that the system is idle, enabling the transport provider to perform low-priority operations.</span></span>
  
```cpp
HRESULT Idle(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="baa89-106">参数</span><span class="sxs-lookup"><span data-stu-id="baa89-106">Parameters</span></span>

 <span data-ttu-id="baa89-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="baa89-107">_ulFlags_</span></span>
  
> <span data-ttu-id="baa89-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="baa89-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="baa89-109">返回值</span><span class="sxs-lookup"><span data-stu-id="baa89-109">Return value</span></span>

<span data-ttu-id="baa89-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="baa89-110">S_OK</span></span> 
  
> <span data-ttu-id="baa89-111">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="baa89-111">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="baa89-112">说明</span><span class="sxs-lookup"><span data-stu-id="baa89-112">Remarks</span></span>

<span data-ttu-id="baa89-113">在系统空闲时, MAPI 后台处理程序定期调用**IXPLogon:: idle**方法 (如果请求), 通过在调用[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)方法时传递对打开当前会话的 XP_LOGON_SP 标志。</span><span class="sxs-lookup"><span data-stu-id="baa89-113">The MAPI spooler periodically calls the **IXPLogon::Idle** method, if requested, during times when the system is idle by passing the XP_LOGON_SP flag in the call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method that opened the current session.</span></span> <span data-ttu-id="baa89-114">在系统处于空闲状态时, 传输提供程序可以执行在其他呼叫过程中不适合或定期发生的后台操作。</span><span class="sxs-lookup"><span data-stu-id="baa89-114">At times when the system is idle, the transport provider can perform background operations that are not appropriate during other calls, or that need to occur on a regular basis.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="baa89-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="baa89-115">See also</span></span>



[<span data-ttu-id="baa89-116">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="baa89-116">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="baa89-117">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="baa89-117">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

