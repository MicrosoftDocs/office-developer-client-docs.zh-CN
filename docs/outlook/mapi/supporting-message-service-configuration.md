---
title: 支持邮件服务配置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb6ab537-2876-474b-be7a-84734ace2bae
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: aa1a433e90eda24f1199783bc604e047deb03ecd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350608"
---
# <a name="supporting-message-service-configuration"></a>支持邮件服务配置
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要支持邮件服务配置, 请使用以下过程:
  
1. 实现符合[MSGSERVICEENTRY](msgserviceentry.md)原型的入口点函数。 邮件服务入口点函数可管理对配置数据的访问, 并在以下情况下调用: 
    
   - 当客户端登录以检索信息以配置邮件服务时。
    
   - 当客户端想要查看或更改配置属性时。 
    
   尽管大多数邮件服务都会提供入口点函数, 但这些函数并不是绝对必需的。 邮件服务可以以其他方式提供对配置数据的访问权限。 但是, 使用入口点函数可标准化和简化配置过程。
    
   MAPI 预期所有邮件服务入口点函数能够存储和检索与它们的邮件服务关联的配置文件节中的属性。 您可以交互、以编程方式或交互方式和编程方式支持此功能。
    
   若要支持交互式配置, 请提供显示配置邮件服务所涉及的属性的属性表。 作为选项, 您还可以为每个可配置的提供程序提供属性表。 某些邮件服务将用户限制为配置属性的只读视图;其他邮件服务允许用户进行更改。
    
   若要支持编程配置, 您的消息服务入口点函数必须能够正常工作, 而无需用户干预。 如果您的消息服务可由配置文件向导调用, 则必须支持编程配置。 如果您的邮件服务不允许其自身使用配置文件向导进行配置, 则可以选择是否支持编程配置。
    
   有关如何在邮件服务入口点函数中支持配置的详细信息, 请参阅[MSGSERVICEENTRY](msgserviceentry.md)。
    
2. 通过在 "邮件服务" 部分中添加以下条目, 在 mapisvc.inf 配置文件中发布您的邮件服务入口点函数的名称:
    
   `PR_SERVICE_ENTRY_NAME=<name of message service>`
    
3. 创建一个或多个用于显示配置数据的属性表对话框。
    
4. 如果您希望允许配置文件向导配置您的邮件服务, 请执行以下任务:
    
   - 实现符合[WIZARDENTRY](wizardentry.md)原型的入口点函数。 
    
   - 实现符合[SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型的标准 Windows 对话框过程。 
    
   - 增强您的消息服务入口点函数以响应其他事件。
    
## <a name="see-also"></a>另请参阅

- [邮件服务实现](message-service-implementation.md)

