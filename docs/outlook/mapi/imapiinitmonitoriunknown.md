---
title: 'IMAPIInitMonitor : IUnknown'
manager: lindalu
26ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIInitMonitor
api_type:
- COM
ms.assetid: ad71ea65-394d-4be2-a9da-cd23099bc2cc
description: IMAPIInitMonitor
Last modified: April 26, 2021
ms.openlocfilehash: dd17d50b04755d9d9c2a10a9b02cd821faf1f7ec
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062044"
---
# <a name="imapiinitmonitor--iunknown"></a><span data-ttu-id="5570e-103">IMAPIInitMonitor : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5570e-103">IMAPIInitMonitor : IUnknown</span></span>

<span data-ttu-id="5570e-104">**适用于：** Outlook 2013 |Outlook 2016 |Outlook 2019 年</span><span class="sxs-lookup"><span data-stu-id="5570e-104">**Applies to**: Outlook 2013 | Outlook 2016 | Outlook 2019</span></span>

<span data-ttu-id="5570e-105">有时，使用 MAPI 的应用程序可能想要知道初始化何时完成。</span><span class="sxs-lookup"><span data-stu-id="5570e-105">There are times when an application which consumes MAPI might want to know when the initialization is completed.</span></span> <span data-ttu-id="5570e-106">例如，它有多个线程，这些线程可以初始化 MAPI，或者为了响应正在初始化的 MAPI，应用程序希望执行一些工作，但不希望始终向上旋转 MAPI 堆栈。</span><span class="sxs-lookup"><span data-stu-id="5570e-106">For example, it has multiple threads which could initialize MAPI, or in response to MAPI being initialized the application would like perform some work, but does not want to always spin up the MAPI stack.</span></span> <span data-ttu-id="5570e-107">初始化监视器通过 [CreateMAPIInitializationMonitor](createmapiinitializationmonitor.md) 对象提供此功能。</span><span class="sxs-lookup"><span data-stu-id="5570e-107">The initialization monitor provides this functionality through a [CreateMAPIInitializationMonitor](createmapiinitializationmonitor.md) object.</span></span>

| <span data-ttu-id="5570e-108">快速信息</span><span class="sxs-lookup"><span data-stu-id="5570e-108">quick info</span></span> | <span data-ttu-id="5570e-109">result</span><span class="sxs-lookup"><span data-stu-id="5570e-109">result</span></span> |
|:-----|:-----|
|<span data-ttu-id="5570e-110">继承自：</span><span class="sxs-lookup"><span data-stu-id="5570e-110">Inherits from:</span></span>  <br/> |<span data-ttu-id="5570e-111">IUnknown</span><span class="sxs-lookup"><span data-stu-id="5570e-111">IUnknown</span></span>  <br/> |
|<span data-ttu-id="5570e-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="5570e-112">Implemented by:</span></span>  <br/> | <span data-ttu-id="5570e-113">OLMAPI32.DLL</span><span class="sxs-lookup"><span data-stu-id="5570e-113">OLMAPI32.DLL</span></span> <br/> |
|<span data-ttu-id="5570e-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="5570e-114">Called by:</span></span>  <br/> |<span data-ttu-id="5570e-115">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="5570e-115">Client applications</span></span>  <br/> |
|<span data-ttu-id="5570e-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="5570e-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="5570e-117">IID_IMAPIInitMonitor</span><span class="sxs-lookup"><span data-stu-id="5570e-117">IID_IMAPIInitMonitor</span></span>  <br/> |

## <a name="vtable-order"></a><span data-ttu-id="5570e-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="5570e-118">Vtable order</span></span>

| <span data-ttu-id="5570e-119">function</span><span class="sxs-lookup"><span data-stu-id="5570e-119">function</span></span> | <span data-ttu-id="5570e-120">说明</span><span class="sxs-lookup"><span data-stu-id="5570e-120">description</span></span> |
|:-----|:-----|
|[<span data-ttu-id="5570e-121">IMAPIInitMonitor::IsInitialized</span><span class="sxs-lookup"><span data-stu-id="5570e-121">IMAPIInitMonitor::IsInitialized</span></span>](imapiinitmonitor-isinitialized.md) <br/> |<span data-ttu-id="5570e-122">返回 MAPI 初始化的当前状态。</span><span class="sxs-lookup"><span data-stu-id="5570e-122">Returns the current state of MAPI initialization.</span></span>  <br/> |
|[<span data-ttu-id="5570e-123">IMAPIInitMonitor::Wait</span><span class="sxs-lookup"><span data-stu-id="5570e-123">IMAPIInitMonitor::Wait</span></span>](imapiinitmonitor-wait.md) <br/> |<span data-ttu-id="5570e-124">在此线程上启动 BLOCKING 调用，该调用将在指定的毫秒数已过或 MAPI 已初始化时返回。</span><span class="sxs-lookup"><span data-stu-id="5570e-124">Initiates a BLOCKING call on this thread, which will return either when the specified number of milliseconds have elapsed or MAPI has been initialized.</span></span>  <span data-ttu-id="5570e-125">INFINITE 可用于无限等待。</span><span class="sxs-lookup"><span data-stu-id="5570e-125">INFINITE can be used to for an infinite wait.</span></span>  <br/> |
|[<span data-ttu-id="5570e-126">IMAPIInitMonitor::BeginWait</span><span class="sxs-lookup"><span data-stu-id="5570e-126">IMAPIInitMonitor::BeginWait</span></span>](imapiinitmonitor-beginwait.md) <br/> |<span data-ttu-id="5570e-127">开始等待 MAPI 初始化或经过的指定毫秒数。</span><span class="sxs-lookup"><span data-stu-id="5570e-127">Start a wait for MAPI initialization or the specified number of milliseconds to elapse.</span></span> <span data-ttu-id="5570e-128">这将返回 IMAPIWaitResult 接口，该接口应调用"End"，以便开始等待。</span><span class="sxs-lookup"><span data-stu-id="5570e-128">This return an IMAPIWaitResult interface which should have “End” called in order begin the wait.</span></span>  <span data-ttu-id="5570e-129">这允许调用方控制我们在等待时被阻止的线程。</span><span class="sxs-lookup"><span data-stu-id="5570e-129">This allows the caller to control which thread is blocked while we are waiting.</span></span> <br/> |
