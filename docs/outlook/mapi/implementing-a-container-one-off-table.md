---
title: 实现容器一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eabbde74-49a1-4eeb-a01d-67e45ae4b343
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d468943f84f1d23f1b4b84881e69cee0041a5bae
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576594"
---
# <a name="implementing-a-container-one-off-table"></a>实现容器一次性表

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
若要访问一次性表属于您容器之一，MAPI 调用的容器[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法使用**IMAPITable**打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性接口。 您的容器要求客户端应用程序尝试将收件人添加到容器时返回其一次性表。 如果容器允许任何收件人，您的提供商可以返回它自己的表实现或呼叫[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)返回 MAPI 实现。 
  
容器一次性表中的模板集应反映特定容器可以包含的收件人的类型。 通常，这包括一个或两个模板，用于创建单个邮件用户或通讯组列表的模板。 **PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 属性中保留这些模板的项标识符。 但是，容器不是限制为这些类型的项。 它们可以保存其他类型的收件人或非收件人条目，如目录。 
  

