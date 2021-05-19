---
title: 邮件服务实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb529cc7-ad09-4f86-89bc-0e8ad29a3f38
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ef3820afbd4ae7ff04a3f54071e56f4e0a856109
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434030"
---
# <a name="message-service-implementation"></a>邮件服务实现

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件服务是分组在一起以简化安装和配置的一个或多个相关服务提供商。 所有服务提供程序都应包含在邮件服务中。
  
若要使用一个或多个提供程序实现邮件服务，请使用以下过程：
  
1. 设计邮件服务，确定要包含的服务提供商的数量和类型。 若要详细了解如何设计邮件服务，请参阅 [设计邮件服务](designing-a-message-service.md)。
    
2. 创建安装程序以在邮件服务中安装服务提供程序。 有关编写邮件服务安装程序的信息，请参阅 [支持邮件服务安装](supporting-message-service-installation.md)。 
    
3. 创建入口点函数以执行配置。 有关编写邮件服务入口点函数的详细信息，请参阅[支持邮件服务配置](supporting-message-service-configuration.md)和[MSGSERVICEENTRY。](msgserviceentry.md) 
    
4. 创建一个公共头文件，其中包含邮件服务支持的任何自定义属性的属性标记和有效值说明。 
    
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

