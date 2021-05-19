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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418993"
---
# <a name="supporting-message-service-configuration"></a>支持邮件服务配置
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要支持邮件服务配置，请使用以下过程：
  
1. 实现符合 [MSGSERVICEENTRY](msgserviceentry.md) 原型的入口点函数。 邮件服务入口点函数管理对配置数据的访问，在下列情况下调用： 
    
   - 客户端登录以检索信息以配置邮件服务时。
    
   - 客户端想要查看或更改配置属性时。 
    
   虽然大多数邮件服务将提供入口点功能，但并非严格要求它们。 邮件服务可以通过其他方式提供对配置数据的访问权限。 但是，使用入口点函数可以标准化并简化配置过程。
    
   MAPI 期望所有邮件服务入口点功能能够存储和检索与其邮件服务关联的配置文件节中的属性。 你可以以交互方式、以编程方式或以交互方式和以编程方式支持此功能。
    
   若要支持交互式配置，属性表显示配置邮件服务所涉及的属性。 作为一个选项，您还可以提供每个可配置提供程序的属性表。 某些邮件服务将用户限制为配置属性的只读视图;其他邮件服务允许用户进行更改。
    
   若要支持编程配置，邮件服务入口点函数必须能够在用户干预的情况下工作。 如果邮件服务可以通过配置文件向导调用，则必须支持编程配置。 如果邮件服务不允许使用配置文件向导配置自身，您可以选择是否支持编程配置。
    
   若要详细了解如何支持邮件服务入口点函数中的配置，请参阅[MSGSERVICEENTRY。](msgserviceentry.md)
    
2. 在邮件服务部分包含以下条目，以在 Mapisvc.inf 配置文件中发布邮件服务入口点函数的名称：
    
   `PR_SERVICE_ENTRY_NAME=<name of message service>`
    
3. 创建一个或多个属性表用于显示配置数据的对话框。
    
4. 如果要允许配置文件向导配置邮件服务，请执行以下任务：
    
   - 实现符合 [WIZARDENTRY](wizardentry.md) 原型的入口点函数。 
    
   - 实现一个Windows [SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型的标准对话框过程。 
    
   - 增强邮件服务入口点功能以响应其他事件。
    
## <a name="see-also"></a>另请参阅

- [邮件服务实现](message-service-implementation.md)

