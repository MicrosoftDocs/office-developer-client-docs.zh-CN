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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327515"
---
# <a name="form-states"></a><span data-ttu-id="b6ee0-103">表单状态</span><span class="sxs-lookup"><span data-stu-id="b6ee0-103">Form states</span></span>

<span data-ttu-id="b6ee0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6ee0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6ee0-105">表单对象可以是五个不同状态之一, 具体取决于在其中调用的方法以及在执行这些方法时是否发生了错误。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-105">Form objects can be in one of five distinct states, depending on what methods have been called in them and whether any errors have occurred in performing those methods.</span></span> <span data-ttu-id="b6ee0-106">以下主题介绍了这些状态:</span><span class="sxs-lookup"><span data-stu-id="b6ee0-106">The states are described in the following topics:</span></span>
  
- [<span data-ttu-id="b6ee0-107">未初始化状态</span><span class="sxs-lookup"><span data-stu-id="b6ee0-107">Uninitialized State</span></span>](uninitialized-state.md)
    
- [<span data-ttu-id="b6ee0-108">正常状态</span><span class="sxs-lookup"><span data-stu-id="b6ee0-108">Normal State</span></span>](normal-state.md)
    
- [<span data-ttu-id="b6ee0-109">NoScribble 状态</span><span class="sxs-lookup"><span data-stu-id="b6ee0-109">NoScribble State</span></span>](noscribble-state.md)
    
- [<span data-ttu-id="b6ee0-110">HandsOffAfterSave 状态</span><span class="sxs-lookup"><span data-stu-id="b6ee0-110">HandsOffAfterSave State</span></span>](handsoffaftersave-state.md)
    
- [<span data-ttu-id="b6ee0-111">HandsOffFromNormal 状态</span><span class="sxs-lookup"><span data-stu-id="b6ee0-111">HandsOffFromNormal State</span></span>](handsofffromnormal-state.md)
    
<span data-ttu-id="b6ee0-112">这些状态主要与 form 对象中的数据的状态相关。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-112">The states primarily relate to the status of the data in the form object.</span></span> <span data-ttu-id="b6ee0-113">不同的状态反映了是否需要保存数据, 窗体对象是否应允许对数据进行修改, 以及保存该窗体的数据的过程点。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-113">The different states reflect whether the data needs to be saved, whether the form object should allow modifications to the data, and what point in the process of saving the data the form is in.</span></span> <span data-ttu-id="b6ee0-114">因此, 它们之间的表单状态和转换与您在表单服务器的 IPersistMessage 实现过程中有更多的不同之处[: IUnknown](ipersistmessageiunknown.md)接口方法。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-114">As such, the form states and transitions between them have more to do with your form server's implementation of [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interface methods than any other.</span></span> <span data-ttu-id="b6ee0-115">这些状态的知识对于正确实现表单服务器必须实现的 MAPI 表单接口非常有用。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-115">Knowledge of these states is very useful for proper implementation of the MAPI form interfaces that your form server must implement.</span></span> 
  
<span data-ttu-id="b6ee0-116">本节中的主题介绍各种状态以及导致转换为其他状态的允许的操作。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-116">The topics in this section describe the various states, along with the allowed actions that cause transitions to other states.</span></span> <span data-ttu-id="b6ee0-117">不允许主题中未列出的任何转换。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-117">Any transitions not listed in the topics are not allowed.</span></span> <span data-ttu-id="b6ee0-118">如果表单对象在状态之间禁止转换, 则它们不会以邮件传递客户端预期的方式运行, 并可能导致不可预测的客户端或表单对象行为。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-118">If your form objects make disallowed transitions between states, they will not behave in the ways that messaging clients expect and could cause unpredictable client or form object behavior.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6ee0-119">某些状态转换取决于以前状态中的信息。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-119">Some state transitions depend on information from previous states.</span></span> <span data-ttu-id="b6ee0-120">您的表单服务器很可能必须在其 form 对象中实现一个标志, 以指示是否已更改邮件属性的值以简化后续状态更改。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-120">Your form server will most likely have to implement a flag in its form objects to indicate whether the values of the message's properties have been changed to facilitate later state changes.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b6ee0-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6ee0-121">See also</span></span>

- [<span data-ttu-id="b6ee0-122">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="b6ee0-122">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

