---
title: 将邮件加载到表单中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4bdbe021-d694-4967-a105-4b24f1eebc44
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: afecd3b334dd2cf7b2953916872982e6459a8434
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355742"
---
# <a name="loading-a-message-into-a-form"></a>将邮件加载到表单中

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要使用窗体服务器将现有邮件加载到表单中, 请使用以下策略之一。
  
- 调用[IMAPISession::P repareform](imapisession-prepareform.md)以创建令牌, 然后[IMAPISession:: ShowForm](imapisession-showform.md)以显示表单。 
    
- 调用[IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md)。 
    
[! 注意] 使用**PrepareForm**和**ShowForm**策略相对简单, 但它会生成与客户端相关的模式窗体。 这是因为在窗体退出之前, 对**ShowForm**的调用不会返回。 如果需要异步处理窗体, 请不要使用此策略。 
  
使用**LoadForm**策略更加困难, 因为方法需要多个参数。 这些参数指示表单管理器在正确的上下文中启动正确的表单服务器, 并显示正确的消息。 如果表单服务器已在运行, 则表单管理器会将邮件加载到表单服务器中, 而不会启动新的表单服务器实例。 
  
若要指定要启动的窗体服务器, 请在_lpszMessageClass_参数的内容中传递由目标服务器处理的邮件类。 可以通过检索要加载的邮件的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性来确定相应的邮件类。 有时指定的邮件类别没有窗体服务器, 只是处理属于邮件超类的邮件的窗体服务器。 如果您想要仅由窗体服务器加载的邮件专门用于处理该类的邮件, 请在**LoadForm**调用中设置 MAPIFORM_EXACTMATCH 标志。 有关详细信息, 请参阅[MAPI 邮件类别](mapi-message-classes.md)。
  
 **LoadForm**还需要指向查看器的消息网站和查看上下文以及目标消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 和**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 的值的指针属性.
  

