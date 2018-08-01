---
title: 配置邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d68892e3-7c87-4b3a-a691-bff92f83ed00
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fd87d169cd5131c6e1c8ca45a35dded96a295c57
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774664"
---
# <a name="configuring-a-message-service"></a>配置邮件服务

  
  
**适用于**： Outlook 
  
 **配置邮件服务中的所有服务提供商**
  
- 调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)。 如果所有所需的配置数据以编程方式为可用，则可以选择显示用户界面。 但是，如果一个或多个提供程序的信息的一些不可用，请确保您设置 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 标志。 不可用导致的未配置的邮件服务所需的配置数据时，禁止显示用户界面。
    
 **若要配置单个服务提供程序中的消息服务**
  
1. 调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问服务提供商的状态对象。 
    
2. 调用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)以显示服务提供商的属性表。 
    
有关使用状态对象的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。
  

