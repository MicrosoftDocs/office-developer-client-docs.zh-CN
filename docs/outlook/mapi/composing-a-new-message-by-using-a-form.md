---
title: 使用窗体撰写新邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c92181c4-79ca-4310-8bf1-2bc335c8e0cd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1c5ba8631ba39309b7131440f04564f80b5dbb57
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412798"
---
# <a name="composing-a-new-message-by-using-a-form"></a>使用窗体撰写新邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要使用窗体撰写新邮件，请首先创建新的自定义邮件对象。
  
 **使用窗体撰写新邮件**
  
1. 调用表单管理器的 [IMAPIFormMgr：：ResolveMessageClass](imapiformmgr-resolvemessageclass.md) 方法来检索指向表单信息对象的指针 — 一个实现 [IMAPIFormInfo ： IMAPIProp 接口](imapiforminfoimapiprop.md) 的对象。 
    
2. 对 [IMAPIFormMgr：：CreateForm](imapiformmgr-createform.md)的调用中传递指向表单信息对象的指针。 **CreateForm** 加载相应的表单服务器。 此外，将接口标识符传递给 **CreateForm** 以指定用于访问新邮件的接口。 通常，通过向 **CreateForm** 传递IID_IPersistMessage [IPersistMessage ： IUnknown。](ipersistmessageiunknown.md)
    
3. 通过调用其 [IPersistMessage：：Save](ipersistmessage-save.md) 方法保存新邮件。 窗体服务器应在创建邮件时为邮件的必需属性设置值。 
    
4. 使用以下两种策略之一加载消息 [：IMAPIFormMgr：：LoadForm](imapiformmgr-loadform.md) 或 [IMAPISession：:P repareForm，](imapisession-prepareform.md) 后跟 [IMAPISession：：ShowForm](imapisession-showform.md)。 有关这些策略详细信息，请参阅 [将邮件加载到窗体中](loading-a-message-into-a-form.md)。
    
> [!NOTE]
> 在将新的自定义邮件加载到表单服务器时，性能会提高，因为在 **ResolveMessageClass** 和 **CreateForm** 调用所需的处理过程中，您已经有机会获取有关邮件的一些信息（如邮件类）。 因此，在调用 **LoadForm** 之前，可以先简化所需的处理，如将邮件加载到窗体主题 [中所述](loading-a-message-into-a-form.md)。 
  

