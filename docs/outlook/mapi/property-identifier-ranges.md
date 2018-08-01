---
title: 属性标识符范围
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c01e95bb-be25-490d-880b-60674f890258
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aee199cbbd05606d20378023f103fa122f1457f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778566"
---
# <a name="property-identifier-ranges"></a>属性标识符范围

  
  
**适用于**： Outlook 
  
下表总结了不同属性标识符，描述每个范围中的属性的所有者的范围。
  
|**标识符范围**|**说明**|
|:-----|:-----|
|0000  <br/> |通过 MAPI 供特殊值**PR_NULL**。  <br/> |
|0001-0BFF  <br/> |定义的 MAPI 邮件信封属性。  <br/> |
|0 C 00-0DFF  <br/> |定义的 MAPI 的收件人属性。  <br/> |
|0E00-0FFF  <br/> |非可传送消息定义 MAPI 的属性。  <br/> |
|1000-2FFF  <br/> |定义的 MAPI 邮件内容属性。  <br/> |
|3000-3FFF  <br/> |邮件和收件人的 MAPI 定义以外的对象的属性。  <br/> |
|4000-57FF  <br/> |邮件信封属性由传输提供程序定义。  <br/> |
|5800-5FFF  <br/> |由传输和通讯簿提供程序定义的收件人属性。  <br/> |
|6000-65FF  <br/> |定义由客户端的非可传送邮件属性。  <br/> |
|6600-67FF  <br/> |定义由服务提供商的非可传送属性。 这些属性可以是用户可见或不可见。  <br/> |
|6800-7BFF  <br/> |自定义邮件类定义这些类的创建者的消息内容属性。  <br/> |
|7C 00-7FFF  <br/> |自定义邮件类定义这些类的创建者的非可传送属性。  <br/> |
|8000-FFFE  <br/> |属性定义由客户端和偶尔服务通过[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法按姓名标识提供程序。  <br/> |
|FFFF  <br/> |通过 MAPI 供 PROP_ID_INVALID 的特殊的错误值。  <br/> |
   
3000 之间的范围和 3FFF 供与邮件或收件人不相关的属性。 MAPI 将此范围分为子范围的类型的对象;下表显示了此进一步细分。 
  
|**标识符范围**|**属性类型**|
|:-----|:-----|
|3000-33FF  <br/> |多个对象，如**PR_DISPLAY_NAME**和**PR_ENTRYID**显示的常见属性。  <br/> |
|3400-35FF  <br/> |消息存储库属性  <br/> |
|3600-36FF  <br/> |文件夹和通讯簿容器属性  <br/> |
|3700-38FF  <br/> |附件属性  <br/> |
|3900-39FF  <br/> |通讯簿属性  <br/> |
|3A00-3BFF  <br/> |消息的用户属性  <br/> |
|3C 00-3CFF  <br/> |通讯组列表属性  <br/> |
|三维 00-3DFF  <br/> |配置文件属性  <br/> |
|3E00-3FFF  <br/> |状态对象属性  <br/> |
   

