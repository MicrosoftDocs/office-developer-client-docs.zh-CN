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
ms.openlocfilehash: d537184f427b2ef240dd2a9a59ab2f624f8f75d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409564"
---
# <a name="imapiadvisesink--iunknown"></a><span data-ttu-id="307c0-103">IMAPIAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="307c0-103">IMAPIAdviseSink : IUnknown</span></span>

  
  
<span data-ttu-id="307c0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="307c0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="307c0-105">实现用于处理通知的建议接收器对象。</span><span class="sxs-lookup"><span data-stu-id="307c0-105">Implements an advise sink object for handling notification.</span></span> <span data-ttu-id="307c0-106">指向通知接收对象的指针在调用服务提供商的 **Advise** 方法（用于注册通知的机制）时传递。</span><span class="sxs-lookup"><span data-stu-id="307c0-106">A pointer to an advise sink object is passed in a call to a service provider's **Advise** method, the mechanism used to register for notification.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="307c0-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="307c0-107">Header file:</span></span>  <br/> |<span data-ttu-id="307c0-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="307c0-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="307c0-109">公开者：</span><span class="sxs-lookup"><span data-stu-id="307c0-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="307c0-110">建议接收对象</span><span class="sxs-lookup"><span data-stu-id="307c0-110">Advise sink objects</span></span>  <br/> |
|<span data-ttu-id="307c0-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="307c0-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="307c0-112">客户端应用程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="307c0-112">Client applications and MAPI</span></span>  <br/> |
|<span data-ttu-id="307c0-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="307c0-113">Called by:</span></span>  <br/> |<span data-ttu-id="307c0-114">服务提供程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="307c0-114">Service providers and MAPI</span></span>  <br/> |
|<span data-ttu-id="307c0-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="307c0-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="307c0-116">IID_IMAPIAdviseSink</span><span class="sxs-lookup"><span data-stu-id="307c0-116">IID_IMAPIAdviseSink</span></span>  <br/> |
|<span data-ttu-id="307c0-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="307c0-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="307c0-118">LPMAPIADVISESINK</span><span class="sxs-lookup"><span data-stu-id="307c0-118">LPMAPIADVISESINK</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="307c0-119">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="307c0-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="307c0-120">OnNotify</span><span class="sxs-lookup"><span data-stu-id="307c0-120">OnNotify</span></span>](imapiadvisesink-onnotify.md) <br/> |<span data-ttu-id="307c0-121">通过执行一个或多个任务来响应通知。</span><span class="sxs-lookup"><span data-stu-id="307c0-121">Responds to a notification by performing one or more tasks.</span></span> <span data-ttu-id="307c0-122">执行的任务取决于事件的类型和生成通知的对象。</span><span class="sxs-lookup"><span data-stu-id="307c0-122">The tasks performed depend on the type of event and the object that generates the notification.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="307c0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="307c0-123">See also</span></span>



[<span data-ttu-id="307c0-124">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="307c0-124">MAPI Interfaces</span></span>](mapi-interfaces.md)

