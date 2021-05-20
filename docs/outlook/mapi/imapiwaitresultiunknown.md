---
title: 'IMAPIWaitResult : IUnknown'
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIWAITRESULT
api_type:
- COM
ms.assetid: d7157f57-709d-4e53-973b-176954e2bb73
description: IMAPIWaitResult
Last modified: April 26, 2021
ms.openlocfilehash: 67a0fffdd0ab6d4989c12568f4d89808ba5adc7a
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062037"
---
# <a name="imapiwaitresult--iunknown"></a><span data-ttu-id="ea06b-103">IMAPIWaitResult : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ea06b-103">IMAPIWaitResult : IUnknown</span></span>
  
<span data-ttu-id="ea06b-104">**适用于：** Outlook 2013 |Outlook 2016 |Outlook 2019 年</span><span class="sxs-lookup"><span data-stu-id="ea06b-104">**Applies to**: Outlook 2013 | Outlook 2016 | Outlook 2019</span></span>

<span data-ttu-id="ea06b-105">IMAPIInitMonitor 的使用者使用此接口来控制等待发生位置。</span><span class="sxs-lookup"><span data-stu-id="ea06b-105">This interface is used by consumers of IMAPIInitMonitor to control where the wait happens.</span></span> <span data-ttu-id="ea06b-106">它允许他们在一个线程上创建对象，并移动另一个线程来执行实际等待。</span><span class="sxs-lookup"><span data-stu-id="ea06b-106">It allows them create the object on one thread and move it another thread to perform the actual wait.</span></span>

## <a name="vtable-order"></a><span data-ttu-id="ea06b-107">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="ea06b-107">Vtable order</span></span>

| <span data-ttu-id="ea06b-108">function</span><span class="sxs-lookup"><span data-stu-id="ea06b-108">function</span></span> | <span data-ttu-id="ea06b-109">说明</span><span class="sxs-lookup"><span data-stu-id="ea06b-109">description</span></span> |
|:-----|:-----|
|[<span data-ttu-id="ea06b-110">HRESULT IMAPIWaitResult：：End () </span><span class="sxs-lookup"><span data-stu-id="ea06b-110">HRESULT IMAPIWaitResult::End()</span></span>](imapiwaitresult-end.md)|<span data-ttu-id="ea06b-111">调用 以在调用它的线程上启动阻止等待，该线程不需要与调用 *IMAPIInitMonitor：：BeginWait 的线程相同*。</span><span class="sxs-lookup"><span data-stu-id="ea06b-111">Called to initiate the blocking wait on the thread where it is called, which does not need to be the same thread that called *IMAPIInitMonitor::BeginWait*.</span></span>|

| <span data-ttu-id="ea06b-112">快速信息</span><span class="sxs-lookup"><span data-stu-id="ea06b-112">quick info</span></span> | <span data-ttu-id="ea06b-113">result</span><span class="sxs-lookup"><span data-stu-id="ea06b-113">result</span></span> |
|:-----|:-----|
|<span data-ttu-id="ea06b-114">继承自：</span><span class="sxs-lookup"><span data-stu-id="ea06b-114">Inherits from:</span></span>  <br/> |<span data-ttu-id="ea06b-115">IUnknown</span><span class="sxs-lookup"><span data-stu-id="ea06b-115">IUnknown</span></span>  <br/> |
|<span data-ttu-id="ea06b-116">实现者：</span><span class="sxs-lookup"><span data-stu-id="ea06b-116">Implemented by:</span></span>  <br/> |  <span data-ttu-id="ea06b-117">OLMAPI32.DLL</span><span class="sxs-lookup"><span data-stu-id="ea06b-117">OLMAPI32.DLL</span></span><br/> |
|<span data-ttu-id="ea06b-118">调用者：</span><span class="sxs-lookup"><span data-stu-id="ea06b-118">Called by:</span></span>  <br/> |<span data-ttu-id="ea06b-119">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="ea06b-119">Client applications</span></span>  <br/> |
|<span data-ttu-id="ea06b-120">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="ea06b-120">Interface identifier:</span></span>  <br/> |<span data-ttu-id="ea06b-121">IID_IMAPIWaitResult</span><span class="sxs-lookup"><span data-stu-id="ea06b-121">IID_IMAPIWaitResult</span></span>  <br/> |

## <a name="see-also"></a><span data-ttu-id="ea06b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea06b-122">See also</span></span>

[<span data-ttu-id="ea06b-123">IMAPIInitMonitor</span><span class="sxs-lookup"><span data-stu-id="ea06b-123">IMAPIInitMonitor</span></span>](imapiinitmonitoriunknown.md)

[<span data-ttu-id="ea06b-124">IMAPIInitMonitor::BeginWait</span><span class="sxs-lookup"><span data-stu-id="ea06b-124">IMAPIInitMonitor::BeginWait</span></span>](imapiinitmonitor-beginwait.md)

[<span data-ttu-id="ea06b-125">IMAPIInitMonitor : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ea06b-125">IMAPIInitMonitor : IUnknown</span></span>](imapiinitmonitoriunknown.md)

[<span data-ttu-id="ea06b-126">CreateMAPIInitializationMonitor</span><span class="sxs-lookup"><span data-stu-id="ea06b-126">CreateMAPIInitializationMonitor</span></span>](createmapiinitializationmonitor.md)
