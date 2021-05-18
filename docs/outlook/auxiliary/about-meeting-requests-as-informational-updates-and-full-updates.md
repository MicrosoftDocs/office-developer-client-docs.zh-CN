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
# <a name="about-meeting-requests-as-informational-updates-and-full-updates"></a>关于信息性更新和完整更新形式的会议请求

会议请求是一封包含 **IPM 的电子邮件。Schedule.Meeting.Request** 作为邮件类。 默认情况下，接收会议请求的与会者会直接响应该请求。 Outlook设置代表主体收件人响应会议请求的代理人。 通过编程Outlook设置会议请求的命名属性[PidLidMeetingType](https://msdn.microsoft.com/library/290b290c-7836-4a7e-bf1a-8d0225a07e56%28Office.15%29.aspx)以标识当前更新状态。 
  
## <a name="recipients-without-delegates"></a>没有代理的收件人

当Outlook收到新的会议请求时，Outlook将会议请求项目的 **PidLidMeetingType** 属性设置 **mtgRequest**。 该会议的任何后续更新可以是 **mtgFullUpdate** (完整更新) 或 **mtgInfoUpdate** (信息更新) 具体取决于更新的原因，Outlook 相应地设置 **PidLidMeetingType。** 完整更新要求与会者明确响应会议请求，而信息更新则不需要。 
  
## <a name="full-updates"></a>完整更新

有两种方案会导致完全更新：
  
- 当组织者更改以前会议请求的日期、时间、时区或重复周期时，组织者必须将更新发送给所有与会者。 此更新是与会者必须明确响应以通知组织者出席的完整更新，因为Outlook会忽略之前的任何响应。
    
- 如果与会者尚未响应初始会议请求并收到后续更新，则初始会议请求将过期，并且更新为完整更新，无论更新的原因如何。
    
## <a name="informational-updates"></a>信息更新

在四种方案中，Outlook信息更新。 在这些情况下，响应信息更新是可选的。
  
- 如果组织者更改了以前的会议请求的位置，组织者必须将更新发送给所有与会者。 如果与会者已接受初始会议请求，则与会者将收到更新信息更新。
    
- 如果组织者向以前的会议请求添加与会者，组织者必须将会议请求发送给新添加的与会者，并且可以选择在更新中包括现有与会者。 新添加的与会者作为新请求接收会议请求。 如果组织者选择向现有与会者发送更新，则与会者将收到该更新作为信息性更新。
    
- 如果组织者从以前的会议请求中删除了与会者，组织者必须将更新发送给已从会议请求中删除的与会者，并且可以选择在更新中包括现有与会者。 与会者接收更新作为信息性更新。
    
- 如果组织者更改了以前的会议请求的主题或正文，组织者可以选择向与会者发送更新，或者只需将更改保存到组织者自己的会议请求副本中。 如果组织者选择发送更新，参与者将收到该更新作为信息性更新。
    
## <a name="recipients-set-up-with-delegates"></a>与代理人一起设置的收件人

选择设置代理的收件人可以让代理响应未标记为"私人"的会议请求。 默认情况下，主体仅接收会议请求的副本或对以前的会议请求的更新副本，并且代理人始终接收原始会议请求或原始完整或信息更新。 在此默认配置中，主体始终接收委派的会议请求和更新;主体的代理人接收会议请求作为新的会议请求、完整更新或信息更新，如"没有代理人的收件人"部分中对没有代理人的收件人所述。
  
默认情况下，主体可以选择响应非私人会议请求和更新，即使代理已设置为代表他们这样做。 但是，作为替代方法，管理员可以设置策略以防止主体收件人做出响应。
  

