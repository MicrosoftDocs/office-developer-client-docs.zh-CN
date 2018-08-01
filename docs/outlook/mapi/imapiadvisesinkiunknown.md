---
title: IMAPIAdviseSink IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIAdviseSink
api_type:
- COM
ms.assetid: f598fc57-75d3-473b-8eb0-9d8a3b92e9f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c6e352288f0bf5b0a3f284441bffc522bf00b9f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775301"
---
# <a name="imapiadvisesink--iunknown"></a><span data-ttu-id="8a7f0-103">IMAPIAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8a7f0-103">IMAPIAdviseSink : IUnknown</span></span>

  
  
<span data-ttu-id="8a7f0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8a7f0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8a7f0-105">实现用于处理通知 advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="8a7f0-105">Implements an advise sink object for handling notification.</span></span> <span data-ttu-id="8a7f0-106">指向 advise 接收器对象的指针传递给服务提供商的**Advise**方法，用于注册通知的机制呼叫中。</span><span class="sxs-lookup"><span data-stu-id="8a7f0-106">A pointer to an advise sink object is passed in a call to a service provider's **Advise** method, the mechanism used to register for notification.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8a7f0-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="8a7f0-107">Header file:</span></span>  <br/> |<span data-ttu-id="8a7f0-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8a7f0-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="8a7f0-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="8a7f0-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="8a7f0-110">建议接收器对象</span><span class="sxs-lookup"><span data-stu-id="8a7f0-110">Advise sink objects</span></span>  <br/> |
|<span data-ttu-id="8a7f0-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="8a7f0-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="8a7f0-112">客户端应用程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="8a7f0-112">Client applications and MAPI</span></span>  <br/> |
|<span data-ttu-id="8a7f0-113">调用：</span><span class="sxs-lookup"><span data-stu-id="8a7f0-113">Called by:</span></span>  <br/> |<span data-ttu-id="8a7f0-114">服务提供商和 MAPI</span><span class="sxs-lookup"><span data-stu-id="8a7f0-114">Service providers and MAPI</span></span>  <br/> |
|<span data-ttu-id="8a7f0-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="8a7f0-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="8a7f0-116">IID_IMAPIAdviseSink</span><span class="sxs-lookup"><span data-stu-id="8a7f0-116">IID_IMAPIAdviseSink</span></span>  <br/> |
|<span data-ttu-id="8a7f0-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="8a7f0-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="8a7f0-118">LPMAPIADVISESINK</span><span class="sxs-lookup"><span data-stu-id="8a7f0-118">LPMAPIADVISESINK</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="8a7f0-119">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="8a7f0-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="8a7f0-120">OnNotify</span><span class="sxs-lookup"><span data-stu-id="8a7f0-120">OnNotify</span></span>](imapiadvisesink-onnotify.md) <br/> |<span data-ttu-id="8a7f0-121">通过执行一个或多个任务响应通知。</span><span class="sxs-lookup"><span data-stu-id="8a7f0-121">Responds to a notification by performing one or more tasks.</span></span> <span data-ttu-id="8a7f0-122">执行的任务取决于事件以及生成通知的对象类型。</span><span class="sxs-lookup"><span data-stu-id="8a7f0-122">The tasks performed depend on the type of event and the object that generates the notification.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8a7f0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a7f0-123">See also</span></span>



[<span data-ttu-id="8a7f0-124">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="8a7f0-124">MAPI Interfaces</span></span>](mapi-interfaces.md)

