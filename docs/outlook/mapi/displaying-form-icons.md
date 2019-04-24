---
title: 显示表单图标
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 197e72ab-f9d6-4889-a677-0ce4c27b1aad
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c93912d19f0ad3c3231092c82f27cec9e3f15b3e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337042"
---
# <a name="displaying-form-icons"></a>显示表单图标

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在文件夹中显示邮件列表时, 如果通过标准 IPM 中的自定义邮件类区分邮件, 则对用户很有帮助。注释消息。 自定义邮件类对应于表单服务器, 窗体服务器提供图标来代表自己。 您可以在消息列表中显示这些图标, 以便在用户打开邮件之前向每个邮件的邮件类别发出警告。 通常情况下, 表单的**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性中的图标是应显示在邮件列表中的图标。 窗体还具有**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 属性, 当窗体在属性表中最小化时, 可以显示该属性。
  
 **为邮件类获取一个图标, 而不为该邮件类激活窗体服务器**
  
1. 调用[IMAPIFormMgr:: OpenFormContainer](imapiformmgr-openformcontainer.md)方法以获取指向[IMAPIFormContainer: IUnknown](imapiformcontaineriunknown.md)接口的指针。 
    
2. 调用[IMAPIFormContainer:: ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法以获取指向[IMAPIFormInfo: IMAPIProp](imapiforminfoimapiprop.md)接口的指针。 
    
3. 调用[IMAPIFormInfo:: MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md)方法以获取图标句柄。 
    
然后, 可以使用标准 Win32 api 显示图标。
  
> [!IMPORTANT]
> 拥有邮件类别的图标后, 请尽一切努力缓存该图标。 不缓存图标会严重影响客户端应用程序的性能。 缓存图标时, 请注意邮件类与其子类之间的关系。 例如, 如果 IPM。注释。若要解决此问题, 请执行 "取消邮件类" 操作。注意, 不要假定所有的 IPM 子类别。注意应使用 IPM 的图标。便笺. 
  

