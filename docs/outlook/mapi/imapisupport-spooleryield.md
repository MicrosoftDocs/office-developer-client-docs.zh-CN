---
title: IMAPISupportSpoolerYield
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.SpoolerYield
api_type:
- COM
ms.assetid: f5c6ba8f-4ef5-4d60-b4e6-5b9160ec4e99
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d90f502e2cd7f97ac273ebecedbd0363097b1d60
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584952"
---
# <a name="imapisupportspooleryield"></a><span data-ttu-id="cda00-103">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="cda00-103">IMAPISupport::SpoolerYield</span></span>

  
  
<span data-ttu-id="cda00-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cda00-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cda00-105">到 MAPI 后台处理程序提供的 CPU 的控件，以便它可以执行它认为需要的任何任务。</span><span class="sxs-lookup"><span data-stu-id="cda00-105">Gives control of the CPU to the MAPI spooler so that it can perform any tasks it considers necessary.</span></span>
  
```cpp
HRESULT SpoolerYield(
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="cda00-106">参数</span><span class="sxs-lookup"><span data-stu-id="cda00-106">Parameters</span></span>

 <span data-ttu-id="cda00-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cda00-107">_ulFlags_</span></span>
  
> <span data-ttu-id="cda00-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="cda00-108">Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cda00-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cda00-109">Return value</span></span>

<span data-ttu-id="cda00-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cda00-110">S_OK</span></span> 
  
> <span data-ttu-id="cda00-111">传输提供程序成功发布 CPU。</span><span class="sxs-lookup"><span data-stu-id="cda00-111">The transport provider successfully released the CPU.</span></span>
    
<span data-ttu-id="cda00-112">MAPI_W_CANCEL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="cda00-112">MAPI_W_CANCEL_MESSAGE</span></span> 
  
> <span data-ttu-id="cda00-113">指示要停止邮件传递到尚未收到任何收件人的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="cda00-113">Instructs the transport provider to stop the delivery of the message to any recipients that have not yet received it.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cda00-114">注解</span><span class="sxs-lookup"><span data-stu-id="cda00-114">Remarks</span></span>

<span data-ttu-id="cda00-115">对于传输提供程序支持对象实现**IMAPISupport::SpoolerYield**方法。</span><span class="sxs-lookup"><span data-stu-id="cda00-115">The **IMAPISupport::SpoolerYield** method is implemented for transport provider support objects.</span></span> <span data-ttu-id="cda00-116">传输提供程序调用**SpoolerYield**以允许 MAPI 后台处理程序完成任何所需的处理。</span><span class="sxs-lookup"><span data-stu-id="cda00-116">Transport providers call **SpoolerYield** to allow the MAPI spooler to accomplish any necessary processing.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="cda00-117">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="cda00-117">Notes to callers</span></span>

<span data-ttu-id="cda00-118">执行可暂停的冗长操作时，请调用**SpoolerYield** 。</span><span class="sxs-lookup"><span data-stu-id="cda00-118">Call **SpoolerYield** when you are performing lengthy operations that can be paused.</span></span> <span data-ttu-id="cda00-119">这样，前景过程较长的操作，如传递到大型收件人列表跨繁忙的网络中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cda00-119">This allows foreground applications to run during a long operation, such as delivery to a large recipient list across a busy network.</span></span> 
  
<span data-ttu-id="cda00-120">如果**SpoolerYield**返回与 MAPI_W_CANCEL_MESSAGE，MAPI 后台处理程序已确定无法再发送邮件。</span><span class="sxs-lookup"><span data-stu-id="cda00-120">If **SpoolerYield** returns with MAPI_W_CANCEL_MESSAGE, the MAPI spooler has determined that the message should no longer be sent.</span></span> <span data-ttu-id="cda00-121">如果可能对您调用进程和退出，返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="cda00-121">Return MAPI_E_USER_CANCEL to your calling process and exit, if possible.</span></span> 
  
<span data-ttu-id="cda00-122">有关转交给 MAPI 后台处理程序的详细信息，请参阅[使用 MAPI 后台处理程序的交互](interacting-with-the-mapi-spooler.md)。</span><span class="sxs-lookup"><span data-stu-id="cda00-122">For more information about yielding to the MAPI spooler, see [Interacting with the MAPI Spooler](interacting-with-the-mapi-spooler.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cda00-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cda00-123">See also</span></span>



[<span data-ttu-id="cda00-124">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="cda00-124">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

