---
title: 使用表单撰写新邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c92181c4-79ca-4310-8bf1-2bc335c8e0cd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f4b9cb00512838e6b54c0cc910b8f7279120db3c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774671"
---
# <a name="composing-a-new-message-by-using-a-form"></a>使用表单撰写新邮件

  
  
**适用于**： Outlook 
  
若要使用窗体撰写新邮件，请首先创建一个新的自定义消息对象。
  
 **撰写新邮件使用窗体**
  
1. 调用该窗体管理器的[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法来检索指向窗体信息对象 — 一个对象，实现[IMAPIFormInfo: IMAPIProp](imapiforminfoimapiprop.md)接口。 
    
2. 将指针传递给[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)调用中的窗体信息对象。 **CreateForm**加载的相应窗体服务器。 此外，将接口标识传递给**CreateForm**来指定要用于访问新邮件的接口。 通常情况下，您请求[IPersistMessage: IUnknown](ipersistmessageiunknown.md)通过将 IID_IPersistMessage 传递给**CreateForm**。
    
3. 通过调用其[IPersistMessage::Save](ipersistmessage-save.md)方法保存新邮件。 在创建邮件时，窗体服务器应设置消息的必需属性的值。 
    
4. 使用两种策略之一加载消息： [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)或[IMAPISession::PrepareForm](imapisession-prepareform.md)后跟[IMAPISession::ShowForm](imapisession-showform.md)。 有关这些策略的详细信息，请参阅[加载邮件到窗体](loading-a-message-into-a-form.md)。
    
> [!NOTE]
> 有机会性能提升时将新的自定义消息加载到窗体服务器，因为您已经有机会获取一些有关邮件信息将 — 例如其邮件类别 —**所需的处理期间ResolveMessageClass**和**CreateForm**呼叫。 因此，您将能够简化过去[加载邮件到窗体](loading-a-message-into-a-form.md)的主题中所述调用**LoadForm**之前所需的处理。 
  

