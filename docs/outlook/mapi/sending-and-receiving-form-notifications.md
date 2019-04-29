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
  
窗体通知在 MAPI 中使用, 以促进从窗体到查看器以及从查看器到表单的通信。
  
当发生以下事件之一时, 窗体将通知发送到查看器:
  
- 关闭窗体。
    
- 在表单中加载新邮件。
    
- 已完成保存操作。
    
- 发送邮件。
    
这些事件类型分别对应于[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)中的特定方法, 即表单查看器必须实现的接口之一。 事件发生时, 窗体调用查看器的通知接收器中对应的**IMAPIViewAdviseSink**方法。 例如, 当您的查看者应在其显示中包含一个新邮件时, 该表单将调用您的[IMAPIViewAdviseSink:: OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法。 
  
采用对查看器有意义的方式来实现您的视图建议接收器;没有标准实现。 例如, 在**OnNewMessage**中, 可以更新当前文件夹的内容表的视图, 以包含新到达的邮件。 在[IMAPIViewAdviseSink:: OnSubmitted](imapiviewadvisesink-onsubmitted.md)中, 当您收到已提交的邮件事件时调用的方法, 您可以将已提交的邮件复制到 "已发送邮件" 文件夹。
  
当发生影响窗体的更改时, 窗体接收来自查看者的通知, 并且您正在加载新邮件。 若要通知表单, 请调用**IMAPIFormAdviseSink**的方法之一: [IMAPIFormAdviseSink:: OnChange](imapiformadvisesink-onchange.md) or [IMAPIFormAdviseSink:: OnActivateNext](imapiformadvisesink-onactivatenext.md)。 调用**OnChange**以传达状态。 例如, 如果在新邮件到达时, 窗体显示文件夹中的最后一项, 则调用**OnChange**并将 VCSTATUS_NEXT 标志设置为通知窗体现在有一个下一个项。 
  
调用**OnActivateNext**将表单通知给可能显示或可能无法显示的新邮件的到达。 将邮件的邮件类别传递给**OnActivateNext**。 
  
由表单对象向客户端应用程序发出的通知由客户端应用程序的**IMAPIViewAdviseSink**接口处理。 有关详细信息, 请参阅[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)。
  

