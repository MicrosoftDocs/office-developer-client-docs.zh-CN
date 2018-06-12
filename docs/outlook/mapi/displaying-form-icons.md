---
title: 显示窗体图标
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 197e72ab-f9d6-4889-a677-0ce4c27b1aad
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b2e79e5568de38bee9a97c9df2598b30f1ba1bdf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774809"
---
# <a name="displaying-form-icons"></a>显示窗体图标

  
  
**适用于**： Outlook 
  
在文件夹中显示的邮件的列表时, 很有用向用户如果从标准 IPM 区分自定义邮件类别的邮件。请注意消息。 自定义邮件类对应于窗体服务器和窗体服务器提供了图标表示本身。 用户打开邮件之前，您可以对每封邮件的邮件类的通知用户的邮件的列表中显示这些图标。 通常情况下，窗体的**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性中的图标是应显示在列表中的邮件。 窗体也有属性表中的窗体最小化时可显示**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 属性。
  
 **要获取为邮件类的图标，而不激活的邮件类的窗体服务器**
  
1. 调用[IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md)方法以获取一个指向[IMAPIFormContainer: IUnknown](imapiformcontaineriunknown.md)接口。 
    
2. 调用[IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法以获取一个指向[IMAPIFormInfo: IMAPIProp](imapiforminfoimapiprop.md)接口。 
    
3. 调用[IMAPIFormInfo::MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md)方法以获取图标句柄。 
    
然后可以使用标准 Win32 Api 显示的图标。
  
> [!IMPORTANT]
> 邮件类的图标后，请尽力缓存的图标。 未缓存图标会严重影响客户端应用程序的性能。 缓存图标时, 应谨慎的邮件类别以及其子类之间的关系。 例如，如果 IPM。Note.Meeting.Cancel 邮件类 IPM 回解决如此。请注意，不假定的所有 IPM 的子类。注意应该使用 IPM 图标。请注意。 
  

