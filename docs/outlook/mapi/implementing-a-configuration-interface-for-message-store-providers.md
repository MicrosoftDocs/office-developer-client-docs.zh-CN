---
title: 实现邮件存储提供程序的配置接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 508e6950-d483-4cbe-b817-8016f4aa5cd8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c349a03b0be465ed1262712372b6ee17a9812abd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415885"
---
# <a name="implementing-a-configuration-interface-for-message-store-providers"></a>实现邮件存储提供程序的配置接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
需要邮件存储提供程序来实现允许用户将邮件存储提供程序配置为在该用户的计算机上运行的接口。 通常，邮件存储提供程序是在将邮件存储提供程序添加到用户配置文件时配置的。 邮件存储提供程序的配置接口通常处理诸如为受保护的邮件存储设置用户名和密码、选择所需文件的路径以及创建它将使用的基础存储机制（如有必要）等任务。
  
您实现的配置接口通过邮件服务提供程序的 DLL 中的其他入口点访问。 有关详细信息，请参阅 [配置邮件服务](configuring-a-message-service.md)。 邮件存储提供程序的配置接口是邮件存储提供程序必须实现的唯一用户界面。
  
## <a name="see-also"></a>另请参阅



[邮件存储功能](message-store-features.md)

