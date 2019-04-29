---
title: 实现一次性表
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
# <a name="implementing-one-off-tables"></a>实现一次性表

**适用于**：Outlook 2013 | Outlook 2016 
  
提供程序可以实现一个或多个一次性表。 一次性表格是用于创建收件人的一次性模板的摘要列表, 这些模板可直接指向容器或传出邮件的收件人列表。 一次性模板是用户在输入与特定地址类型相关的数据时使用的表单。 在用户使用完模板后, 提供程序将创建新的收件人并将其添加到邮件中。 通常, 每个模板都处理一个地址类型。 但是, 模板可以处理多个类型或多个模板来处理同一类型。 
  
提供程序必须支持它包含在一次性表中的每个模板的**OpenEntry**方法。 **OpenEntry**的实现应检索模板的显示表。 MAPI 使用显示表格使该模板对用户可见。 
  
虽然一次性表中的大多数行都代表模板, 但某些行可用于对模板进行分类或分组。 一次性表中的行是否表示模板由其**PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) 列的值指示。 表示模板的行的 "PR_SELECTABLE" 列设置为 TRUE;不表示模板的行已将其设置为 FALSE。
  
MAPI 定义了三种类型的一次性表:
  
- 反映单个容器支持的模板的一次性表
    
- 反映提供程序支持的所有模板的一次性表 
    
- 一个一次性表, 反映配置文件支持中的所有提供程序和 MAPI 支持的所有模板
    
前两种类型由支持创建收件人的提供程序实现, 无论是在邮件上, 还是在容器中。 提供程序可以在其一次性表中包含相同的一组或一组不同的模板。 这两种类型的主要区别在于, 提供程序表应包含用于创建可用于传出邮件的收件人的模板, 并且您的容器表应包含用于创建要添加到容器中的收件人的模板。 容器仅支持一组有限的模板, 但提供程序的一次性表应包含提供程序支持的每个模板。
  
第三种类型的一次性表是由 MAPI 实现的;提供程序通过调用[IMAPISupport:: GetOneOffTable](imapisupport-getoneofftable.md)获取对它的访问权限。 MAPI 一次性表是所有提供程序表的并集;它包括配置文件中每个提供程序支持的每个模板。 它还包括 MAPI 支持的模板。 提供程序可以使用此表代替为容器请求的表。 但是, 此表中的模板还可用于创建传出邮件的收件人。
  

