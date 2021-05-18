---
title: 关于信息性更新和完整更新形式的会议请求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 084928ca-efc0-36da-fe4f-5cc45f226178
description: 会议请求是一封包含 IPM 的电子邮件。Schedule.Meeting.Request 作为邮件类。 默认情况下，接收会议请求的与会者会直接响应该请求。
ms.openlocfilehash: 8e7ab7a85d3f9f7c0a67245b8d8ad27442f5c5e4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316994"
---
# <a name="about-meeting-requests-as-informational-updates-and-full-updates"></a><span data-ttu-id="4ae84-104">关于信息性更新和完整更新形式的会议请求</span><span class="sxs-lookup"><span data-stu-id="4ae84-104">About meeting requests as informational updates and full updates</span></span>

<span data-ttu-id="4ae84-105">会议请求是一封包含 **IPM 的电子邮件。Schedule.Meeting.Request** 作为邮件类。</span><span class="sxs-lookup"><span data-stu-id="4ae84-105">A meeting request is an email that has **IPM.Schedule.Meeting.Request** as the message class.</span></span> <span data-ttu-id="4ae84-106">默认情况下，接收会议请求的与会者会直接响应该请求。</span><span class="sxs-lookup"><span data-stu-id="4ae84-106">By default, an attendee receiving a meeting request responds to it directly.</span></span> <span data-ttu-id="4ae84-107">Outlook设置代表主体收件人响应会议请求的代理人。</span><span class="sxs-lookup"><span data-stu-id="4ae84-107">Outlook supports setting up delegates who can respond to meeting requests on behalf of the principal recipient.</span></span> <span data-ttu-id="4ae84-108">通过编程Outlook设置会议请求的命名属性[PidLidMeetingType](https://msdn.microsoft.com/library/290b290c-7836-4a7e-bf1a-8d0225a07e56%28Office.15%29.aspx)以标识当前更新状态。</span><span class="sxs-lookup"><span data-stu-id="4ae84-108">Programmatically, Outlook sets the named property [PidLidMeetingType](https://msdn.microsoft.com/library/290b290c-7836-4a7e-bf1a-8d0225a07e56%28Office.15%29.aspx) of a meeting request to identify the current update status.</span></span> 
  
## <a name="recipients-without-delegates"></a><span data-ttu-id="4ae84-109">没有代理的收件人</span><span class="sxs-lookup"><span data-stu-id="4ae84-109">Recipients without delegates</span></span>

<span data-ttu-id="4ae84-110">当Outlook收到新的会议请求时，Outlook将会议请求项目的 **PidLidMeetingType** 属性设置 **mtgRequest**。</span><span class="sxs-lookup"><span data-stu-id="4ae84-110">When Outlook receives a new meeting request, Outlook sets the **PidLidMeetingType** property of the meeting request item to **mtgRequest**.</span></span> <span data-ttu-id="4ae84-111">该会议的任何后续更新可以是 **mtgFullUpdate** (完整更新) 或 **mtgInfoUpdate** (信息更新) 具体取决于更新的原因，Outlook 相应地设置 **PidLidMeetingType。**</span><span class="sxs-lookup"><span data-stu-id="4ae84-111">Any subsequent update of that meeting is either **mtgFullUpdate** (a full update) or **mtgInfoUpdate** (an informational update) depending on the cause of the update, with Outlook setting **PidLidMeetingType** accordingly.</span></span> <span data-ttu-id="4ae84-112">完整更新要求与会者明确响应会议请求，而信息更新则不需要。</span><span class="sxs-lookup"><span data-stu-id="4ae84-112">A full update requires an attendee to explicitly respond to the meeting request, and an informational update does not.</span></span> 
  
## <a name="full-updates"></a><span data-ttu-id="4ae84-113">完整更新</span><span class="sxs-lookup"><span data-stu-id="4ae84-113">Full updates</span></span>

<span data-ttu-id="4ae84-114">有两种方案会导致完全更新：</span><span class="sxs-lookup"><span data-stu-id="4ae84-114">There are two scenarios that result in a full update:</span></span>
  
- <span data-ttu-id="4ae84-115">当组织者更改以前会议请求的日期、时间、时区或重复周期时，组织者必须将更新发送给所有与会者。</span><span class="sxs-lookup"><span data-stu-id="4ae84-115">When an organizer changes the date, time, time zones, or recurrence of a prior meeting request, the organizer must send an update to all the attendees.</span></span> <span data-ttu-id="4ae84-116">此更新是与会者必须明确响应以通知组织者出席的完整更新，因为Outlook会忽略之前的任何响应。</span><span class="sxs-lookup"><span data-stu-id="4ae84-116">This update is a full update to which an attendee must explicitly respond to notify the organizer of attendance, because Outlook ignores any previous responses.</span></span>
    
- <span data-ttu-id="4ae84-117">如果与会者尚未响应初始会议请求并收到后续更新，则初始会议请求将过期，并且更新为完整更新，无论更新的原因如何。</span><span class="sxs-lookup"><span data-stu-id="4ae84-117">If an attendee has not responded to an initial meeting request and receives a subsequent update, the initial meeting request becomes out-of-date and the update is a full update, regardless of the cause of the update.</span></span>
    
## <a name="informational-updates"></a><span data-ttu-id="4ae84-118">信息更新</span><span class="sxs-lookup"><span data-stu-id="4ae84-118">Informational updates</span></span>

<span data-ttu-id="4ae84-119">在四种方案中，Outlook信息更新。</span><span class="sxs-lookup"><span data-stu-id="4ae84-119">There are four scenarios in which Outlook generates an informational update.</span></span> <span data-ttu-id="4ae84-120">在这些情况下，响应信息更新是可选的。</span><span class="sxs-lookup"><span data-stu-id="4ae84-120">In these scenarios, responding to the informational update is optional.</span></span>
  
- <span data-ttu-id="4ae84-121">如果组织者更改了以前的会议请求的位置，组织者必须将更新发送给所有与会者。</span><span class="sxs-lookup"><span data-stu-id="4ae84-121">If an organizer changes the location of a prior meeting request, the organizer must send an update to all the attendees.</span></span> <span data-ttu-id="4ae84-122">如果与会者已接受初始会议请求，则与会者将收到更新信息更新。</span><span class="sxs-lookup"><span data-stu-id="4ae84-122">If an attendee already accepted the initial meeting request, the attendee receives the update as an informational update.</span></span>
    
- <span data-ttu-id="4ae84-123">如果组织者向以前的会议请求添加与会者，组织者必须将会议请求发送给新添加的与会者，并且可以选择在更新中包括现有与会者。</span><span class="sxs-lookup"><span data-stu-id="4ae84-123">If an organizer adds an attendee to a prior meeting request, the organizer must send the meeting request to the newly added attendee, and has the option to include existing attendees on the update.</span></span> <span data-ttu-id="4ae84-124">新添加的与会者作为新请求接收会议请求。</span><span class="sxs-lookup"><span data-stu-id="4ae84-124">The newly added attendee receives the meeting request as a new request.</span></span> <span data-ttu-id="4ae84-125">如果组织者选择向现有与会者发送更新，则与会者将收到该更新作为信息性更新。</span><span class="sxs-lookup"><span data-stu-id="4ae84-125">If the organizer chooses to send an update to existing attendees, the attendees receive the update as an informational update.</span></span>
    
- <span data-ttu-id="4ae84-126">如果组织者从以前的会议请求中删除了与会者，组织者必须将更新发送给已从会议请求中删除的与会者，并且可以选择在更新中包括现有与会者。</span><span class="sxs-lookup"><span data-stu-id="4ae84-126">If an organizer removes an attendee from a prior meeting request, the organizer must send an update to the attendee who was removed from the meeting request and has an option to include existing attendees on the update.</span></span> <span data-ttu-id="4ae84-127">与会者接收更新作为信息性更新。</span><span class="sxs-lookup"><span data-stu-id="4ae84-127">Attendees receive the update as an informational update.</span></span>
    
- <span data-ttu-id="4ae84-128">如果组织者更改了以前的会议请求的主题或正文，组织者可以选择向与会者发送更新，或者只需将更改保存到组织者自己的会议请求副本中。</span><span class="sxs-lookup"><span data-stu-id="4ae84-128">If an organizer changes the subject or body of a prior meeting request, the organizer has the option to send an update to the attendees or just save the changes to the organizer's own copy of the meeting request.</span></span> <span data-ttu-id="4ae84-129">如果组织者选择发送更新，参与者将收到该更新作为信息性更新。</span><span class="sxs-lookup"><span data-stu-id="4ae84-129">If the organizer chooses to send an update, attendees receive the update as an informational update.</span></span>
    
## <a name="recipients-set-up-with-delegates"></a><span data-ttu-id="4ae84-130">与代理人一起设置的收件人</span><span class="sxs-lookup"><span data-stu-id="4ae84-130">Recipients set up with delegates</span></span>

<span data-ttu-id="4ae84-131">选择设置代理的收件人可以让代理响应未标记为"私人"的会议请求。</span><span class="sxs-lookup"><span data-stu-id="4ae84-131">Recipients who choose to set up delegates can have delegates respond to meeting requests that are not marked Private.</span></span> <span data-ttu-id="4ae84-132">默认情况下，主体仅接收会议请求的副本或对以前的会议请求的更新副本，并且代理人始终接收原始会议请求或原始完整或信息更新。</span><span class="sxs-lookup"><span data-stu-id="4ae84-132">By default, the principal receives only a copy of a meeting request or a copy of an update to a prior meeting request, and the delegates always receive the original meeting request or original full or informational update.</span></span> <span data-ttu-id="4ae84-133">在此默认配置中，主体始终接收委派的会议请求和更新;主体的代理人接收会议请求作为新的会议请求、完整更新或信息更新，如"没有代理人的收件人"部分中对没有代理人的收件人所述。</span><span class="sxs-lookup"><span data-stu-id="4ae84-133">In this default configuration, the principal always receives delegated meeting requests and updates; delegates of the principal receive meeting requests as new meeting requests, full updates, or informational updates, as described for recipients without delegates in the section "Recipients Without Delegates."</span></span>
  
<span data-ttu-id="4ae84-134">默认情况下，主体可以选择响应非私人会议请求和更新，即使代理已设置为代表他们这样做。</span><span class="sxs-lookup"><span data-stu-id="4ae84-134">By default, principals can choose to respond to non-private meeting requests and updates, even though delegates are set up to do that on their behalf.</span></span> <span data-ttu-id="4ae84-135">但是，作为替代方法，管理员可以设置策略以防止主体收件人做出响应。</span><span class="sxs-lookup"><span data-stu-id="4ae84-135">However, as an alternative, administrators can set up a policy to prevent principal recipients from responding.</span></span>
  

