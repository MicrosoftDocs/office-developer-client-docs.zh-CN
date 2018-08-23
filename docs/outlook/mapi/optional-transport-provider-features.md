---
title: 可选的传输提供程序功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0bec2c17-b41c-4e46-8961-a55bde1f7326
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b55e6518ee1f3f59ef0459b3aeb68461f00a7ab3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566822"
---
# <a name="optional-transport-provider-features"></a>可选的传输提供程序功能

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
传输提供程序可以实现的可选功能包括：
  
- 注册消息和特定于传输提供程序的收件人选项。
    
- 维护配置文件，如有必要，以存储配置信息和消息系统的凭据。
    
- 执行任何的所需的邮件系统的凭据进行验证。
    
- 使用[IMAPISupport::Notify](imapisupport-notify.md)方法支持感客户端应用程序的事件通知。 
    
- 显示配置属性表和向导的对话框，以便用户能够配置传输提供程序的设置。
    
- 提供客户端应用程序的邮件送达报告。
    

