---
title: 关于信息性更新和完整更新形式的会议请求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 084928ca-efc0-36da-fe4f-5cc45f226178
description: 会议请求是具有 IPM 电子邮件。邮件类作为 Schedule.Meeting.Request。 默认情况下，与会者接收会议请求响应其直接。
ms.openlocfilehash: 8e7ab7a85d3f9f7c0a67245b8d8ad27442f5c5e4
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400129"
---
# <a name="about-meeting-requests-as-informational-updates-and-full-updates"></a>关于信息性更新和完整更新形式的会议请求

会议请求是具有**IPM 电子邮件。Schedule.Meeting.Request**作为邮件类。 默认情况下，与会者接收会议请求响应其直接。 Outlook 支持设置代理人可以代表主体的收件人的会议请求响应。 以编程方式，Outlook 设置的命名的属性[PidLidMeetingType](https://msdn.microsoft.com/library/290b290c-7836-4a7e-bf1a-8d0225a07e56%28Office.15%29.aspx)的会议请求来识别当前更新状态。 
  
## <a name="recipients-without-delegates"></a>没有代理人的收件人

当 Outlook 收到新会议请求，会议请求的**PidLidMeetingType**属性**mtgRequest**到项目的 Outlook 设置。 将会议的任何后续更新为**mtgFullUpdate** （完全更新） 或**mtgInfoUpdate** （信息性更新） 根据具有相应地设置**PidLidMeetingType**的 Outlook 更新的原因。 完全更新需要显式响应会议请求中，与会者和信息性更新不。 
  
## <a name="full-updates"></a>完全更新

有两种方案，由此导致完全更新：
  
- 当组织者更改日期、 时间、 时区或将前一个会议请求的定期时，组织者必须将更新发送给所有与会者。 此更新是出勤的完全更新与会者必须明确响应通知的组织者，因为 Outlook 将忽略任何以前的响应。
    
- 如果参与者尚未响应的初始会议请求和接收的后续更新，初始会议请求将变成过期，更新完全更新，而不考虑更新的原因。
    
## <a name="informational-updates"></a>信息性更新

有四种情况，Outlook 将在其中生成信息性更新。 在这些方案中，信息性更新响应是可选的。
  
- 如果组织者更改以前的会议请求的位置，组织者必须发送给所有与会者的更新。 参与者已接受初始会议请求中，如果参与者作为信息性更新接收到更新。
    
- 如果组织者将参与者添加到前一个会议请求，组织者必须向新添加的与会者，发送会议请求，并可以选择要包含在更新现有与会者。 新添加的与会者作为新请求接收会议请求。 如果组织者选择将更新发送给现有与会者，与会者作为信息性更新接收更新。
    
- 如果组织者在早期会议请求中删除与会者，组织者必须向会议请求中已删除具有一个选项，包括在更新现有与会者的与会者发送更新。 与会者接收作为信息性更新的更新。
    
- 如果组织者更改主题或正文的前一个会议请求，组织者可以选择要向与会者发送更新或刚刚将所做的更改保存到会议请求的组织者自己的副本。 如果组织者选择发送更新，与会者作为信息性更新接收更新。
    
## <a name="recipients-set-up-with-delegates"></a>设置与代理人的收件人

收件人选择设置代理人可以响应会议请求的未标记专用的代理人。 默认情况下主体接收仅会议请求的副本或以前的会议请求，更新的副本，然后代理人始终接收的原始会议请求或原始完整或信息性更新。 在此默认配置，主体始终接收委派的会议请求和更新;主体的代理人都会收到新会议请求、 完全更新或信息性更新作为会议请求，如下所述的收件人无委托的部分"没有代理人的收件人"。
  
默认情况下主体可以选择响应非私有会议请求和更新，即使设置代理人代表其拨打执行的。 但是，或者，管理员可以设置策略以阻止进行响应的主体的收件人。
  

