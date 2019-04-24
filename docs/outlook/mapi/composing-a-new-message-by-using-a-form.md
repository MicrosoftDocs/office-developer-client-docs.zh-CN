---
title: 使用表单撰写新邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c92181c4-79ca-4310-8bf1-2bc335c8e0cd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1c5ba8631ba39309b7131440f04564f80b5dbb57
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335124"
---
# <a name="composing-a-new-message-by-using-a-form"></a>使用表单撰写新邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要使用表单撰写新邮件, 请首先创建一个新的自定义邮件对象。
  
 **使用表单撰写新邮件**
  
1. 调用表单管理器的[IMAPIFormMgr:: ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法以检索指向表单信息对象的指针, 即实现[IMAPIFormInfo: IMAPIProp](imapiforminfoimapiprop.md)接口的对象。 
    
2. 在对[IMAPIFormMgr:: CreateForm](imapiformmgr-createform.md)的调用中传递指向表单信息对象的指针。 **CreateForm**加载适当的表单服务器。 此外, 将接口标识符传递给**CreateForm** , 以指定用于访问新邮件的接口。 通常情况下, 通过将 IID_IPersistMessage 传递给**CreateForm**来请求[IPersistMessage: IUnknown](ipersistmessageiunknown.md) 。
    
3. 通过调用[IPersistMessage:: Save](ipersistmessage-save.md)方法保存新邮件。 窗体服务器在创建邮件时, 应设置邮件的必需属性的值。 
    
4. 使用以下两个策略之一加载邮件: [IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md)或[IMAPISession::P repareform](imapisession-prepareform.md)后接[IMAPISession:: ShowForm](imapisession-showform.md)。 有关这些策略的详细信息, 请参阅将[邮件加载到表单](loading-a-message-into-a-form.md)中。
    
> [!NOTE]
> 将新的自定义邮件加载到表单服务器中时, 会有机会提高性能, 因为在处理的过程中, 您已经有机会获取有关邮件 (如邮件类) 的某些信息。 **ResolveMessageClass**和**CreateForm**调用。 因此, 您将能够在调用**LoadForm**之前, 简化在将[邮件加载到表单](loading-a-message-into-a-form.md)中所述的步骤之前所需的处理过程。 
  

