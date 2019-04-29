---
title: 重新配置传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3d466bde-b70d-44b6-ba03-6ad8353ec759
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b35ca2bb52439cf2ba1750c6fad2883730c4c3f8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408408"
---
# <a name="reconfiguring-a-transport-provider"></a>重新配置传输提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您可以使用传输提供程序的状态对象来更改提供程序的一些属性。 可以更改的属性范围取决于提供程序的属性表附带的属性以及如何定义这些属性。 
  
 **重新配置活动传输提供程序**
  
1. 调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问状态表。 
    
2. 通过创建与目标提供程序的名称相匹配的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性限制, 找到要重新配置的传输提供程序的行。 
    
3. 调用[IMAPITable:: FindRow](imapitable-findrow.md)以检索相应的行。 
    
4. 检查目标传输提供程序的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中是否设置了 STATUS_SETTINGS_DIALOG 和 STATUS_VALIDATE_STATE 标志。 如果未设置 STATUS_SETTINGS_DIALOG, 则传输提供程序不显示配置属性表。 如果未设置 STATUS_VALIDATE_STATE, 则无法执行动态重新配置。
    
5. 如果设置了 STATUS_SETTINGS_DIALOG, 则调用[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)以显示传输提供程序的属性表, 并允许用户进行更改。 
    
6. 在用户完成重新配置之后, 调用[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)如果设置了 STATUS_VALIDATE_STATE, 则传递 CONFIG_CHANGED。 
    

