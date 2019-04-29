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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3e68c564357880b623e02081a228e881c084fa94
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425272"
---
# <a name="ixplogonpoll"></a><span data-ttu-id="7cdc5-103">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="7cdc5-103">IXPLogon::Poll</span></span>

  
  
<span data-ttu-id="7cdc5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7cdc5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7cdc5-105">指示传输提供程序是否已收到一个或多个入站邮件。</span><span class="sxs-lookup"><span data-stu-id="7cdc5-105">Indicates whether the transport provider has received one or more inbound messages.</span></span>
  
```cpp
HRESULT Poll(
  ULONG FAR * lpulIncoming
);
```

## <a name="parameters"></a><span data-ttu-id="7cdc5-106">参数</span><span class="sxs-lookup"><span data-stu-id="7cdc5-106">Parameters</span></span>

 <span data-ttu-id="7cdc5-107">_lpulIncoming_</span><span class="sxs-lookup"><span data-stu-id="7cdc5-107">_lpulIncoming_</span></span>
  
> <span data-ttu-id="7cdc5-108">排除一个指示是否存在入站邮件的值。</span><span class="sxs-lookup"><span data-stu-id="7cdc5-108">[out] A value that indicates the existence of inbound messages.</span></span> <span data-ttu-id="7cdc5-109">非零值表示有入站邮件。</span><span class="sxs-lookup"><span data-stu-id="7cdc5-109">A nonzero value indicates that there are inbound messages.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7cdc5-110">返回值</span><span class="sxs-lookup"><span data-stu-id="7cdc5-110">Return value</span></span>

<span data-ttu-id="7cdc5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cdc5-111">S_OK</span></span> 
  
> <span data-ttu-id="7cdc5-112">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="7cdc5-112">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7cdc5-113">说明</span><span class="sxs-lookup"><span data-stu-id="7cdc5-113">Remarks</span></span>

<span data-ttu-id="7cdc5-114">MAPI 后台处理程序定期调用**IXPLogon::P oll**方法如果传输提供程序指示它必须通过将 LOGON_SP_POLL 标志传递给[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)的新邮件进行轮询::会话开始时的方法。</span><span class="sxs-lookup"><span data-stu-id="7cdc5-114">The MAPI spooler periodically calls the **IXPLogon::Poll** method if the transport provider indicates it must be polled for new messages, which the provider does by passing the LOGON_SP_POLL flag to the call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method at the beginning of a session.</span></span> <span data-ttu-id="7cdc5-115">如果传输提供程序指示有一个或多个可供其处理的入站邮件的**轮询**呼叫响应, MAPI 后台处理程序将调用[IXPLogon:: StartMessage](ixplogon-startmessage.md)方法, 以允许提供程序处理第一个入站消息。</span><span class="sxs-lookup"><span data-stu-id="7cdc5-115">If the transport provider indicates in response to the **Poll** call that there are one or more inbound messages available for it to process, the MAPI spooler calls the [IXPLogon::StartMessage](ixplogon-startmessage.md) method to allow the provider to process the first inbound message.</span></span> <span data-ttu-id="7cdc5-116">传输提供程序通过将_lpulIncoming_参数中的值设置为非零值来指示入站邮件。</span><span class="sxs-lookup"><span data-stu-id="7cdc5-116">The transport provider indicates inbound messages by setting the value in the  _lpulIncoming_ parameter to a nonzero value.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7cdc5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cdc5-117">See also</span></span>



[<span data-ttu-id="7cdc5-118">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="7cdc5-118">IXPLogon::StartMessage</span></span>](ixplogon-startmessage.md)
  
[<span data-ttu-id="7cdc5-119">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="7cdc5-119">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="7cdc5-120">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7cdc5-120">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

