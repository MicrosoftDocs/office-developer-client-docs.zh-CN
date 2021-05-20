---
title: 表单状态
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dfc9fbf1-90d4-4756-92d9-032ac56a9c50
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 61d20ff7010151a82c53cafc69270e6925796a5c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429164"
---
# <a name="form-states"></a><span data-ttu-id="4f2bf-103">表单状态</span><span class="sxs-lookup"><span data-stu-id="4f2bf-103">Form states</span></span>

<span data-ttu-id="4f2bf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f2bf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4f2bf-105">Form 对象可能位于五个不同的状态之一，具体取决于已调用的方法以及执行这些方法时是否发生了任何错误。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-105">Form objects can be in one of five distinct states, depending on what methods have been called in them and whether any errors have occurred in performing those methods.</span></span> <span data-ttu-id="4f2bf-106">这些状态在下列主题中进行了介绍：</span><span class="sxs-lookup"><span data-stu-id="4f2bf-106">The states are described in the following topics:</span></span>
  
- [<span data-ttu-id="4f2bf-107">未初始化状态</span><span class="sxs-lookup"><span data-stu-id="4f2bf-107">Uninitialized State</span></span>](uninitialized-state.md)
    
- [<span data-ttu-id="4f2bf-108">正常状态</span><span class="sxs-lookup"><span data-stu-id="4f2bf-108">Normal State</span></span>](normal-state.md)
    
- [<span data-ttu-id="4f2bf-109">NoScribble 状态</span><span class="sxs-lookup"><span data-stu-id="4f2bf-109">NoScribble State</span></span>](noscribble-state.md)
    
- [<span data-ttu-id="4f2bf-110">HandsOffAfterSave 状态</span><span class="sxs-lookup"><span data-stu-id="4f2bf-110">HandsOffAfterSave State</span></span>](handsoffaftersave-state.md)
    
- [<span data-ttu-id="4f2bf-111">HandsOffFromNormal 状态</span><span class="sxs-lookup"><span data-stu-id="4f2bf-111">HandsOffFromNormal State</span></span>](handsofffromnormal-state.md)
    
<span data-ttu-id="4f2bf-112">状态主要与表单对象中数据的状态相关。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-112">The states primarily relate to the status of the data in the form object.</span></span> <span data-ttu-id="4f2bf-113">不同的状态反映了是否需要保存数据、表单对象是否应该允许修改数据，以及保存表单数据的过程中位于什么点。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-113">The different states reflect whether the data needs to be saved, whether the form object should allow modifications to the data, and what point in the process of saving the data the form is in.</span></span> <span data-ttu-id="4f2bf-114">因此，与任何其他方法不同，表单状态和转换与表单服务器的 [IPersistMessage ： IUnknown](ipersistmessageiunknown.md) 接口方法的实现相关。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-114">As such, the form states and transitions between them have more to do with your form server's implementation of [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interface methods than any other.</span></span> <span data-ttu-id="4f2bf-115">了解这些状态对于正确实现表单服务器必须实施的 MAPI 表单接口非常有用。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-115">Knowledge of these states is very useful for proper implementation of the MAPI form interfaces that your form server must implement.</span></span> 
  
<span data-ttu-id="4f2bf-116">本节中的主题介绍各种状态，以及导致过渡到其他状态允许的操作。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-116">The topics in this section describe the various states, along with the allowed actions that cause transitions to other states.</span></span> <span data-ttu-id="4f2bf-117">不允许在主题中未列出的任何转换。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-117">Any transitions not listed in the topics are not allowed.</span></span> <span data-ttu-id="4f2bf-118">如果表单对象不允许在状态之间进行转换，则它们的行为方式不会与邮件客户端预期的方式一样，并且可能导致不可预知的客户端或表单对象行为。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-118">If your form objects make disallowed transitions between states, they will not behave in the ways that messaging clients expect and could cause unpredictable client or form object behavior.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f2bf-119">某些状态转换取决于以前状态的信息。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-119">Some state transitions depend on information from previous states.</span></span> <span data-ttu-id="4f2bf-120">您的表单服务器很可能必须在其表单对象中实现一个标志，以指示是否已更改邮件属性的值，以便以后更改状态。</span><span class="sxs-lookup"><span data-stu-id="4f2bf-120">Your form server will most likely have to implement a flag in its form objects to indicate whether the values of the message's properties have been changed to facilitate later state changes.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4f2bf-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f2bf-121">See also</span></span>

- [<span data-ttu-id="4f2bf-122">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="4f2bf-122">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

