---
title: 实现容器一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eabbde74-49a1-4eeb-a01d-67e45ae4b343
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 72dc73b6ed8519be2d8010544fdd5dc5b7b0f759
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332884"
---
# <a name="implementing-a-container-one-off-table"></a>实现容器一次性表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要访问属于某个容器的一次性表, MAPI 会调用容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 以使用**IMAPITable**打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性交互. 当客户端应用程序尝试向容器中添加收件人时, 将要求您的容器返回其一次性表格。 如果容器允许任何收件人, 则提供程序可以返回自己的表实现或调用[IMAPISupport:: GetOneOffTable](imapisupport-getoneofftable.md)以返回 MAPI 实现。 
  
容器一次性表中的一组模板应反映特定容器可以包含的收件人的类型。 通常情况下, 这包括一个或两个模板, 这些模板用于创建单个邮件用户或通讯组列表。 这些模板的条目标识符保存在**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 属性中。 但是, 容器的含义并不局限于这些类型的条目。 他们可以保留其他类型的收件人或非收件人条目 (如目录)。 
  

