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
# <a name="ixplogonidle"></a><span data-ttu-id="1c608-103">IXPLogon::Idle</span><span class="sxs-lookup"><span data-stu-id="1c608-103">IXPLogon::Idle</span></span>

  
  
<span data-ttu-id="1c608-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c608-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1c608-105">指示系统处于空闲状态，使传输提供程序能够执行低优先级操作。</span><span class="sxs-lookup"><span data-stu-id="1c608-105">Indicates that the system is idle, enabling the transport provider to perform low-priority operations.</span></span>
  
```cpp
HRESULT Idle(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="1c608-106">参数</span><span class="sxs-lookup"><span data-stu-id="1c608-106">Parameters</span></span>

 <span data-ttu-id="1c608-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1c608-107">_ulFlags_</span></span>
  
> <span data-ttu-id="1c608-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="1c608-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1c608-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1c608-109">Return value</span></span>

<span data-ttu-id="1c608-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c608-110">S_OK</span></span> 
  
> <span data-ttu-id="1c608-111">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="1c608-111">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1c608-112">备注</span><span class="sxs-lookup"><span data-stu-id="1c608-112">Remarks</span></span>

<span data-ttu-id="1c608-113">如果请求，MAPI 后台处理程序在系统空闲时定期调用 **IXPLogon：：Idle** 方法，方法是在调用中将 XP_LOGON_SP 标志传递给打开当前会话的 [IXPProvider：：TransportLogon](ixpprovider-transportlogon.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="1c608-113">The MAPI spooler periodically calls the **IXPLogon::Idle** method, if requested, during times when the system is idle by passing the XP_LOGON_SP flag in the call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method that opened the current session.</span></span> <span data-ttu-id="1c608-114">当系统处于空闲状态时，传输提供程序可以执行其他调用期间不适合的后台操作，或者需要定期执行这些后台操作。</span><span class="sxs-lookup"><span data-stu-id="1c608-114">At times when the system is idle, the transport provider can perform background operations that are not appropriate during other calls, or that need to occur on a regular basis.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1c608-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c608-115">See also</span></span>



[<span data-ttu-id="1c608-116">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="1c608-116">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="1c608-117">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1c608-117">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

