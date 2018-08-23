---
title: 延迟处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a791b95f-56ad-493a-9ba5-fb4c7dd80e89
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2c4577a35315c9df0055e97de26dd0baf1a2b489
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580584"
---
# <a name="deferring-processing"></a><span data-ttu-id="2847f-103">延迟处理</span><span class="sxs-lookup"><span data-stu-id="2847f-103">Deferring Processing</span></span>

  
  
<span data-ttu-id="2847f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2847f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2847f-105">传递给方法调用 MAPI_DEFERRED_ERRORS 标志尽可能。</span><span class="sxs-lookup"><span data-stu-id="2847f-105">Pass the MAPI_DEFERRED_ERRORS flag to method calls as much as possible.</span></span> <span data-ttu-id="2847f-106">已优化的 MAPI 方法调用许多接受此标志，导致的提供程序，也可以同时执行多个任务或可以等待不再结果之前延迟请求的任务。</span><span class="sxs-lookup"><span data-stu-id="2847f-106">Many of the MAPI method calls have been optimized to accept this flag, causing the provider to either postpone the requested task until multiple tasks can be performed at once or you can wait no longer for the results.</span></span>
  
<span data-ttu-id="2847f-107">例如，如果 MAPI_DEFERRED_ERRORS 传递给[IMsgStore::OpenEntry](imsgstore-openentry.md)打开一个文件夹，打开的文件夹和可能的远程呼叫可以被延迟，直到您进行另一个呼叫，如调用该文件夹的**通讯**或**GetProps**方法。</span><span class="sxs-lookup"><span data-stu-id="2847f-107">For example, if you pass MAPI_DEFERRED_ERRORS to [IMsgStore::OpenEntry](imsgstore-openentry.md) to open a folder, the opening of the folder and a possible remote call can be postponed until you make another call such as a call to the folder's **GetHierarchyTable** or **GetProps** methods.</span></span> <span data-ttu-id="2847f-108">**通讯**和**GetProps**需要从服务提供商，必须立即执行的任务的数据返回。</span><span class="sxs-lookup"><span data-stu-id="2847f-108">Both **GetHierarchyTable** and **GetProps** require the return of data from the service provider, a task that must be performed immediately.</span></span> 
  
<span data-ttu-id="2847f-109">延迟处理另一种方法是只需不发起呼叫。</span><span class="sxs-lookup"><span data-stu-id="2847f-109">Another way to defer processing is simply not to make a call.</span></span> <span data-ttu-id="2847f-110">通过注意的用户和用户可以感知处理时间或资源耗尽，您可以确定时有意义发起呼叫。</span><span class="sxs-lookup"><span data-stu-id="2847f-110">By being aware of the user and when the user can perceive a drain on resources or processing time, you can determine when it makes sense to make calls.</span></span> <span data-ttu-id="2847f-111">没有机会来提高性能，通过调用可以一次用户将不注意到或根本不进行。</span><span class="sxs-lookup"><span data-stu-id="2847f-111">There is an opportunity to improve performance by making calls either at a time when the user will not notice or by not making them at all.</span></span>
  
<span data-ttu-id="2847f-112">当您从移动大量的消息的消息存储收到每秒的多个通知，例如，假设这种情况。</span><span class="sxs-lookup"><span data-stu-id="2847f-112">For example, consider the situation when you are receiving more than one notification per second from a message store that is moving a great number of messages.</span></span> <span data-ttu-id="2847f-113">显示进度指示器以指示该操作完成百分比。</span><span class="sxs-lookup"><span data-stu-id="2847f-113">A progress indicator is displayed to indicate the percentage of the operation's completion.</span></span> <span data-ttu-id="2847f-114">用户通常将不会察觉此操作会较慢，直到过去几秒钟。</span><span class="sxs-lookup"><span data-stu-id="2847f-114">Users typically will not perceive this operation to be slow until a few seconds have passed.</span></span> <span data-ttu-id="2847f-115">因此，如果您正在更新进度指示器，不要任何更改之前，至少 4 秒后移动操作的初始。</span><span class="sxs-lookup"><span data-stu-id="2847f-115">Therefore, if you are updating the progress indicator, do not make any changes until at least four seconds after the initiation of the move operation.</span></span> <span data-ttu-id="2847f-116">将 fast 操作时的常见情况节省时间并操作太慢时正在及时通知用户。</span><span class="sxs-lookup"><span data-stu-id="2847f-116">This will save time in the common cases when the operation is fast and inform users in a timely manner when the operation is slow.</span></span>
  

