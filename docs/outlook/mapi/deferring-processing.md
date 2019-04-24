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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336930"
---
# <a name="deferring-processing"></a><span data-ttu-id="ea412-103">延迟处理</span><span class="sxs-lookup"><span data-stu-id="ea412-103">Deferring Processing</span></span>

  
  
<span data-ttu-id="ea412-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ea412-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ea412-105">尽可能将 MAPI_DEFERRED_ERRORS 标志传递给方法调用。</span><span class="sxs-lookup"><span data-stu-id="ea412-105">Pass the MAPI_DEFERRED_ERRORS flag to method calls as much as possible.</span></span> <span data-ttu-id="ea412-106">许多 MAPI 方法调用已经过优化, 可接受此标志, 从而导致提供程序推迟请求的任务, 直到可以同时执行多个任务, 或者您也可以等待结果不再执行。</span><span class="sxs-lookup"><span data-stu-id="ea412-106">Many of the MAPI method calls have been optimized to accept this flag, causing the provider to either postpone the requested task until multiple tasks can be performed at once or you can wait no longer for the results.</span></span>
  
<span data-ttu-id="ea412-107">例如, 如果将 MAPI_DEFERRED_ERRORS 传递给[IMsgStore:: OpenEntry](imsgstore-openentry.md)打开文件夹, 则可以延迟打开文件夹和可能的远程呼叫, 直到您执行另一个调用 (如调用文件夹的**GetHierarchyTable** ) 或**GetProps**方法。</span><span class="sxs-lookup"><span data-stu-id="ea412-107">For example, if you pass MAPI_DEFERRED_ERRORS to [IMsgStore::OpenEntry](imsgstore-openentry.md) to open a folder, the opening of the folder and a possible remote call can be postponed until you make another call such as a call to the folder's **GetHierarchyTable** or **GetProps** methods.</span></span> <span data-ttu-id="ea412-108">**GetHierarchyTable**和**GetProps**都需要从服务提供商 (必须立即执行的任务) 返回数据。</span><span class="sxs-lookup"><span data-stu-id="ea412-108">Both **GetHierarchyTable** and **GetProps** require the return of data from the service provider, a task that must be performed immediately.</span></span> 
  
<span data-ttu-id="ea412-109">推迟处理的另一种方法就是不发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="ea412-109">Another way to defer processing is simply not to make a call.</span></span> <span data-ttu-id="ea412-110">通过了解用户以及当用户可以感知资源或处理时间时, 您可以确定何时有必要进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="ea412-110">By being aware of the user and when the user can perceive a drain on resources or processing time, you can determine when it makes sense to make calls.</span></span> <span data-ttu-id="ea412-111">在用户不会注意到或根本不会注意到的情况时, 可以通过调用来提高性能。</span><span class="sxs-lookup"><span data-stu-id="ea412-111">There is an opportunity to improve performance by making calls either at a time when the user will not notice or by not making them at all.</span></span>
  
<span data-ttu-id="ea412-112">例如, 如果要从正在移动大量邮件的邮件存储中每秒接收多个通知, 请考虑这样一种情况。</span><span class="sxs-lookup"><span data-stu-id="ea412-112">For example, consider the situation when you are receiving more than one notification per second from a message store that is moving a great number of messages.</span></span> <span data-ttu-id="ea412-113">将显示一个进度指示器, 以指示操作完成的百分比。</span><span class="sxs-lookup"><span data-stu-id="ea412-113">A progress indicator is displayed to indicate the percentage of the operation's completion.</span></span> <span data-ttu-id="ea412-114">用户通常无法感知此操作在几秒钟后才会变慢。</span><span class="sxs-lookup"><span data-stu-id="ea412-114">Users typically will not perceive this operation to be slow until a few seconds have passed.</span></span> <span data-ttu-id="ea412-115">因此, 如果要更新进度指示器, 则在启动移动操作至少四秒后才进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="ea412-115">Therefore, if you are updating the progress indicator, do not make any changes until at least four seconds after the initiation of the move operation.</span></span> <span data-ttu-id="ea412-116">这将节省操作速度较快时的常见情况, 并在操作缓慢时及时通知用户。</span><span class="sxs-lookup"><span data-stu-id="ea412-116">This will save time in the common cases when the operation is fast and inform users in a timely manner when the operation is slow.</span></span>
  

