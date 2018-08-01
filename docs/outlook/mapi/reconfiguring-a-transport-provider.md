---
title: 重新配置传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3d466bde-b70d-44b6-ba03-6ad8353ec759
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ec5a431d04799e3f19c23dd0437aeac13fbf0968
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778597"
---
# <a name="reconfiguring-a-transport-provider"></a>重新配置传输提供程序

  
  
**适用于**： Outlook 
  
您可以使用传输提供程序的状态对象更改的一些提供程序的属性。 可以更改属性的范围取决于包含在提供程序的属性表和如何定义这些属性的属性。 
  
 **若要重新配置的活动传输提供程序**
  
1. 调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。 
    
2. 找到要通过创建匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性限制重新配置的传输提供程序的行与目标提供程序的名称。 
    
3. 调用[IMAPITable::FindRow](imapitable-findrow.md)检索相应行。 
    
4. 目标传输提供程序的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中设置了 STATUS_SETTINGS_DIALOG 和 STATUS_VALIDATE_STATE 标志的检查。 如果未设置 STATUS_SETTINGS_DIALOG，传输提供程序不显示配置属性表。 如果未设置 STATUS_VALIDATE_STATE，不能执行动态重新配置。
    
5. 如果设置 STATUS_SETTINGS_DIALOG，调用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)显示传输提供程序的属性表，并允许用户做出更改。 
    
6. 用户已重新配置完成后，调用[IMAPIStatus::ValidateState](imapistatus-validatestate.md) ，如果设置 STATUS_VALIDATE_STATE，传递 CONFIG_CHANGED。 
    

