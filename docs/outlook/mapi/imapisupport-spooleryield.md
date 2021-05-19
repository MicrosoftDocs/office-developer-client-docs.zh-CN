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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f6cdebf82d8b84ada3d029865867c5192af90b0d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409907"
---
# <a name="imapisupportspooleryield"></a><span data-ttu-id="ff339-103">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="ff339-103">IMAPISupport::SpoolerYield</span></span>

  
  
<span data-ttu-id="ff339-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff339-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff339-105">将 CPU 控制权授予 MAPI 后台处理程序，以便它可以执行认为必要的任何任务。</span><span class="sxs-lookup"><span data-stu-id="ff339-105">Gives control of the CPU to the MAPI spooler so that it can perform any tasks it considers necessary.</span></span>
  
```cpp
HRESULT SpoolerYield(
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="ff339-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff339-106">Parameters</span></span>

 <span data-ttu-id="ff339-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ff339-107">_ulFlags_</span></span>
  
> <span data-ttu-id="ff339-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="ff339-108">Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ff339-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ff339-109">Return value</span></span>

<span data-ttu-id="ff339-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff339-110">S_OK</span></span> 
  
> <span data-ttu-id="ff339-111">传输提供程序已成功释放 CPU。</span><span class="sxs-lookup"><span data-stu-id="ff339-111">The transport provider successfully released the CPU.</span></span>
    
<span data-ttu-id="ff339-112">MAPI_W_CANCEL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="ff339-112">MAPI_W_CANCEL_MESSAGE</span></span> 
  
> <span data-ttu-id="ff339-113">指示传输提供程序停止向尚未收到邮件的任何收件人传递邮件。</span><span class="sxs-lookup"><span data-stu-id="ff339-113">Instructs the transport provider to stop the delivery of the message to any recipients that have not yet received it.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ff339-114">备注</span><span class="sxs-lookup"><span data-stu-id="ff339-114">Remarks</span></span>

<span data-ttu-id="ff339-115">**为传输提供程序支持对象实现 IMAPISupport：：SpoolerYield** 方法。</span><span class="sxs-lookup"><span data-stu-id="ff339-115">The **IMAPISupport::SpoolerYield** method is implemented for transport provider support objects.</span></span> <span data-ttu-id="ff339-116">传输提供程序调用 **SpoolerYield** 以允许 MAPI 后台处理程序完成任何必要的处理。</span><span class="sxs-lookup"><span data-stu-id="ff339-116">Transport providers call **SpoolerYield** to allow the MAPI spooler to accomplish any necessary processing.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ff339-117">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ff339-117">Notes to callers</span></span>

<span data-ttu-id="ff339-118">执行可以暂停的冗长操作时，请调用 **SpoolerYield。**</span><span class="sxs-lookup"><span data-stu-id="ff339-118">Call **SpoolerYield** when you are performing lengthy operations that can be paused.</span></span> <span data-ttu-id="ff339-119">这允许前台应用程序在长时间操作（如通过繁忙网络传递至大型收件人列表）期间运行。</span><span class="sxs-lookup"><span data-stu-id="ff339-119">This allows foreground applications to run during a long operation, such as delivery to a large recipient list across a busy network.</span></span> 
  
<span data-ttu-id="ff339-120">如果 **SpoolerYield** 返回 MAPI_W_CANCEL_MESSAGE，则 MAPI 后台处理程序已确定不再发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="ff339-120">If **SpoolerYield** returns with MAPI_W_CANCEL_MESSAGE, the MAPI spooler has determined that the message should no longer be sent.</span></span> <span data-ttu-id="ff339-121">如果MAPI_E_USER_CANCEL，请返回到调用过程并退出。</span><span class="sxs-lookup"><span data-stu-id="ff339-121">Return MAPI_E_USER_CANCEL to your calling process and exit, if possible.</span></span> 
  
<span data-ttu-id="ff339-122">有关向 MAPI 后台处理程序提供收益的信息，请参阅与 [MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)。</span><span class="sxs-lookup"><span data-stu-id="ff339-122">For more information about yielding to the MAPI spooler, see [Interacting with the MAPI Spooler](interacting-with-the-mapi-spooler.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff339-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff339-123">See also</span></span>



[<span data-ttu-id="ff339-124">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ff339-124">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

