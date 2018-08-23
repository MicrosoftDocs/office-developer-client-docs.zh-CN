---
title: IMAPISync IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISync
api_type:
- COM
ms.assetid: c14d1012-f3d4-47eb-8a90-3160331f94e8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8e2e7a3f9279485d862fac5bb6413b3d3eb1343e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589082"
---
# <a name="imapisync--iunknown"></a><span data-ttu-id="c18b2-103">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c18b2-103">IMAPISync : IUnknown</span></span>

  
  
<span data-ttu-id="c18b2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c18b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c18b2-105">提供一种机制，同步电子邮件，而不是使用传输 API。</span><span class="sxs-lookup"><span data-stu-id="c18b2-105">Provides a mechanism for synchronizing email instead of using the Transport API.</span></span> <span data-ttu-id="c18b2-106">此接口将公开的存储对象。</span><span class="sxs-lookup"><span data-stu-id="c18b2-106">This interface is exposed on a store object.</span></span> <span data-ttu-id="c18b2-107">使用此接口和[IMAPISyncProgressCallback: IUnknown](imapisyncprogresscallbackiunknown.md)、 传输提供程序可以提供更好的进度和比的错误消息的显示在 Microsoft Outlook 中的发送/接收对话框。</span><span class="sxs-lookup"><span data-stu-id="c18b2-107">By using this interface and [IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md), a transport provider can provide better progress and error messages than those that appear in the Send/Receive dialog in Microsoft Outlook.</span></span>
  
<span data-ttu-id="c18b2-108">发件箱仍位于默认存储。</span><span class="sxs-lookup"><span data-stu-id="c18b2-108">The outbox is still in the default store.</span></span> <span data-ttu-id="c18b2-109">Outlook 将继续使用 Transport Api 来发送邮件，因为传出消息不能在外部存储中。</span><span class="sxs-lookup"><span data-stu-id="c18b2-109">Outlook will continue to use the Transport APIs to send mail because the outgoing message cannot be in the external store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c18b2-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="c18b2-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="c18b2-111">存储和传输提供程序</span><span class="sxs-lookup"><span data-stu-id="c18b2-111">Store and transport providers</span></span>  <br/> |
|<span data-ttu-id="c18b2-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="c18b2-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="c18b2-113">Outlook</span><span class="sxs-lookup"><span data-stu-id="c18b2-113">Outlook</span></span>  <br/> |
|<span data-ttu-id="c18b2-114">调用：</span><span class="sxs-lookup"><span data-stu-id="c18b2-114">Called by:</span></span>  <br/> |<span data-ttu-id="c18b2-115">存储和传输提供程序</span><span class="sxs-lookup"><span data-stu-id="c18b2-115">Store and Transport providers</span></span>  <br/> |
|<span data-ttu-id="c18b2-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="c18b2-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c18b2-117">IID_IMAPISync</span><span class="sxs-lookup"><span data-stu-id="c18b2-117">IID_IMAPISync</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="c18b2-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="c18b2-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="c18b2-119">SynchronizeInBackground</span><span class="sxs-lookup"><span data-stu-id="c18b2-119">SynchronizeInBackground</span></span>](imapisyncsynchronizeinbackground.md) <br/> |<span data-ttu-id="c18b2-120">由消息存储提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="c18b2-120">Implemented by message store providers.</span></span> <span data-ttu-id="c18b2-121">Outlook 2010 和 Outlook 2013 启动同步调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c18b2-121">This method is called by Outlook 2010 and Outlook 2013 to start synchronization.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c18b2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c18b2-122">See also</span></span>



[<span data-ttu-id="c18b2-123">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c18b2-123">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)


[<span data-ttu-id="c18b2-124">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="c18b2-124">MAPI Interfaces</span></span>](mapi-interfaces.md)

