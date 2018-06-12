---
title: 发送和接收窗体通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a4374728-e2bc-47d9-8b03-ba09545a38d8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4730fb04d530fce516fe1ca4fd572c58fc1f1ffa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778729"
---
# <a name="sending-and-receiving-form-notifications"></a>发送和接收窗体通知

  
  
**适用于**： Outlook 
  
窗体通知使用 MAPI 便于您查看器的窗体中以及向窗体您查看器进行通信。
  
表单将通知发送到您查看器时出现以下事件之一,：
  
- 关闭窗体。
    
- 在窗体中加载新邮件。
    
- 完成保存操作。
    
- 发送一条消息。
    
每个事件类型对应于中的特定方法[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)，在表单查看器必须实现的接口之一。 当发生事件时，您查看器中的相应**IMAPIViewAdviseSink**方法的建议接收器的窗体呼叫。 例如，您查看器应包括在其显示新消息时，窗体调用[IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法。 
  
您的视图的建议方式，才有意义的您查看器; 接收器的实现没有任何标准的实现。 例如，在**OnNewMessage**可以更新当前文件夹的内容的表格，以包含新到达的消息的视图。 在[IMAPIViewAdviseSink::OnSubmitted](imapiviewadvisesink-onsubmitted.md)，当您收到的已提交的邮件事件，调用的方法可以将提交的邮件复制到已发送邮件文件夹。
  
发生更改的影响窗体时和您正在加载新消息时，窗体从您查看器收到通知。 若要通知窗体，请调用**IMAPIFormAdviseSink**的方法之一： [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md)或[IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md)。 调用**OnChange**传达状态。 例如，如果新邮件到达时，窗体文件夹中显示的最后一项，VCSTATUS_NEXT 标志设置，以告知窗体是现在下一个项目调用**OnChange** 。 
  
调用**OnActivateNext**警告表单转换为新消息的到达其可能也可能不能显示。 传递给**OnActivateNext**邮件的邮件类别。 
  
通过客户端应用程序的**IMAPIViewAdviseSink**接口来处理由客户端应用程序窗体对象的通知。 有关详细信息，请参阅[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)。
  

