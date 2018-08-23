---
title: 发送和接收表单通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a4374728-e2bc-47d9-8b03-ba09545a38d8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7148383c92b59adb9d3783e079e7c5f28c038eac
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588991"
---
# <a name="sending-and-receiving-form-notifications"></a><span data-ttu-id="e2e40-103">发送和接收表单通知</span><span class="sxs-lookup"><span data-stu-id="e2e40-103">Sending and Receiving Form Notifications</span></span>

  
  
<span data-ttu-id="e2e40-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e2e40-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e2e40-105">窗体通知使用 MAPI 便于您查看器的窗体中以及向窗体您查看器进行通信。</span><span class="sxs-lookup"><span data-stu-id="e2e40-105">Form notifications are used in MAPI to facilitate communication both from the form to your viewer as well as from your viewer to the form.</span></span>
  
<span data-ttu-id="e2e40-106">表单将通知发送到您查看器时出现以下事件之一,：</span><span class="sxs-lookup"><span data-stu-id="e2e40-106">Forms send notifications to your viewer when one of the following events occur:</span></span>
  
- <span data-ttu-id="e2e40-107">关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="e2e40-107">The form is closed.</span></span>
    
- <span data-ttu-id="e2e40-108">在窗体中加载新邮件。</span><span class="sxs-lookup"><span data-stu-id="e2e40-108">A new message is loaded in the form.</span></span>
    
- <span data-ttu-id="e2e40-109">完成保存操作。</span><span class="sxs-lookup"><span data-stu-id="e2e40-109">A save operation is completed.</span></span>
    
- <span data-ttu-id="e2e40-110">发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="e2e40-110">A message is sent.</span></span>
    
<span data-ttu-id="e2e40-111">每个事件类型对应于中的特定方法[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)，在表单查看器必须实现的接口之一。</span><span class="sxs-lookup"><span data-stu-id="e2e40-111">Each of these event types correspond to a particular method in [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md), one of the interfaces that your form viewer must implement.</span></span> <span data-ttu-id="e2e40-112">当发生事件时，您查看器中的相应**IMAPIViewAdviseSink**方法的建议接收器的窗体呼叫。</span><span class="sxs-lookup"><span data-stu-id="e2e40-112">When an event occurs, the form calls the corresponding **IMAPIViewAdviseSink** method in your viewer's advise sink.</span></span> <span data-ttu-id="e2e40-113">例如，您查看器应包括在其显示新消息时，窗体调用[IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e2e40-113">For example, when a new message arrives that your viewer should include in its display, the form calls your [IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md) method.</span></span> 
  
<span data-ttu-id="e2e40-114">您的视图的建议方式，才有意义的您查看器; 接收器的实现没有任何标准的实现。</span><span class="sxs-lookup"><span data-stu-id="e2e40-114">Implement your view advise sink in a way that makes sense for your viewer; there is no standard implementation.</span></span> <span data-ttu-id="e2e40-115">例如，在**OnNewMessage**可以更新当前文件夹的内容的表格，以包含新到达的消息的视图。</span><span class="sxs-lookup"><span data-stu-id="e2e40-115">For example, in **OnNewMessage** you can update the view of the current folder's contents table to include the newly arrived message.</span></span> <span data-ttu-id="e2e40-116">在[IMAPIViewAdviseSink::OnSubmitted](imapiviewadvisesink-onsubmitted.md)，当您收到的已提交的邮件事件，调用的方法可以将提交的邮件复制到已发送邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="e2e40-116">In [IMAPIViewAdviseSink::OnSubmitted](imapiviewadvisesink-onsubmitted.md), the method that is called when you receive a submitted message event, you can copy the submitted message to a Sent Items folder.</span></span>
  
<span data-ttu-id="e2e40-117">发生更改的影响窗体时和您正在加载新消息时，窗体从您查看器收到通知。</span><span class="sxs-lookup"><span data-stu-id="e2e40-117">Forms receive notification from your viewer when a change occurs that affects the form and when you are loading a new message.</span></span> <span data-ttu-id="e2e40-118">若要通知窗体，请调用**IMAPIFormAdviseSink**的方法之一： [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md)或[IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md)。</span><span class="sxs-lookup"><span data-stu-id="e2e40-118">To notify a form, call one of the methods of **IMAPIFormAdviseSink**: [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md) or [IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md).</span></span> <span data-ttu-id="e2e40-119">调用**OnChange**传达状态。</span><span class="sxs-lookup"><span data-stu-id="e2e40-119">Call **OnChange** to communicate status.</span></span> <span data-ttu-id="e2e40-120">例如，如果新邮件到达时，窗体文件夹中显示的最后一项，VCSTATUS_NEXT 标志设置，以告知窗体是现在下一个项目调用**OnChange** 。</span><span class="sxs-lookup"><span data-stu-id="e2e40-120">For example, if the form is displaying the last item in a folder when a new message arrives, call **OnChange** with the VCSTATUS_NEXT flag set to tell the form that there is now a next item.</span></span> 
  
<span data-ttu-id="e2e40-121">调用**OnActivateNext**警告表单转换为新消息的到达其可能也可能不能显示。</span><span class="sxs-lookup"><span data-stu-id="e2e40-121">Call **OnActivateNext** to alert the form to the arrival of a new message that it may or may not be able to display.</span></span> <span data-ttu-id="e2e40-122">传递给**OnActivateNext**邮件的邮件类别。</span><span class="sxs-lookup"><span data-stu-id="e2e40-122">Pass the message class of the message to **OnActivateNext**.</span></span> 
  
<span data-ttu-id="e2e40-123">通过客户端应用程序的**IMAPIViewAdviseSink**接口来处理由客户端应用程序窗体对象的通知。</span><span class="sxs-lookup"><span data-stu-id="e2e40-123">Notifications by a form object to the client application are handled by the client application's **IMAPIViewAdviseSink** interface.</span></span> <span data-ttu-id="e2e40-124">有关详细信息，请参阅[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="e2e40-124">For more information, see [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md).</span></span>
  

