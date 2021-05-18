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
  
可以使用传输提供程序的状态对象更改提供程序的一些属性。 可更改的属性范围取决于提供程序的提供程序属性中包含的属性属性表定义这些属性的方式。 
  
 **重新配置活动传输提供程序**
  
1. 调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 以访问状态表。 
    
2. 通过创建与 PR_DISPLAY_NAME ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 与目标提供程序名称相匹配的属性限制，找到要重新配置的传输提供程序的行。 
    
3. 调用 [IMAPITable：：FindRow](imapitable-findrow.md) 以检索相应的行。 
    
4. 检查目标STATUS_SETTINGS_DIALOG [PidTagResourceMethods](pidtagresourcemethods-canonical-property.md) STATUS_VALIDATE_STATE 属性中是否设置了PR_RESOURCE_METHODS (和) 标志。 如果未STATUS_SETTINGS_DIALOG，则传输提供程序不会显示配置属性表。 如果未STATUS_VALIDATE_STATE，则不能执行动态重新配置。
    
5. 如果STATUS_SETTINGS_DIALOG，请调用 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 以显示传输提供程序属性表并允许用户进行更改。 
    
6. 在用户完成重新配置后，如果已设置STATUS_VALIDATE_STATE，则调用[IMAPIStatus：：ValidateState，CONFIG_CHANGED。](imapistatus-validatestate.md) 
    

