---
title: 邮件服务实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb529cc7-ad09-4f86-89bc-0e8ad29a3f38
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6ba2f9542fd021c544d73d8208ed356a7bf95309
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776504"
---
# <a name="message-service-implementation"></a>邮件服务实现

  
  
**适用于**： Outlook 
  
消息服务是组合在一起以简化安装和配置的一个或多个相关的服务提供商。 所有服务提供程序应都包含在邮件服务。
  
若要实现与一个或多个提供程序的消息服务，请使用以下过程：
  
1. 设计邮件服务，确定的数量和要包括的服务提供商的类型。 有关如何设计的消息服务的详细信息，请参阅[Designing 消息服务](designing-a-message-service.md)。
    
2. 创建用于消息服务中安装的服务提供程序安装程序。 有关编写消息服务安装程序的详细信息，请参阅[支持的消息服务安装](supporting-message-service-installation.md)。 
    
3. 创建执行配置入口点函数。 有关写入消息服务的条目的详细信息指向函数，请参阅[支持的消息服务配置](supporting-message-service-configuration.md)和[MSGSERVICEENTRY](msgserviceentry.md)。 
    
4. 创建公共头文件包含属性标记和消息服务支持的任何自定义属性的有效值的说明。 
    
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

