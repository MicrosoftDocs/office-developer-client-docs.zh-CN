---
title: 实现一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57933d44-d47a-4e7f-ba95-b49b4934d0a5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b86ec02c0255d892c42a9be9610d31b76041822c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579107"
---
# <a name="implementing-one-off-tables"></a>实现一次性表

**适用于**： Outlook 2013 |Outlook 2016 
  
您的提供商可能实现一个或多个一次性表。 一次性表是一次性模板用于创建收件人，直接将容器或到收件人列表中的传出邮件的摘要列表。 一次性模板是地址的输入与特定类型相关的数据表单用户使用。 用户已完成时使用的模板，您的提供程序创建新收件人并将其添加到邮件。 通常，每个模板处理单个地址类型。 但是，也可能模板可以处理多个类型或多个要处理的相同类型的模板。 
  
您的提供商必须支持它包括一次性表中的每个模板**OpenEntry**方法。 **OpenEntry**的实现应检索显示表格模板。 MAPI 使用显示表以使该模板对用户可见。 
  
虽然大部分一次性表中的行代表模板，但某些行可用于分类，或组，模板。 一次性表中的行代表由其**PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) 列的值指示模板。 代表模板的各行都设置为 TRUE; 的 PR_SELECTABLE 栏行不表示模板已设置为 FALSE。
  
MAPI 定义三种类型的一次性表：
  
- 一个一次性表，反映了单个容器所支持的模板
    
- 反映您的提供商支持的模板的所有一次性表 
    
- 一个一次性表，反映的所有模板的所有配置文件中提供程序支持 plus 某些的 MAPI 支持
    
由提供程序支持创建收件人，到一条消息，或到容器实现的前两个的类型。 您的提供商可以包含一组相同或不同的模板集及其一次性表中。 两种类型的主要区别是提供程序表应包含模板，用于创建可用于待发邮件的收件人和容器表应包含模板，用于创建收件人添加到您的容器。 容器可能仅支持一组有限的模板，但提供程序一次性表应包含每个模板提供程序支持。
  
MAPI; 由实现一次性表的第三种类型提供对其进行访问通过调用[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)。 MAPI 一次性表是全都的提供程序表中。它包括配置文件中的每个提供程序支持的每个模板。 它还包括支持 MAPI 的模板。 您的提供商可以使用此替换为容器请求的表的表。 但是，此表中的模板还可用于创建待发邮件的收件人。
  

