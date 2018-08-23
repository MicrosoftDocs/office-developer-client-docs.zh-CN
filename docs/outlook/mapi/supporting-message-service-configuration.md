---
title: 支持的消息服务配置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb6ab537-2876-474b-be7a-84734ace2bae
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6f9ac5d9cef09ce6d4f3006ecc804db6291cae77
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579338"
---
# <a name="supporting-message-service-configuration"></a>支持的消息服务配置
  
**适用于**： Outlook 2013 |Outlook 2016 
  
若要支持消息服务配置，请使用以下过程：
  
1. 实现符合[MSGSERVICEENTRY](msgserviceentry.md)原型入口点函数。 消息服务入口点函数管理访问配置数据，并在以下情况下调用： 
    
   - 当客户端登录时检索配置消息服务的信息。
    
   - 当客户端要查看或更改的配置属性。 
    
   尽管大多数消息服务将提供入口点函数，如它们应，这些函数不严格需要。 消息服务可提供对其他方式配置数据访问。 但是，使用入口点函数标准化和简化的配置过程。
    
   MAPI 要求所有邮件服务入口点函数能够从存储和检索属性与其消息服务关联的配置文件部分。 您可以支持此功能，以交互方式，以编程方式或两个以交互方式以及通过编程方式。
    
   若要支持交互式配置，提供显示配置您的消息服务所涉及的属性的属性表。 作为一个选项，还可以为每个可配置提供程序提供属性表。 某些消息服务将用户限制为只读的视图的配置属性;其他消息服务允许用户进行更改。
    
   若要支持编程配置，您消息服务入口点函数必须能够无需用户干预工作。 如果您的消息服务可由配置文件向导，您必须支持编程配置。 如果您的消息服务不允许自身来使用配置文件向导进行配置，则可以选择支持编程配置。
    
   有关如何在消息服务项中支持配置的详细信息指向函数，请参阅[MSGSERVICEENTRY](msgserviceentry.md)。
    
2. Mapisvc.inf 配置文件中发布您的消息服务入口点函数的名称，通过在邮件服务部分中包含以下条目：
    
   `PR_SERVICE_ENTRY_NAME=<name of message service>`
    
3. 创建一个或多个属性表对话框显示的配置数据。
    
4. 如果您想要让配置文件向导以配置邮件服务，请执行以下任务：
    
   - 实现符合[WIZARDENTRY](wizardentry.md)原型入口点函数。 
    
   - 实现[SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型符合标准的 Windows 对话框框过程。 
    
   - 增强对其他事件作出响应您消息服务入口点函数。
    
## <a name="see-also"></a>另请参阅

- [邮件服务实现](message-service-implementation.md)

