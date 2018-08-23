---
title: IMAPISyncProgressCallback IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISyncProgressCallback
api_type:
- COM
ms.assetid: 146b5e36-8d73-4949-9fed-1074f707423d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 33d811af0fc9e06902750075ba39bfb6ca88903f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593709"
---
# <a name="imapisyncprogresscallback--iunknown"></a><span data-ttu-id="f3176-103">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f3176-103">IMAPISyncProgressCallback : IUnknown</span></span>

  
  
<span data-ttu-id="f3176-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3176-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3176-105">传入的存储提供程序作为字段的 MAPISIB 结构到在呼叫过程中[IMAPISync: SynchronizeInBackground](imapisyncsynchronizeinbackground.md)。</span><span class="sxs-lookup"><span data-stu-id="f3176-105">Passes the store provider as a field on the MAPISIB structure during a call to [IMAPISync : SynchronizeInBackground](imapisyncsynchronizeinbackground.md).</span></span> <span data-ttu-id="f3176-106">存储提供程序使用此接口提供反馈到 Microsoft Outlook 同步的状态。</span><span class="sxs-lookup"><span data-stu-id="f3176-106">The store provider uses this interface to provide feedback to Microsoft Outlook about the status of the synchronization.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f3176-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="f3176-107">Header file:</span></span>  <br/> ||
|<span data-ttu-id="f3176-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="f3176-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="f3176-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="f3176-109">Outlook</span></span>  <br/> |
|<span data-ttu-id="f3176-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="f3176-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="f3176-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="f3176-111">Outlook</span></span>  <br/> |
|<span data-ttu-id="f3176-112">调用：</span><span class="sxs-lookup"><span data-stu-id="f3176-112">Called by:</span></span>  <br/> |<span data-ttu-id="f3176-113">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="f3176-113">Store providers</span></span>  <br/> |
|<span data-ttu-id="f3176-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="f3176-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="f3176-115">IID_IMAPISyncProgressCallback</span><span class="sxs-lookup"><span data-stu-id="f3176-115">IID_IMAPISyncProgressCallback</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="f3176-116">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="f3176-116">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="f3176-117">Progress</span><span class="sxs-lookup"><span data-stu-id="f3176-117">Progress</span></span>](imapisyncprogresscallback-progress.md) <br/> |<span data-ttu-id="f3176-118">存储提供程序定期调用此函数可更新发送/接收对话框中的状态。</span><span class="sxs-lookup"><span data-stu-id="f3176-118">The store provider periodically calls this function to update the status in the Send/Receive dialog.</span></span>  <br/> |
|[<span data-ttu-id="f3176-119">Error</span><span class="sxs-lookup"><span data-stu-id="f3176-119">Error</span></span>](imapisyncprogresscallback-error.md) <br/> |<span data-ttu-id="f3176-120">如果同步过程中遇到错误，存储提供程序调用此函数可提供发送/接收对话框中显示的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f3176-120">If errors are encountered during synchronization, the store provider calls this function to provide details that are displayed in the Send/Receive dialog.</span></span>  <br/> |
|[<span data-ttu-id="f3176-121">完成</span><span class="sxs-lookup"><span data-stu-id="f3176-121">Done</span></span>](imapisyncprogresscallback-done.md) <br/> |<span data-ttu-id="f3176-122">存储提供程序调用此函数来通知 Outlook 同步已完成。</span><span class="sxs-lookup"><span data-stu-id="f3176-122">The store provider calls this function to inform Outlook that synchronization has completed.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f3176-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3176-123">See also</span></span>



[<span data-ttu-id="f3176-124">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f3176-124">IMAPISync : IUnknown</span></span>](imapisynciunknown.md)


[<span data-ttu-id="f3176-125">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="f3176-125">MAPI Interfaces</span></span>](mapi-interfaces.md)

