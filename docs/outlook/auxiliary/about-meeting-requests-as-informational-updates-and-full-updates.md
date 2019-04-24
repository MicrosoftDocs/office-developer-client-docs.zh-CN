---
title: 关于信息性更新和完整更新形式的会议请求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 084928ca-efc0-36da-fe4f-5cc45f226178
description: 会议请求是具有 IPM 的电子邮件。作为邮件类的日程安排。 默认情况下, 收到会议请求的与会者将直接响应。
ms.openlocfilehash: 8e7ab7a85d3f9f7c0a67245b8d8ad27442f5c5e4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316994"
---
# <a name="about-meeting-requests-as-informational-updates-and-full-updates"></a>关于信息性更新和完整更新形式的会议请求

会议请求是具有 IPM 的电子邮件 **。** 作为邮件类的日程安排。 默认情况下, 收到会议请求的与会者将直接响应。 Outlook 支持设置可以代表主体收件人响应会议请求的代理。 Outlook 以编程方式设置会议请求的命名属性[PidLidMeetingType](https://msdn.microsoft.com/library/290b290c-7836-4a7e-bf1a-8d0225a07e56%28Office.15%29.aspx) , 以标识当前的更新状态。 
  
## <a name="recipients-without-delegates"></a>没有代理的收件人

当 outlook 收到新的会议请求时, outlook 会将会议请求项目的**PidLidMeetingType**属性设置为**mtgRequest**。 该会议的任何后续更新都可以是**mtgFullUpdate** (完全更新) 或**mtgInfoUpdate** (信息更新), 具体取决于更新原因, 并相应地设置了 Outlook 设置**PidLidMeetingType** 。 完全更新要求与会者显式响应会议请求, 而信息更新则不会。 
  
## <a name="full-updates"></a>完全更新

有两种情况会导致完全更新:
  
- 当组织者更改以前会议请求的日期、时间、时区或重复周期时, 组织者必须向所有与会者发送更新。 此更新是一项完全更新, 与会者必须明确地对其做出响应, 以通知组织者出席情况, 因为 Outlook 将忽略任何以前的响应。
    
- 如果与会者未对初始会议请求做出响应, 并收到后续更新, 则初始会议请求将变得过时, 并且更新是完全更新, 而不考虑更新的原因。
    
## <a name="informational-updates"></a>信息更新

Outlook 生成信息性更新的情况有四种。 在这些情况下, 响应信息性更新是可选的。
  
- 如果组织者更改了上一个会议请求的位置, 则组织者必须向所有与会者发送更新。 如果与会者已接受初始会议请求, 则与会者会收到更新信息更新。
    
- 如果组织者将与会者添加到之前的会议请求中, 则组织者必须将会议请求发送给新添加的与会者, 并且可以选择在更新中包括现有的与会者。 新添加的与会者将接收会议请求作为新的请求。 如果组织者选择发送对现有与会者的更新, 则与会者会收到更新信息更新。
    
- 如果组织者从以前的会议请求中删除了某个与会者, 则该组织者必须向从会议请求中删除的与会者发送更新, 并且可以选择将现有与会者包含在更新中。 与会者以信息更新的形式接收更新。
    
- 如果组织者更改了之前会议请求的主题或正文, 则组织者可以选择向与会者发送更新, 也可以仅保存对组织者自己的会议请求副本所做的更改。 如果组织者选择发送更新, 与会者会收到更新信息更新。
    
## <a name="recipients-set-up-with-delegates"></a>设置了代理的收件人

选择设置代理的收件人可以让代理响应未标记为 "私人性质" 的会议请求。 默认情况下, 主体仅收到会议请求的副本或前一个会议请求的更新副本, 并且代理始终接收原始会议请求或原始的完整或信息性更新。 在此默认配置中, 主体始终接收委派的会议请求和更新;作为新会议请求、完全更新或信息更新的主体接收会议请求的代理人, 如 "不带委派的收件人" 一节中没有代理的收件人所述。
  
默认情况下, 主体可以选择响应非私有会议请求和更新, 即使已将代理设置为代表自己执行此操作。 但是, 作为一种替代方法, 管理员可以设置策略以阻止主体收件人进行响应。
  

