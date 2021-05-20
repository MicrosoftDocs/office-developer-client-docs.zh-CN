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
# <a name="sending-and-receiving-form-notifications"></a><span data-ttu-id="1a610-103">发送和接收表单通知</span><span class="sxs-lookup"><span data-stu-id="1a610-103">Sending and Receiving Form Notifications</span></span>

  
  
<span data-ttu-id="1a610-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1a610-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1a610-105">窗体通知在 MAPI 中用于促进从窗体到查看器以及从查看器到窗体的通信。</span><span class="sxs-lookup"><span data-stu-id="1a610-105">Form notifications are used in MAPI to facilitate communication both from the form to your viewer as well as from your viewer to the form.</span></span>
  
<span data-ttu-id="1a610-106">发生以下事件之一时，表单会向查看器发送通知：</span><span class="sxs-lookup"><span data-stu-id="1a610-106">Forms send notifications to your viewer when one of the following events occur:</span></span>
  
- <span data-ttu-id="1a610-107">窗体已关闭。</span><span class="sxs-lookup"><span data-stu-id="1a610-107">The form is closed.</span></span>
    
- <span data-ttu-id="1a610-108">在表单中加载新邮件。</span><span class="sxs-lookup"><span data-stu-id="1a610-108">A new message is loaded in the form.</span></span>
    
- <span data-ttu-id="1a610-109">保存操作已完成。</span><span class="sxs-lookup"><span data-stu-id="1a610-109">A save operation is completed.</span></span>
    
- <span data-ttu-id="1a610-110">邮件已发送。</span><span class="sxs-lookup"><span data-stu-id="1a610-110">A message is sent.</span></span>
    
<span data-ttu-id="1a610-111">每个事件类型对应于 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md)中的特定方法，即表单查看器必须实现接口之一。</span><span class="sxs-lookup"><span data-stu-id="1a610-111">Each of these event types correspond to a particular method in [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md), one of the interfaces that your form viewer must implement.</span></span> <span data-ttu-id="1a610-112">当事件发生时，表单在查看者的建议接收器中调用相应的 **IMAPIViewAdviseSink** 方法。</span><span class="sxs-lookup"><span data-stu-id="1a610-112">When an event occurs, the form calls the corresponding **IMAPIViewAdviseSink** method in your viewer's advise sink.</span></span> <span data-ttu-id="1a610-113">例如，当新消息到达您的查看器应包含在其显示中时，表单将调用 [IMAPIViewAdviseSink：：OnNewMessage](imapiviewadvisesink-onnewmessage.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="1a610-113">For example, when a new message arrives that your viewer should include in its display, the form calls your [IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md) method.</span></span> 
  
<span data-ttu-id="1a610-114">以对查看者有意义的方式实现视图建议接收;没有标准实现。</span><span class="sxs-lookup"><span data-stu-id="1a610-114">Implement your view advise sink in a way that makes sense for your viewer; there is no standard implementation.</span></span> <span data-ttu-id="1a610-115">例如，在 **OnNewMessage** 中，可以更新当前文件夹的内容表的视图，以包含新到达的邮件。</span><span class="sxs-lookup"><span data-stu-id="1a610-115">For example, in **OnNewMessage** you can update the view of the current folder's contents table to include the newly arrived message.</span></span> <span data-ttu-id="1a610-116">在 [IMAPIViewAdviseSink：：OnSubmitted](imapiviewadvisesink-onsubmitted.md)中，接收提交的邮件事件时调用的方法可以将提交的邮件复制到"已发送的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="1a610-116">In [IMAPIViewAdviseSink::OnSubmitted](imapiviewadvisesink-onsubmitted.md), the method that is called when you receive a submitted message event, you can copy the submitted message to a Sent Items folder.</span></span>
  
<span data-ttu-id="1a610-117">当更改影响窗体和加载新邮件时，窗体会从查看器接收通知。</span><span class="sxs-lookup"><span data-stu-id="1a610-117">Forms receive notification from your viewer when a change occurs that affects the form and when you are loading a new message.</span></span> <span data-ttu-id="1a610-118">若要通知表单，请调用 **IMAPIFormAdviseSink**： [IMAPIFormAdviseSink：：OnChange](imapiformadvisesink-onchange.md) 或 [IMAPIFormAdviseSink：：OnActivateNext](imapiformadvisesink-onactivatenext.md)的方法之一。</span><span class="sxs-lookup"><span data-stu-id="1a610-118">To notify a form, call one of the methods of **IMAPIFormAdviseSink**: [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md) or [IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md).</span></span> <span data-ttu-id="1a610-119">调用 **OnChange** 来传达状态。</span><span class="sxs-lookup"><span data-stu-id="1a610-119">Call **OnChange** to communicate status.</span></span> <span data-ttu-id="1a610-120">例如，如果窗体在有新邮件到达时显示文件夹中的最后一个项目，请调用设置了 VCSTATUS_NEXT 标志的 **OnChange，** 告诉窗体现在有下一个项目。</span><span class="sxs-lookup"><span data-stu-id="1a610-120">For example, if the form is displaying the last item in a folder when a new message arrives, call **OnChange** with the VCSTATUS_NEXT flag set to tell the form that there is now a next item.</span></span> 
  
<span data-ttu-id="1a610-121">调用 **OnActivateNext** 以提醒表单新消息的到达，该邮件可能会显示，也可能无法显示。</span><span class="sxs-lookup"><span data-stu-id="1a610-121">Call **OnActivateNext** to alert the form to the arrival of a new message that it may or may not be able to display.</span></span> <span data-ttu-id="1a610-122">将邮件的邮件类传递到 **OnActivateNext**。</span><span class="sxs-lookup"><span data-stu-id="1a610-122">Pass the message class of the message to **OnActivateNext**.</span></span> 
  
<span data-ttu-id="1a610-123">通过表单对象向客户端应用程序发送的通知由客户端应用程序的 **IMAPIViewAdviseSink 接口** 处理。</span><span class="sxs-lookup"><span data-stu-id="1a610-123">Notifications by a form object to the client application are handled by the client application's **IMAPIViewAdviseSink** interface.</span></span> <span data-ttu-id="1a610-124">有关详细信息，请参阅 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="1a610-124">For more information, see [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md).</span></span>
  

