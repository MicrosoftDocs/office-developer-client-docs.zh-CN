---
title: IXPLogonTransportLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.TransportLogoff
api_type:
- COM
ms.assetid: b2b368ce-4486-4f90-985f-59e50ca95229
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 78b4feeca263035b9c90184f10edd294e6cd7b10
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417859"
---
# <a name="ixplogontransportlogoff"></a><span data-ttu-id="68bf8-103">IXPLogon::TransportLogoff</span><span class="sxs-lookup"><span data-stu-id="68bf8-103">IXPLogon::TransportLogoff</span></span>

  
  
<span data-ttu-id="68bf8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="68bf8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="68bf8-105">启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="68bf8-105">Initiates the logoff process.</span></span> 
  
```cpp
HRESULT TransportLogoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="68bf8-106">参数</span><span class="sxs-lookup"><span data-stu-id="68bf8-106">Parameters</span></span>

 <span data-ttu-id="68bf8-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="68bf8-107">_ulFlags_</span></span>
  
> <span data-ttu-id="68bf8-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="68bf8-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="68bf8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="68bf8-109">Return value</span></span>

<span data-ttu-id="68bf8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="68bf8-110">S_OK</span></span> 
  
> <span data-ttu-id="68bf8-111">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="68bf8-111">The call succeeded and returned the expected value or values.</span></span> <span data-ttu-id="68bf8-112">如果返回 S_OK 之外的任何内容, 则将注销该提供程序。</span><span class="sxs-lookup"><span data-stu-id="68bf8-112">If anything other than S_OK is returned, the provider is logged off.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="68bf8-113">说明</span><span class="sxs-lookup"><span data-stu-id="68bf8-113">Remarks</span></span>

<span data-ttu-id="68bf8-114">MAPI 后台处理程序调用**IXPLogon:: TransportLogoff**方法, 以终止特定用户的传输提供程序会话。</span><span class="sxs-lookup"><span data-stu-id="68bf8-114">The MAPI spooler calls the **IXPLogon::TransportLogoff** method to terminate a transport provider session for a particular user.</span></span> <span data-ttu-id="68bf8-115">在调用**TransportLogoff**之前, MAPI 后台处理程序会丢弃有关在[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法中传递的此会话的受支持的邮件地址类型的任何数据。</span><span class="sxs-lookup"><span data-stu-id="68bf8-115">Before calling **TransportLogoff**, the MAPI spooler discards any data about supported messaging address types for this session passed in the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="68bf8-116">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="68bf8-116">Notes to implementers</span></span>

<span data-ttu-id="68bf8-117">传输提供程序应准备好随时接受对**TransportLogoff**的调用。</span><span class="sxs-lookup"><span data-stu-id="68bf8-117">The transport provider should be prepared to accept a call to **TransportLogoff** at any time.</span></span> <span data-ttu-id="68bf8-118">如果正在处理邮件, 则提供程序应停止发送过程。</span><span class="sxs-lookup"><span data-stu-id="68bf8-118">If a message is in process, the provider should stop the sending process.</span></span> 
  
<span data-ttu-id="68bf8-119">传输提供程序应释放为其当前会话分配的所有资源。</span><span class="sxs-lookup"><span data-stu-id="68bf8-119">The transport provider should release all resources allocated for its current session.</span></span> <span data-ttu-id="68bf8-120">如果它已使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为此会话分配了任何内存, 它应使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放内存。</span><span class="sxs-lookup"><span data-stu-id="68bf8-120">If it has allocated any memory for this session with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, it should free the memory by using the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> <span data-ttu-id="68bf8-121">传输提供程序为满足对[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法的调用而分配的任何内存都可以安全地发布。</span><span class="sxs-lookup"><span data-stu-id="68bf8-121">Any memory allocated by the transport provider to satisfy calls to the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method can be safely released at this time.</span></span> 
  
<span data-ttu-id="68bf8-122">通常, 在完成**TransportLogoff**调用之后, 提供程序应首先通过调用[IMAPISupport:: MakeInvalid](imapisupport-makeinvalid.md)方法来使其登录对象失效, 然后释放其支持对象。</span><span class="sxs-lookup"><span data-stu-id="68bf8-122">Usually, on completing a **TransportLogoff** call, a provider should first invalidate its logon object by calling the [IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md) method and then release its support object.</span></span> <span data-ttu-id="68bf8-123">提供程序的**TransportLogoff**实现将在最后发布支持对象, 因为在发布支持对象时, MAPI 后台处理程序还可以释放提供程序对象本身。</span><span class="sxs-lookup"><span data-stu-id="68bf8-123">The provider's implementation of **TransportLogoff** should release the support object last, because when the support object is released, the MAPI spooler can also release the provider object itself.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="68bf8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68bf8-124">See also</span></span>



[<span data-ttu-id="68bf8-125">IMAPISupport::MakeInvalid</span><span class="sxs-lookup"><span data-stu-id="68bf8-125">IMAPISupport::MakeInvalid</span></span>](imapisupport-makeinvalid.md)
  
[<span data-ttu-id="68bf8-126">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="68bf8-126">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md)
  
[<span data-ttu-id="68bf8-127">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="68bf8-127">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)
  
[<span data-ttu-id="68bf8-128">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="68bf8-128">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="68bf8-129">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="68bf8-129">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="68bf8-130">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="68bf8-130">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

