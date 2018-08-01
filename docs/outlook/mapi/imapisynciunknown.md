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
ms.openlocfilehash: fb7a8ea39d6e7b1d7df1560658ceb67a79d39d92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775676"
---
# <a name="imapisync--iunknown"></a><span data-ttu-id="52fc0-103">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="52fc0-103">IMAPISync : IUnknown</span></span>

  
  
<span data-ttu-id="52fc0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="52fc0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="52fc0-105">提供一种机制，同步电子邮件，而不是使用传输 API。</span><span class="sxs-lookup"><span data-stu-id="52fc0-105">Provides a mechanism for synchronizing email instead of using the Transport API.</span></span> <span data-ttu-id="52fc0-106">此接口将公开的存储对象。</span><span class="sxs-lookup"><span data-stu-id="52fc0-106">This interface is exposed on a store object.</span></span> <span data-ttu-id="52fc0-107">使用此接口和[IMAPISyncProgressCallback: IUnknown](imapisyncprogresscallbackiunknown.md)、 传输提供程序可以提供更好的进度和比的错误消息的显示在 Microsoft Outlook 中的发送/接收对话框。</span><span class="sxs-lookup"><span data-stu-id="52fc0-107">By using this interface and [IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md), a transport provider can provide better progress and error messages than those that appear in the Send/Receive dialog in Microsoft Outlook.</span></span>
  
<span data-ttu-id="52fc0-108">发件箱仍位于默认存储。</span><span class="sxs-lookup"><span data-stu-id="52fc0-108">The outbox is still in the default store.</span></span> <span data-ttu-id="52fc0-109">Outlook 将继续使用 Transport Api 来发送邮件，因为传出消息不能在外部存储中。</span><span class="sxs-lookup"><span data-stu-id="52fc0-109">Outlook will continue to use the Transport APIs to send mail because the outgoing message cannot be in the external store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="52fc0-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="52fc0-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="52fc0-111">存储和传输提供程序</span><span class="sxs-lookup"><span data-stu-id="52fc0-111">Store and transport providers</span></span>  <br/> |
|<span data-ttu-id="52fc0-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="52fc0-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="52fc0-113">Outlook</span><span class="sxs-lookup"><span data-stu-id="52fc0-113">Outlook</span></span>  <br/> |
|<span data-ttu-id="52fc0-114">调用：</span><span class="sxs-lookup"><span data-stu-id="52fc0-114">Called by:</span></span>  <br/> |<span data-ttu-id="52fc0-115">存储和传输提供程序</span><span class="sxs-lookup"><span data-stu-id="52fc0-115">Store and Transport providers</span></span>  <br/> |
|<span data-ttu-id="52fc0-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="52fc0-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="52fc0-117">IID_IMAPISync</span><span class="sxs-lookup"><span data-stu-id="52fc0-117">IID_IMAPISync</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="52fc0-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="52fc0-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="52fc0-119">SynchronizeInBackground</span><span class="sxs-lookup"><span data-stu-id="52fc0-119">SynchronizeInBackground</span></span>](imapisyncsynchronizeinbackground.md) <br/> |<span data-ttu-id="52fc0-120">由消息存储提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="52fc0-120">Implemented by message store providers.</span></span> <span data-ttu-id="52fc0-121">Outlook 2010 和 Outlook 2013 启动同步调用此方法。</span><span class="sxs-lookup"><span data-stu-id="52fc0-121">This method is called by Outlook 2010 and Outlook 2013 to start synchronization.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="52fc0-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52fc0-122">See also</span></span>



[<span data-ttu-id="52fc0-123">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="52fc0-123">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)


[<span data-ttu-id="52fc0-124">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="52fc0-124">MAPI Interfaces</span></span>](mapi-interfaces.md)

