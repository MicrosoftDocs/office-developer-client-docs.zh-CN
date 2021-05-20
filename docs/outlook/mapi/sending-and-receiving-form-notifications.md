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
# <a name="sending-and-receiving-form-notifications"></a>发送和接收表单通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
窗体通知在 MAPI 中用于促进从窗体到查看器以及从查看器到窗体的通信。
  
发生以下事件之一时，表单会向查看器发送通知：
  
- 窗体已关闭。
    
- 在表单中加载新邮件。
    
- 保存操作已完成。
    
- 邮件已发送。
    
每个事件类型对应于 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md)中的特定方法，即表单查看器必须实现接口之一。 当事件发生时，表单在查看者的建议接收器中调用相应的 **IMAPIViewAdviseSink** 方法。 例如，当新消息到达您的查看器应包含在其显示中时，表单将调用 [IMAPIViewAdviseSink：：OnNewMessage](imapiviewadvisesink-onnewmessage.md) 方法。 
  
以对查看者有意义的方式实现视图建议接收;没有标准实现。 例如，在 **OnNewMessage** 中，可以更新当前文件夹的内容表的视图，以包含新到达的邮件。 在 [IMAPIViewAdviseSink：：OnSubmitted](imapiviewadvisesink-onsubmitted.md)中，接收提交的邮件事件时调用的方法可以将提交的邮件复制到"已发送的项目"文件夹。
  
当更改影响窗体和加载新邮件时，窗体会从查看器接收通知。 若要通知表单，请调用 **IMAPIFormAdviseSink**： [IMAPIFormAdviseSink：：OnChange](imapiformadvisesink-onchange.md) 或 [IMAPIFormAdviseSink：：OnActivateNext](imapiformadvisesink-onactivatenext.md)的方法之一。 调用 **OnChange** 来传达状态。 例如，如果窗体在有新邮件到达时显示文件夹中的最后一个项目，请调用设置了 VCSTATUS_NEXT 标志的 **OnChange，** 告诉窗体现在有下一个项目。 
  
调用 **OnActivateNext** 以提醒表单新消息的到达，该邮件可能会显示，也可能无法显示。 将邮件的邮件类传递到 **OnActivateNext**。 
  
通过表单对象向客户端应用程序发送的通知由客户端应用程序的 **IMAPIViewAdviseSink 接口** 处理。 有关详细信息，请参阅 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md)。
  

