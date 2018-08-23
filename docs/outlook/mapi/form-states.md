---
title: 窗体状态
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dfc9fbf1-90d4-4756-92d9-032ac56a9c50
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 195a82bfcc163ee01d2d42c71e79a8f5c9c620e5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564631"
---
# <a name="form-states"></a><span data-ttu-id="7e3cb-103">窗体状态</span><span class="sxs-lookup"><span data-stu-id="7e3cb-103">Form states</span></span>

<span data-ttu-id="7e3cb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e3cb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e3cb-105">窗体对象可以五个不同的状态，具体取决于在其中调用了哪些方法和是否任何错误发生在执行这些方法之一。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-105">Form objects can be in one of five distinct states, depending on what methods have been called in them and whether any errors have occurred in performing those methods.</span></span> <span data-ttu-id="7e3cb-106">以下主题中描述的状态：</span><span class="sxs-lookup"><span data-stu-id="7e3cb-106">The states are described in the following topics:</span></span>
  
- [<span data-ttu-id="7e3cb-107">Uninitialized 状态</span><span class="sxs-lookup"><span data-stu-id="7e3cb-107">Uninitialized State</span></span>](uninitialized-state.md)
    
- [<span data-ttu-id="7e3cb-108">Normal 状态</span><span class="sxs-lookup"><span data-stu-id="7e3cb-108">Normal State</span></span>](normal-state.md)
    
- [<span data-ttu-id="7e3cb-109">NoScribble 状态</span><span class="sxs-lookup"><span data-stu-id="7e3cb-109">NoScribble State</span></span>](noscribble-state.md)
    
- [<span data-ttu-id="7e3cb-110">HandsOffAfterSave 状态</span><span class="sxs-lookup"><span data-stu-id="7e3cb-110">HandsOffAfterSave State</span></span>](handsoffaftersave-state.md)
    
- [<span data-ttu-id="7e3cb-111">HandsOffFromNormal 状态</span><span class="sxs-lookup"><span data-stu-id="7e3cb-111">HandsOffFromNormal State</span></span>](handsofffromnormal-state.md)
    
<span data-ttu-id="7e3cb-112">状态主要与窗体对象中的数据的状态。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-112">The states primarily relate to the status of the data in the form object.</span></span> <span data-ttu-id="7e3cb-113">不同的状态反映是否需要将数据保存，是否 form 对象应允许修改数据和内容指向保存窗体处于的数据的过程。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-113">The different states reflect whether the data needs to be saved, whether the form object should allow modifications to the data, and what point in the process of saving the data the form is in.</span></span> <span data-ttu-id="7e3cb-114">因此，窗体状态和它们之间的转换有更如何处理您的窗体服务器实现[IPersistMessage: IUnknown](ipersistmessageiunknown.md)接口比其他方法。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-114">As such, the form states and transitions between them have more to do with your form server's implementation of [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interface methods than any other.</span></span> <span data-ttu-id="7e3cb-115">非常有用的 MAPI 表单接口的窗体服务器必须实现的正确实施这些状态的知识。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-115">Knowledge of these states is very useful for proper implementation of the MAPI form interfaces that your form server must implement.</span></span> 
  
<span data-ttu-id="7e3cb-116">本节中的主题介绍各种状态，以及允许导致切换到其他状态的操作。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-116">The topics in this section describe the various states, along with the allowed actions that cause transitions to other states.</span></span> <span data-ttu-id="7e3cb-117">不允许使用主题中未列出任何转换。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-117">Any transitions not listed in the topics are not allowed.</span></span> <span data-ttu-id="7e3cb-118">如果表单对象进行状态之间不允许的切换，它们将不行为消息客户端期望，并且可能会导致无法预料的客户端或窗体对象的行为方式。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-118">If your form objects make disallowed transitions between states, they will not behave in the ways that messaging clients expect and could cause unpredictable client or form object behavior.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e3cb-119">某些状态转换取决于从以前的状态信息。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-119">Some state transitions depend on information from previous states.</span></span> <span data-ttu-id="7e3cb-120">窗体服务器很可能会在其表单对象，以指示该消息的属性的值是否已被更改以加快更高版本的状态更改中实现一个标志。</span><span class="sxs-lookup"><span data-stu-id="7e3cb-120">Your form server will most likely have to implement a flag in its form objects to indicate whether the values of the message's properties have been changed to facilitate later state changes.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7e3cb-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e3cb-121">See also</span></span>

- [<span data-ttu-id="7e3cb-122">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="7e3cb-122">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

