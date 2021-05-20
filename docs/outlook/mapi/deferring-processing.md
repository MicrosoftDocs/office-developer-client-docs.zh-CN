---
title: 延迟处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a791b95f-56ad-493a-9ba5-fb4c7dd80e89
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2d3fbf8f7a725f121579066001715fb0bc6beba0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430929"
---
# <a name="deferring-processing"></a><span data-ttu-id="98741-103">延迟处理</span><span class="sxs-lookup"><span data-stu-id="98741-103">Deferring Processing</span></span>

  
  
<span data-ttu-id="98741-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="98741-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="98741-105">将MAPI_DEFERRED_ERRORS标志传递给方法调用。</span><span class="sxs-lookup"><span data-stu-id="98741-105">Pass the MAPI_DEFERRED_ERRORS flag to method calls as much as possible.</span></span> <span data-ttu-id="98741-106">许多 MAPI 方法调用已优化为接受此标志，导致提供程序要么将请求的任务推迟，直到可以同时执行多个任务，要么可以不再等待结果。</span><span class="sxs-lookup"><span data-stu-id="98741-106">Many of the MAPI method calls have been optimized to accept this flag, causing the provider to either postpone the requested task until multiple tasks can be performed at once or you can wait no longer for the results.</span></span>
  
<span data-ttu-id="98741-107">例如，如果将 MAPI_DEFERRED_ERRORS 传递到 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 以打开文件夹，则打开文件夹和可能的远程调用可以延迟，直到您进行其他调用（如调用文件夹的 **GetHierarchyTable** 或 **GetProps** 方法）。</span><span class="sxs-lookup"><span data-stu-id="98741-107">For example, if you pass MAPI_DEFERRED_ERRORS to [IMsgStore::OpenEntry](imsgstore-openentry.md) to open a folder, the opening of the folder and a possible remote call can be postponed until you make another call such as a call to the folder's **GetHierarchyTable** or **GetProps** methods.</span></span> <span data-ttu-id="98741-108">**GetHierarchyTable** 和 **GetProps** 都要求从服务提供商返回数据，这是一个必须立即执行的任务。</span><span class="sxs-lookup"><span data-stu-id="98741-108">Both **GetHierarchyTable** and **GetProps** require the return of data from the service provider, a task that must be performed immediately.</span></span> 
  
<span data-ttu-id="98741-109">延迟处理的另一种方式是直接不进行调用。</span><span class="sxs-lookup"><span data-stu-id="98741-109">Another way to defer processing is simply not to make a call.</span></span> <span data-ttu-id="98741-110">通过了解用户以及用户何时可以感知到资源消耗或处理时间，你可以确定何时进行调用有意义。</span><span class="sxs-lookup"><span data-stu-id="98741-110">By being aware of the user and when the user can perceive a drain on resources or processing time, you can determine when it makes sense to make calls.</span></span> <span data-ttu-id="98741-111">有机会在用户不会注意到或完全不发出呼叫时发出调用来提高性能。</span><span class="sxs-lookup"><span data-stu-id="98741-111">There is an opportunity to improve performance by making calls either at a time when the user will not notice or by not making them at all.</span></span>
  
<span data-ttu-id="98741-112">例如，在每秒从移动大量邮件的邮件存储中接收多个通知时，请考虑这种情况。</span><span class="sxs-lookup"><span data-stu-id="98741-112">For example, consider the situation when you are receiving more than one notification per second from a message store that is moving a great number of messages.</span></span> <span data-ttu-id="98741-113">将显示进度指示器以指示操作完成百分比。</span><span class="sxs-lookup"><span data-stu-id="98741-113">A progress indicator is displayed to indicate the percentage of the operation's completion.</span></span> <span data-ttu-id="98741-114">在几秒钟过去之前，用户通常不会认为此操作很慢。</span><span class="sxs-lookup"><span data-stu-id="98741-114">Users typically will not perceive this operation to be slow until a few seconds have passed.</span></span> <span data-ttu-id="98741-115">因此，如果要更新进度指示器，在启动移动操作至少四秒钟后不要进行更改。</span><span class="sxs-lookup"><span data-stu-id="98741-115">Therefore, if you are updating the progress indicator, do not make any changes until at least four seconds after the initiation of the move operation.</span></span> <span data-ttu-id="98741-116">这将在操作速度较快的常见情况下节省时间，并通知用户操作缓慢时及时通知用户。</span><span class="sxs-lookup"><span data-stu-id="98741-116">This will save time in the common cases when the operation is fast and inform users in a timely manner when the operation is slow.</span></span>
  

