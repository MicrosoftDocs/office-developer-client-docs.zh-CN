---
title: 实现One-Off表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57933d44-d47a-4e7f-ba95-b49b4934d0a5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c29feae84d81874988997409fd229b042a701640
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421639"
---
# <a name="implementing-one-off-tables"></a>实现One-Off表

**适用于**：Outlook 2013 | Outlook 2016 
  
提供程序可能实现一个或多个一键式表。 一对多表是用于创建收件人的一次使用模板的摘要列表，这些模板直接放入容器或传出邮件的收件人列表中。 一次使用模板是用户用于输入与特定地址类型相关的数据的表单。 当用户完成对模板的处理后，您的提供程序将创建新收件人并添加到邮件中。 通常，每个模板处理一个地址类型。 但是，模板可以处理多个类型，也可以让多个模板处理同一类型。 
  
您的提供程序必须支持其包括在一次方表中的每个模板的 **OpenEntry** 方法。 **OpenEntry 的** 实现应检索模板的显示表。 MAPI 使用显示表使模板对用户可见。 
  
尽管一键式表中的大多数行表示模板，但某些行可用于对模板进行分类或分组。 一次方表中的行是否表示模板由它的 **PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) 指示。 表示模板的行将PR_SELECTABLE设置为 TRUE;不表示模板的行将设置为 FALSE。
  
MAPI 定义三种类型的一键式表：
  
- 反映单个容器支持的模板的一对一表
    
- 反映提供程序支持的所有模板的一对一表 
    
- 反映配置文件中所有提供程序支持的所有模板以及 MAPI 支持的一些模板的一对表
    
前两种类型由支持创建收件人的提供程序实现，既可以在邮件上实现，也可以支持放入容器中。 您的提供程序可以在其一键式表中包含同一组模板或另一组模板。 这两种类型之间的主要区别在于，您的提供程序表应包含用于创建可在传出邮件中使用的收件人的模板，而容器表应包含用于创建要添加到容器的收件人的模板。 容器可能仅支持一组受限制的模板，但提供程序一次表应包含提供程序支持的每一个模板。
  
第三种类型的一对一表由 MAPI 实现;提供程序通过调用 [IMAPISupport：：GetOneOffTable 获取对它的访问](imapisupport-getoneofftable.md)权。 MAPI 一键式表是所有提供程序表的并列;它包括配置文件中每个提供程序支持的每一个模板。 它还包括 MAPI 支持的模板。 提供程序可以使用此表来表示容器请求的表。 但是，此表中的模板还可用于为传出邮件创建收件人。
  

