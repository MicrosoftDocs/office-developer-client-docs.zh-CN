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
ms.openlocfilehash: 4d46152136f3806c79f0dd454ed9fd41fc845721
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405589"
---
# <a name="imapisync--iunknown"></a><span data-ttu-id="08f2e-103">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08f2e-103">IMAPISync : IUnknown</span></span>

  
  
<span data-ttu-id="08f2e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08f2e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08f2e-105">提供用于同步电子邮件而不是使用传输 API 的机制。</span><span class="sxs-lookup"><span data-stu-id="08f2e-105">Provides a mechanism for synchronizing email instead of using the Transport API.</span></span> <span data-ttu-id="08f2e-106">此接口在 store 对象上公开。</span><span class="sxs-lookup"><span data-stu-id="08f2e-106">This interface is exposed on a store object.</span></span> <span data-ttu-id="08f2e-107">通过使用此接口和[IMAPISyncProgressCallback: IUnknown](imapisyncprogresscallbackiunknown.md), 传输提供程序可以提供比 Microsoft Outlook 中的 "发送/接收" 对话框中显示的内容更好的进度和错误消息。</span><span class="sxs-lookup"><span data-stu-id="08f2e-107">By using this interface and [IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md), a transport provider can provide better progress and error messages than those that appear in the Send/Receive dialog in Microsoft Outlook.</span></span>
  
<span data-ttu-id="08f2e-108">发件箱仍在默认存储中。</span><span class="sxs-lookup"><span data-stu-id="08f2e-108">The outbox is still in the default store.</span></span> <span data-ttu-id="08f2e-109">Outlook 将继续使用传输 api 发送邮件, 因为传出邮件不能位于外部存储中。</span><span class="sxs-lookup"><span data-stu-id="08f2e-109">Outlook will continue to use the Transport APIs to send mail because the outgoing message cannot be in the external store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="08f2e-110">公开者:</span><span class="sxs-lookup"><span data-stu-id="08f2e-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="08f2e-111">存储和传输提供程序</span><span class="sxs-lookup"><span data-stu-id="08f2e-111">Store and transport providers</span></span>  <br/> |
|<span data-ttu-id="08f2e-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="08f2e-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="08f2e-113">Outlook</span><span class="sxs-lookup"><span data-stu-id="08f2e-113">Outlook</span></span>  <br/> |
|<span data-ttu-id="08f2e-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="08f2e-114">Called by:</span></span>  <br/> |<span data-ttu-id="08f2e-115">存储和传输提供程序</span><span class="sxs-lookup"><span data-stu-id="08f2e-115">Store and Transport providers</span></span>  <br/> |
|<span data-ttu-id="08f2e-116">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="08f2e-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="08f2e-117">IID_IMAPISync</span><span class="sxs-lookup"><span data-stu-id="08f2e-117">IID_IMAPISync</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="08f2e-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="08f2e-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="08f2e-119">SynchronizeInBackground</span><span class="sxs-lookup"><span data-stu-id="08f2e-119">SynchronizeInBackground</span></span>](imapisyncsynchronizeinbackground.md) <br/> |<span data-ttu-id="08f2e-120">由邮件存储提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="08f2e-120">Implemented by message store providers.</span></span> <span data-ttu-id="08f2e-121">此方法由 outlook 2010 和 outlook 2013 调用以启动同步。</span><span class="sxs-lookup"><span data-stu-id="08f2e-121">This method is called by Outlook 2010 and Outlook 2013 to start synchronization.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="08f2e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08f2e-122">See also</span></span>



[<span data-ttu-id="08f2e-123">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08f2e-123">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)


[<span data-ttu-id="08f2e-124">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="08f2e-124">MAPI Interfaces</span></span>](mapi-interfaces.md)

