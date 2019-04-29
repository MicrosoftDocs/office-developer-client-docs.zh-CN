---
title: 发送和接收表单通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a4374728-e2bc-47d9-8b03-ba09545a38d8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4ee47b51a98cf732f4e9af2a87fa1734a7250208
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431853"
---
# <a name="sending-and-receiving-form-notifications"></a><span data-ttu-id="3765a-103">发送和接收表单通知</span><span class="sxs-lookup"><span data-stu-id="3765a-103">Sending and Receiving Form Notifications</span></span>

  
  
<span data-ttu-id="3765a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3765a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3765a-105">窗体通知在 MAPI 中使用, 以促进从窗体到查看器以及从查看器到表单的通信。</span><span class="sxs-lookup"><span data-stu-id="3765a-105">Form notifications are used in MAPI to facilitate communication both from the form to your viewer as well as from your viewer to the form.</span></span>
  
<span data-ttu-id="3765a-106">当发生以下事件之一时, 窗体将通知发送到查看器:</span><span class="sxs-lookup"><span data-stu-id="3765a-106">Forms send notifications to your viewer when one of the following events occur:</span></span>
  
- <span data-ttu-id="3765a-107">关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="3765a-107">The form is closed.</span></span>
    
- <span data-ttu-id="3765a-108">在表单中加载新邮件。</span><span class="sxs-lookup"><span data-stu-id="3765a-108">A new message is loaded in the form.</span></span>
    
- <span data-ttu-id="3765a-109">已完成保存操作。</span><span class="sxs-lookup"><span data-stu-id="3765a-109">A save operation is completed.</span></span>
    
- <span data-ttu-id="3765a-110">发送邮件。</span><span class="sxs-lookup"><span data-stu-id="3765a-110">A message is sent.</span></span>
    
<span data-ttu-id="3765a-111">这些事件类型分别对应于[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)中的特定方法, 即表单查看器必须实现的接口之一。</span><span class="sxs-lookup"><span data-stu-id="3765a-111">Each of these event types correspond to a particular method in [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md), one of the interfaces that your form viewer must implement.</span></span> <span data-ttu-id="3765a-112">事件发生时, 窗体调用查看器的通知接收器中对应的**IMAPIViewAdviseSink**方法。</span><span class="sxs-lookup"><span data-stu-id="3765a-112">When an event occurs, the form calls the corresponding **IMAPIViewAdviseSink** method in your viewer's advise sink.</span></span> <span data-ttu-id="3765a-113">例如, 当您的查看者应在其显示中包含一个新邮件时, 该表单将调用您的[IMAPIViewAdviseSink:: OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3765a-113">For example, when a new message arrives that your viewer should include in its display, the form calls your [IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md) method.</span></span> 
  
<span data-ttu-id="3765a-114">采用对查看器有意义的方式来实现您的视图建议接收器;没有标准实现。</span><span class="sxs-lookup"><span data-stu-id="3765a-114">Implement your view advise sink in a way that makes sense for your viewer; there is no standard implementation.</span></span> <span data-ttu-id="3765a-115">例如, 在**OnNewMessage**中, 可以更新当前文件夹的内容表的视图, 以包含新到达的邮件。</span><span class="sxs-lookup"><span data-stu-id="3765a-115">For example, in **OnNewMessage** you can update the view of the current folder's contents table to include the newly arrived message.</span></span> <span data-ttu-id="3765a-116">在[IMAPIViewAdviseSink:: OnSubmitted](imapiviewadvisesink-onsubmitted.md)中, 当您收到已提交的邮件事件时调用的方法, 您可以将已提交的邮件复制到 "已发送邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3765a-116">In [IMAPIViewAdviseSink::OnSubmitted](imapiviewadvisesink-onsubmitted.md), the method that is called when you receive a submitted message event, you can copy the submitted message to a Sent Items folder.</span></span>
  
<span data-ttu-id="3765a-117">当发生影响窗体的更改时, 窗体接收来自查看者的通知, 并且您正在加载新邮件。</span><span class="sxs-lookup"><span data-stu-id="3765a-117">Forms receive notification from your viewer when a change occurs that affects the form and when you are loading a new message.</span></span> <span data-ttu-id="3765a-118">若要通知表单, 请调用**IMAPIFormAdviseSink**的方法之一: [IMAPIFormAdviseSink:: OnChange](imapiformadvisesink-onchange.md) or [IMAPIFormAdviseSink:: OnActivateNext](imapiformadvisesink-onactivatenext.md)。</span><span class="sxs-lookup"><span data-stu-id="3765a-118">To notify a form, call one of the methods of **IMAPIFormAdviseSink**: [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md) or [IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md).</span></span> <span data-ttu-id="3765a-119">调用**OnChange**以传达状态。</span><span class="sxs-lookup"><span data-stu-id="3765a-119">Call **OnChange** to communicate status.</span></span> <span data-ttu-id="3765a-120">例如, 如果在新邮件到达时, 窗体显示文件夹中的最后一项, 则调用**OnChange**并将 VCSTATUS_NEXT 标志设置为通知窗体现在有一个下一个项。</span><span class="sxs-lookup"><span data-stu-id="3765a-120">For example, if the form is displaying the last item in a folder when a new message arrives, call **OnChange** with the VCSTATUS_NEXT flag set to tell the form that there is now a next item.</span></span> 
  
<span data-ttu-id="3765a-121">调用**OnActivateNext**将表单通知给可能显示或可能无法显示的新邮件的到达。</span><span class="sxs-lookup"><span data-stu-id="3765a-121">Call **OnActivateNext** to alert the form to the arrival of a new message that it may or may not be able to display.</span></span> <span data-ttu-id="3765a-122">将邮件的邮件类别传递给**OnActivateNext**。</span><span class="sxs-lookup"><span data-stu-id="3765a-122">Pass the message class of the message to **OnActivateNext**.</span></span> 
  
<span data-ttu-id="3765a-123">由表单对象向客户端应用程序发出的通知由客户端应用程序的**IMAPIViewAdviseSink**接口处理。</span><span class="sxs-lookup"><span data-stu-id="3765a-123">Notifications by a form object to the client application are handled by the client application's **IMAPIViewAdviseSink** interface.</span></span> <span data-ttu-id="3765a-124">有关详细信息, 请参阅[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="3765a-124">For more information, see [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md).</span></span>
  

