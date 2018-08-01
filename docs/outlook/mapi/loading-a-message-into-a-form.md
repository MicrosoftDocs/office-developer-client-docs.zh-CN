---
title: 将邮件加载到表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4bdbe021-d694-4967-a105-4b24f1eebc44
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d677958b1a429201c05b5195c58bd7462d0f3d37
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776146"
---
# <a name="loading-a-message-into-a-form"></a>将邮件加载到表单

  
  
**适用于**： Outlook 
  
若要使用表单服务器表单加载现有消息，请使用以下策略之一。
  
- 调用[IMAPISession::PrepareForm](imapisession-prepareform.md)创建令牌，然后[IMAPISession::ShowForm](imapisession-showform.md)显示窗体。 
    
- 调用[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)。 
    
使用的**PrepareForm**和**ShowForm**策略而言容易，但其结果是相对于您的客户端模式的窗体中。 这是因为**ShowForm**将呼叫不会返回直到窗体已退出。 如果您需要异步处理窗体，请不要使用此策略。 
  
使用**LoadForm**策略是更加难以，因为方法需要多个参数。 这些参数指示窗体管理器启动正确的上下文中的正确表单服务器并显示正确的消息。 如果已运行窗体服务器，窗体管理器将加载邮件到窗体服务器无需启动的窗体服务器的新实例。 
  
指定要启动，则传递的邮件类的窗体服务器处理_lpszMessageClass_参数的内容中的目标服务器。 可以通过检索邮件要加载的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性确定适当的邮件类。 有时没有窗体服务器指定的邮件类仅窗体服务器的处理属于消息的超类别的邮件。 如果您愿意加载只能通过专门为了处理邮件的类的窗体服务器的邮件，，设置 MAPIFORM_EXACTMATCH 标志**LoadForm**呼叫中。 有关详细信息，请参阅[MAPI 邮件类](mapi-message-classes.md)。
  
 **LoadForm**还需要为查看者的消息网站和视图上下文，将值的指针的目标消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 和**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))属性。
  

