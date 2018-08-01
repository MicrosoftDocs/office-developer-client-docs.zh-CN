---
title: 实现邮件存储区提供程序的配置接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 508e6950-d483-4cbe-b817-8016f4aa5cd8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f7151841eef180a78a13ad161d197af783decfb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775762"
---
# <a name="implementing-a-configuration-interface-for-message-store-providers"></a>实现邮件存储区提供程序的配置接口

  
  
**适用于**： Outlook 
  
消息存储提供程序所需实现允许用户配置要在该用户的计算机上运行的消息存储提供程序的接口。 通常情况下，消息存储提供程序配置的消息存储提供程序添加到用户的配置文件时。 消息存储提供程序的配置界面通常处理任务，例如用户名和密码的受保护的邮件存储区中，选择所需文件的路径设置并创建基础存储机制它将使用，如有必要。
  
您实现配置界面来访问邮件服务提供商的 DLL 中的其他入口点。 有关详细信息，请参阅[配置邮件服务](configuring-a-message-service.md)。 消息存储提供程序的配置接口是消息存储提供程序必须实现的唯一用户界面。
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

