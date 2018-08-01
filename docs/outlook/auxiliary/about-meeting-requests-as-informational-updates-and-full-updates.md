---
title: 关于信息性更新和完整更新形式的会议请求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 084928ca-efc0-36da-fe4f-5cc45f226178
description: 会议请求是具有 IPM 电子邮件。邮件类作为 Schedule.Meeting.Request。 默认情况下，与会者接收会议请求响应其直接。
ms.openlocfilehash: 3565b2af03ef79d70fc9f2817c64a788f031c416
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774168"
---
# <a name="about-meeting-requests-as-informational-updates-and-full-updates"></a><span data-ttu-id="8069b-104">关于信息性更新和完整更新形式的会议请求</span><span class="sxs-lookup"><span data-stu-id="8069b-104">About meeting requests as informational updates and full updates</span></span>

<span data-ttu-id="8069b-105">会议请求是具有**IPM 电子邮件。Schedule.Meeting.Request**作为邮件类。</span><span class="sxs-lookup"><span data-stu-id="8069b-105">A meeting request is an email that has **IPM.Schedule.Meeting.Request** as the message class.</span></span> <span data-ttu-id="8069b-106">默认情况下，与会者接收会议请求响应其直接。</span><span class="sxs-lookup"><span data-stu-id="8069b-106">By default, an attendee receiving a meeting request responds to it directly.</span></span> <span data-ttu-id="8069b-107">Outlook 支持设置代理人可以代表主体的收件人的会议请求响应。</span><span class="sxs-lookup"><span data-stu-id="8069b-107">Outlook supports setting up delegates who can respond to meeting requests on behalf of the principal recipient.</span></span> <span data-ttu-id="8069b-108">以编程方式，Outlook 设置的命名的属性[PidLidMeetingType](http://msdn.microsoft.com/library/290b290c-7836-4a7e-bf1a-8d0225a07e56%28Office.15%29.aspx)的会议请求来识别当前更新状态。</span><span class="sxs-lookup"><span data-stu-id="8069b-108">Programmatically, Outlook sets the named property [PidLidMeetingType](http://msdn.microsoft.com/library/290b290c-7836-4a7e-bf1a-8d0225a07e56%28Office.15%29.aspx) of a meeting request to identify the current update status.</span></span> 
  
## <a name="recipients-without-delegates"></a><span data-ttu-id="8069b-109">没有代理人的收件人</span><span class="sxs-lookup"><span data-stu-id="8069b-109">Recipients without delegates</span></span>

<span data-ttu-id="8069b-110">当 Outlook 收到新会议请求，会议请求的**PidLidMeetingType**属性**mtgRequest**到项目的 Outlook 设置。</span><span class="sxs-lookup"><span data-stu-id="8069b-110">When Outlook receives a new meeting request, Outlook sets the **PidLidMeetingType** property of the meeting request item to **mtgRequest**.</span></span> <span data-ttu-id="8069b-111">将会议的任何后续更新为**mtgFullUpdate** （完全更新） 或**mtgInfoUpdate** （信息性更新） 根据具有相应地设置**PidLidMeetingType**的 Outlook 更新的原因。</span><span class="sxs-lookup"><span data-stu-id="8069b-111">Any subsequent update of that meeting is either **mtgFullUpdate** (a full update) or **mtgInfoUpdate** (an informational update) depending on the cause of the update, with Outlook setting **PidLidMeetingType** accordingly.</span></span> <span data-ttu-id="8069b-112">完全更新需要显式响应会议请求中，与会者和信息性更新不。</span><span class="sxs-lookup"><span data-stu-id="8069b-112">A full update requires an attendee to explicitly respond to the meeting request, and an informational update does not.</span></span> 
  
## <a name="full-updates"></a><span data-ttu-id="8069b-113">完全更新</span><span class="sxs-lookup"><span data-stu-id="8069b-113">Full updates</span></span>

<span data-ttu-id="8069b-114">有两种方案，由此导致完全更新：</span><span class="sxs-lookup"><span data-stu-id="8069b-114">There are two scenarios that result in a full update:</span></span>
  
- <span data-ttu-id="8069b-115">当组织者更改日期、 时间、 时区或将前一个会议请求的定期时，组织者必须将更新发送给所有与会者。</span><span class="sxs-lookup"><span data-stu-id="8069b-115">When an organizer changes the date, time, time zones, or recurrence of a prior meeting request, the organizer must send an update to all the attendees.</span></span> <span data-ttu-id="8069b-116">此更新是出勤的完全更新与会者必须明确响应通知的组织者，因为 Outlook 将忽略任何以前的响应。</span><span class="sxs-lookup"><span data-stu-id="8069b-116">This update is a full update to which an attendee must explicitly respond to notify the organizer of attendance, because Outlook ignores any previous responses.</span></span>
    
- <span data-ttu-id="8069b-117">如果参与者尚未响应的初始会议请求和接收的后续更新，初始会议请求将变成过期，更新完全更新，而不考虑更新的原因。</span><span class="sxs-lookup"><span data-stu-id="8069b-117">If an attendee has not responded to an initial meeting request and receives a subsequent update, the initial meeting request becomes out-of-date and the update is a full update, regardless of the cause of the update.</span></span>
    
## <a name="informational-updates"></a><span data-ttu-id="8069b-118">信息性更新</span><span class="sxs-lookup"><span data-stu-id="8069b-118">Informational updates</span></span>

<span data-ttu-id="8069b-119">有四种情况，Outlook 将在其中生成信息性更新。</span><span class="sxs-lookup"><span data-stu-id="8069b-119">There are four scenarios in which Outlook generates an informational update.</span></span> <span data-ttu-id="8069b-120">在这些方案中，信息性更新响应是可选的。</span><span class="sxs-lookup"><span data-stu-id="8069b-120">In these scenarios, responding to the informational update is optional.</span></span>
  
- <span data-ttu-id="8069b-121">如果组织者更改以前的会议请求的位置，组织者必须发送给所有与会者的更新。</span><span class="sxs-lookup"><span data-stu-id="8069b-121">If an organizer changes the location of a prior meeting request, the organizer must send an update to all the attendees.</span></span> <span data-ttu-id="8069b-122">参与者已接受初始会议请求中，如果参与者作为信息性更新接收到更新。</span><span class="sxs-lookup"><span data-stu-id="8069b-122">If an attendee already accepted the initial meeting request, the attendee receives the update as an informational update.</span></span>
    
- <span data-ttu-id="8069b-123">如果组织者将参与者添加到前一个会议请求，组织者必须向新添加的与会者，发送会议请求，并可以选择要包含在更新现有与会者。</span><span class="sxs-lookup"><span data-stu-id="8069b-123">If an organizer adds an attendee to a prior meeting request, the organizer must send the meeting request to the newly added attendee, and has the option to include existing attendees on the update.</span></span> <span data-ttu-id="8069b-124">新添加的与会者作为新请求接收会议请求。</span><span class="sxs-lookup"><span data-stu-id="8069b-124">The newly added attendee receives the meeting request as a new request.</span></span> <span data-ttu-id="8069b-125">如果组织者选择将更新发送给现有与会者，与会者作为信息性更新接收更新。</span><span class="sxs-lookup"><span data-stu-id="8069b-125">If the organizer chooses to send an update to existing attendees, the attendees receive the update as an informational update.</span></span>
    
- <span data-ttu-id="8069b-126">如果组织者在早期会议请求中删除与会者，组织者必须向会议请求中已删除具有一个选项，包括在更新现有与会者的与会者发送更新。</span><span class="sxs-lookup"><span data-stu-id="8069b-126">If an organizer removes an attendee from a prior meeting request, the organizer must send an update to the attendee who was removed from the meeting request and has an option to include existing attendees on the update.</span></span> <span data-ttu-id="8069b-127">与会者接收作为信息性更新的更新。</span><span class="sxs-lookup"><span data-stu-id="8069b-127">Attendees receive the update as an informational update.</span></span>
    
- <span data-ttu-id="8069b-128">如果组织者更改主题或正文的前一个会议请求，组织者可以选择要向与会者发送更新或刚刚将所做的更改保存到会议请求的组织者自己的副本。</span><span class="sxs-lookup"><span data-stu-id="8069b-128">If an organizer changes the subject or body of a prior meeting request, the organizer has the option to send an update to the attendees or just save the changes to the organizer's own copy of the meeting request.</span></span> <span data-ttu-id="8069b-129">如果组织者选择发送更新，与会者作为信息性更新接收更新。</span><span class="sxs-lookup"><span data-stu-id="8069b-129">If the organizer chooses to send an update, attendees receive the update as an informational update.</span></span>
    
## <a name="recipients-set-up-with-delegates"></a><span data-ttu-id="8069b-130">设置与代理人的收件人</span><span class="sxs-lookup"><span data-stu-id="8069b-130">Recipients set up with delegates</span></span>

<span data-ttu-id="8069b-131">收件人选择设置代理人可以响应会议请求的未标记专用的代理人。</span><span class="sxs-lookup"><span data-stu-id="8069b-131">Recipients who choose to set up delegates can have delegates respond to meeting requests that are not marked Private.</span></span> <span data-ttu-id="8069b-132">默认情况下主体接收仅会议请求的副本或以前的会议请求，更新的副本，然后代理人始终接收的原始会议请求或原始完整或信息性更新。</span><span class="sxs-lookup"><span data-stu-id="8069b-132">By default, the principal receives only a copy of a meeting request or a copy of an update to a prior meeting request, and the delegates always receive the original meeting request or original full or informational update.</span></span> <span data-ttu-id="8069b-133">在此默认配置，主体始终接收委派的会议请求和更新;主体的代理人都会收到新会议请求、 完全更新或信息性更新作为会议请求，如下所述的收件人无委托的部分"没有代理人的收件人"。</span><span class="sxs-lookup"><span data-stu-id="8069b-133">In this default configuration, the principal always receives delegated meeting requests and updates; delegates of the principal receive meeting requests as new meeting requests, full updates, or informational updates, as described for recipients without delegates in the section "Recipients Without Delegates."</span></span>
  
<span data-ttu-id="8069b-134">默认情况下主体可以选择响应非私有会议请求和更新，即使设置代理人代表其拨打执行的。</span><span class="sxs-lookup"><span data-stu-id="8069b-134">By default, principals can choose to respond to non-private meeting requests and updates, even though delegates are set up to do that on their behalf.</span></span> <span data-ttu-id="8069b-135">但是，或者，管理员可以设置策略以阻止进行响应的主体的收件人。</span><span class="sxs-lookup"><span data-stu-id="8069b-135">However, as an alternative, administrators can set up a policy to prevent principal recipients from responding.</span></span>
  

