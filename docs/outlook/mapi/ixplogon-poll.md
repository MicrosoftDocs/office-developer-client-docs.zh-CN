---
title: IXPLogonPoll
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.Poll
api_type:
- COM
ms.assetid: 1524eb06-7492-42de-b455-e0982bda7ece
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3426854e727ebce7a2ac2243491994ce0e066ac6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591378"
---
# <a name="ixplogonpoll"></a><span data-ttu-id="cd39b-103">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="cd39b-103">IXPLogon::Poll</span></span>

  
  
<span data-ttu-id="cd39b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cd39b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cd39b-105">指示的传输提供程序是否已接收到一个或多个入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="cd39b-105">Indicates whether the transport provider has received one or more inbound messages.</span></span>
  
```cpp
HRESULT Poll(
  ULONG FAR * lpulIncoming
);
```

## <a name="parameters"></a><span data-ttu-id="cd39b-106">参数</span><span class="sxs-lookup"><span data-stu-id="cd39b-106">Parameters</span></span>

 <span data-ttu-id="cd39b-107">_lpulIncoming_</span><span class="sxs-lookup"><span data-stu-id="cd39b-107">_lpulIncoming_</span></span>
  
> <span data-ttu-id="cd39b-108">[输出]一个值，指示存在入站邮件。</span><span class="sxs-lookup"><span data-stu-id="cd39b-108">[out] A value that indicates the existence of inbound messages.</span></span> <span data-ttu-id="cd39b-109">为非零值指示存在入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="cd39b-109">A nonzero value indicates that there are inbound messages.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cd39b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="cd39b-110">Return value</span></span>

<span data-ttu-id="cd39b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd39b-111">S_OK</span></span> 
  
> <span data-ttu-id="cd39b-112">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="cd39b-112">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cd39b-113">注解</span><span class="sxs-lookup"><span data-stu-id="cd39b-113">Remarks</span></span>

<span data-ttu-id="cd39b-114">如果传输提供程序指示它必须轮询新邮件，提供程序会通过传递 LOGON_SP_POLL 标记对[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)调用 MAPI 后台处理程序将定期调用**IXPLogon::Poll**方法会话开头的方法。</span><span class="sxs-lookup"><span data-stu-id="cd39b-114">The MAPI spooler periodically calls the **IXPLogon::Poll** method if the transport provider indicates it must be polled for new messages, which the provider does by passing the LOGON_SP_POLL flag to the call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method at the beginning of a session.</span></span> <span data-ttu-id="cd39b-115">如果有一个**投票**呼叫的响应中指示的传输提供程序或入站的邮件更多可用的过程，MAPI 后台处理程序调用[IXPLogon::StartMessage](ixplogon-startmessage.md)方法，以允许对第一个过程的提供程序的入站邮件消息。</span><span class="sxs-lookup"><span data-stu-id="cd39b-115">If the transport provider indicates in response to the **Poll** call that there are one or more inbound messages available for it to process, the MAPI spooler calls the [IXPLogon::StartMessage](ixplogon-startmessage.md) method to allow the provider to process the first inbound message.</span></span> <span data-ttu-id="cd39b-116">传输提供程序值设置为非零值_lpulIncoming_参数中指示入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="cd39b-116">The transport provider indicates inbound messages by setting the value in the  _lpulIncoming_ parameter to a nonzero value.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cd39b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd39b-117">See also</span></span>



[<span data-ttu-id="cd39b-118">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="cd39b-118">IXPLogon::StartMessage</span></span>](ixplogon-startmessage.md)
  
[<span data-ttu-id="cd39b-119">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="cd39b-119">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="cd39b-120">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="cd39b-120">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

