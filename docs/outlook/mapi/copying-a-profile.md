---
title: 复制配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b722a157-0d92-404d-9075-39547241dbb7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 86f381eff1dab0144afe0f94dcd6dd54d1ad7fa8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424726"
---
# <a name="copying-a-profile"></a>复制配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建配置文件的一个方法就是从现有配置文件复制并更改必要的邮件服务和服务提供商。 复制配置文件涉及使用 MAPI 通过 [MAPIAdminProfiles](mapiadminprofiles.md) 函数提供的配置文件管理对象。 
  
 **复制配置文件**
  
1. 调用 **MAPIAdminProfiles** 以检索 **IProfAdmin** 接口指针。 
    
2. 调用 [IProfAdmin：：GetProfileTable](iprofadmin-getprofiletable.md) 以访问配置文件表。 
    
3. 使用 [SPropertyRestriction](spropertyrestriction.md) 结构构建属性限制，以将 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 与要复制的配置文件的名称相匹配。 
    
4. 调用 [IMAPITable：：FindRow](imapitable-findrow.md) 以在配置文件表中查找相应的行。 
    
5. 调用 [IProfAdmin：：CopyProfile](iprofadmin-copyprofile.md)，以 _lpszOldProfileName_ 参数 **PR_DISPLAY_NAME** 列的值。 
    

