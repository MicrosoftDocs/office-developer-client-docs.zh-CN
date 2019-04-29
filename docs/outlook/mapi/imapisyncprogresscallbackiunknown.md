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
ms.openlocfilehash: 54f61eb1bf111601e8b2c889b0d2890d0c10d63b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418335"
---
# <a name="imapisyncprogresscallback--iunknown"></a><span data-ttu-id="21003-103">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="21003-103">IMAPISyncProgressCallback : IUnknown</span></span>

  
  
<span data-ttu-id="21003-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="21003-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="21003-105">在调用[IMAPISync: SynchronizeInBackground](imapisyncsynchronizeinbackground.md)过程中, 会将存储提供程序作为字段传递给 MAPISIB 结构。</span><span class="sxs-lookup"><span data-stu-id="21003-105">Passes the store provider as a field on the MAPISIB structure during a call to [IMAPISync : SynchronizeInBackground](imapisyncsynchronizeinbackground.md).</span></span> <span data-ttu-id="21003-106">存储提供程序使用此接口向 Microsoft Outlook 提供有关同步状态的反馈。</span><span class="sxs-lookup"><span data-stu-id="21003-106">The store provider uses this interface to provide feedback to Microsoft Outlook about the status of the synchronization.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="21003-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="21003-107">Header file:</span></span>  <br/> ||
|<span data-ttu-id="21003-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="21003-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="21003-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="21003-109">Outlook</span></span>  <br/> |
|<span data-ttu-id="21003-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="21003-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="21003-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="21003-111">Outlook</span></span>  <br/> |
|<span data-ttu-id="21003-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="21003-112">Called by:</span></span>  <br/> |<span data-ttu-id="21003-113">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="21003-113">Store providers</span></span>  <br/> |
|<span data-ttu-id="21003-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="21003-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="21003-115">IID_IMAPISyncProgressCallback</span><span class="sxs-lookup"><span data-stu-id="21003-115">IID_IMAPISyncProgressCallback</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="21003-116">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="21003-116">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="21003-117">Progress</span><span class="sxs-lookup"><span data-stu-id="21003-117">Progress</span></span>](imapisyncprogresscallback-progress.md) <br/> |<span data-ttu-id="21003-118">存储提供程序定期调用此函数以更新 "发送/接收" 对话框中的状态。</span><span class="sxs-lookup"><span data-stu-id="21003-118">The store provider periodically calls this function to update the status in the Send/Receive dialog.</span></span>  <br/> |
|[<span data-ttu-id="21003-119">错误</span><span class="sxs-lookup"><span data-stu-id="21003-119">Error</span></span>](imapisyncprogresscallback-error.md) <br/> |<span data-ttu-id="21003-120">如果在同步过程中遇到错误, 则存储提供程序将调用此函数, 以提供在 "发送/接收" 对话框中显示的详细信息。</span><span class="sxs-lookup"><span data-stu-id="21003-120">If errors are encountered during synchronization, the store provider calls this function to provide details that are displayed in the Send/Receive dialog.</span></span>  <br/> |
|[<span data-ttu-id="21003-121">完成</span><span class="sxs-lookup"><span data-stu-id="21003-121">Done</span></span>](imapisyncprogresscallback-done.md) <br/> |<span data-ttu-id="21003-122">存储提供程序调用此函数来通知 Outlook 同步已完成。</span><span class="sxs-lookup"><span data-stu-id="21003-122">The store provider calls this function to inform Outlook that synchronization has completed.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="21003-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21003-123">See also</span></span>



[<span data-ttu-id="21003-124">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="21003-124">IMAPISync : IUnknown</span></span>](imapisynciunknown.md)


[<span data-ttu-id="21003-125">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="21003-125">MAPI Interfaces</span></span>](mapi-interfaces.md)

