---
title: 实现容器One-Off表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eabbde74-49a1-4eeb-a01d-67e45ae4b343
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 72dc73b6ed8519be2d8010544fdd5dc5b7b0f759
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417418"
---
# <a name="implementing-a-container-one-off-table"></a>实现容器One-Off表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要访问属于其中一个容器的一次表，MAPI 调用容器的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法，以使用 **IMAPITable** 接口打开 **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 当客户端应用程序尝试将收件人添加到容器时，会要求容器返回其一次表。 如果容器允许任何收件人，则提供程序可以返回其自己的表实现，也可以调用 [IMAPISupport：：GetOneOffTable](imapisupport-getoneofftable.md) 返回 MAPI 实现。 
  
容器一对一表中的模板集应反映特定容器可以保留的收件人类型。 通常，这包括一个或两个模板，即用于创建单个邮件用户或通讯组列表的模板。 这些模板的条目标识符位于 **PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和 **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 属性中。 但是，容器并不限于这些类型的条目。 它们可以保留其他类型的收件人或非收件人条目，如目录。 
  

