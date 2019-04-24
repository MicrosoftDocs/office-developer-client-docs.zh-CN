---
title: 配置邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d68892e3-7c87-4b3a-a691-bff92f83ed00
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4c3d30c7111e7b26886cbfb069ec2822d2ee0234
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335110"
---
# <a name="configuring-a-message-service"></a>配置邮件服务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **在邮件服务中配置所有服务提供程序**
  
- 调用[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)。 如果配置所需的所有数据都以编程方式使用, 则可以选择是否显示用户界面。 但是, 如果一个或多个提供程序的某些信息不可用, 请确保设置了 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 标志。 如果所需的配置数据不可用, 则隐含用户界面将导致未配置的邮件服务。
    
 **在邮件服务中配置单个服务提供程序**
  
1. 调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问服务提供程序的状态对象。 
    
2. 调用[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)以显示服务提供程序的属性表。 
    
有关使用 status 对象的详细信息, 请参阅[status Table 和 status 对象](status-table-and-status-objects.md)。
  

