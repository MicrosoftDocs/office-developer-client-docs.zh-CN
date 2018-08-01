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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 195f2d718428eb8bb618fc982488c276d8a536da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776137"
---
# <a name="ixplogontransportlogoff"></a><span data-ttu-id="17a95-103">IXPLogon::TransportLogoff</span><span class="sxs-lookup"><span data-stu-id="17a95-103">IXPLogon::TransportLogoff</span></span>

  
  
<span data-ttu-id="17a95-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="17a95-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="17a95-105">启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="17a95-105">Initiates the logoff process.</span></span> 
  
```cpp
HRESULT TransportLogoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="17a95-106">参数</span><span class="sxs-lookup"><span data-stu-id="17a95-106">Parameters</span></span>

 <span data-ttu-id="17a95-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="17a95-107">_ulFlags_</span></span>
  
> <span data-ttu-id="17a95-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="17a95-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="17a95-109">返回值</span><span class="sxs-lookup"><span data-stu-id="17a95-109">Return value</span></span>

<span data-ttu-id="17a95-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="17a95-110">S_OK</span></span> 
  
> <span data-ttu-id="17a95-111">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="17a95-111">The call succeeded and returned the expected value or values.</span></span> <span data-ttu-id="17a95-112">如果返回 S_OK 之外的任何，提供程序被注销。</span><span class="sxs-lookup"><span data-stu-id="17a95-112">If anything other than S_OK is returned, the provider is logged off.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="17a95-113">说明</span><span class="sxs-lookup"><span data-stu-id="17a95-113">Remarks</span></span>

<span data-ttu-id="17a95-114">MAPI 后台处理程序调用**IXPLogon::TransportLogoff**方法终止传输提供程序会话的特定用户。</span><span class="sxs-lookup"><span data-stu-id="17a95-114">The MAPI spooler calls the **IXPLogon::TransportLogoff** method to terminate a transport provider session for a particular user.</span></span> <span data-ttu-id="17a95-115">调用**TransportLogoff**之前, MAPI 后台处理程序放弃[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法中传递该会话的支持邮件的地址类型有关的任何数据。</span><span class="sxs-lookup"><span data-stu-id="17a95-115">Before calling **TransportLogoff**, the MAPI spooler discards any data about supported messaging address types for this session passed in the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="17a95-116">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="17a95-116">Notes to implementers</span></span>

<span data-ttu-id="17a95-117">传输提供程序应准备随时接受**TransportLogoff**调用。</span><span class="sxs-lookup"><span data-stu-id="17a95-117">The transport provider should be prepared to accept a call to **TransportLogoff** at any time.</span></span> <span data-ttu-id="17a95-118">如果消息的过程中，提供程序应停止发送进程。</span><span class="sxs-lookup"><span data-stu-id="17a95-118">If a message is in process, the provider should stop the sending process.</span></span> 
  
<span data-ttu-id="17a95-119">传输提供程序应释放分配其当前会话的所有资源。</span><span class="sxs-lookup"><span data-stu-id="17a95-119">The transport provider should release all resources allocated for its current session.</span></span> <span data-ttu-id="17a95-120">如果它具有与[MAPIAllocateBuffer](mapiallocatebuffer.md)函数该会话的分配任何内存，它应使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放内存。</span><span class="sxs-lookup"><span data-stu-id="17a95-120">If it has allocated any memory for this session with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, it should free the memory by using the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> <span data-ttu-id="17a95-121">此时可以安全地释放由传输提供程序以满足对[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法调用分配任何内存。</span><span class="sxs-lookup"><span data-stu-id="17a95-121">Any memory allocated by the transport provider to satisfy calls to the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method can be safely released at this time.</span></span> 
  
<span data-ttu-id="17a95-122">通常，在完成**TransportLogoff**呼叫，提供程序应首先使其登录对象无效通过调用[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)方法，然后释放其支持对象。</span><span class="sxs-lookup"><span data-stu-id="17a95-122">Usually, on completing a **TransportLogoff** call, a provider should first invalidate its logon object by calling the [IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md) method and then release its support object.</span></span> <span data-ttu-id="17a95-123">因为 MAPI 后台处理程序发布支持对象时，还可以解除提供商对象本身， **TransportLogoff**提供程序的实现应最后一发行版支持对象。</span><span class="sxs-lookup"><span data-stu-id="17a95-123">The provider's implementation of **TransportLogoff** should release the support object last, because when the support object is released, the MAPI spooler can also release the provider object itself.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="17a95-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17a95-124">See also</span></span>



[<span data-ttu-id="17a95-125">IMAPISupport::MakeInvalid</span><span class="sxs-lookup"><span data-stu-id="17a95-125">IMAPISupport::MakeInvalid</span></span>](imapisupport-makeinvalid.md)
  
[<span data-ttu-id="17a95-126">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="17a95-126">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md)
  
[<span data-ttu-id="17a95-127">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="17a95-127">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)
  
[<span data-ttu-id="17a95-128">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="17a95-128">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="17a95-129">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="17a95-129">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="17a95-130">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="17a95-130">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

