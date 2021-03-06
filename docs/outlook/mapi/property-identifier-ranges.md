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
ms.openlocfilehash: cdf1eae945cddf9eb76a2b7a2532d5dc6568beac
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422703"
---
# <a name="property-identifier-ranges"></a>属性标识符范围

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
下表总结了属性标识符的不同范围，并描述了每个范围中属性的所有者。
  
|**标识符范围**|**说明**|
|:-----|:-----|
|0000  <br/> |由 MAPI 保留，用于特殊 **PR_NULL。**  <br/> |
|0001 - 0BFF  <br/> |MAPI 定义的邮件信封属性。  <br/> |
|0C00 - 0DFF  <br/> |由 MAPI 定义的收件人属性。  <br/> |
|0E00 - 0FFF  <br/> |MAPI 定义的不可传输邮件属性。  <br/> |
|1000 - 2FFF  <br/> |MAPI 定义的邮件内容属性。  <br/> |
|3000 - 3FFF  <br/> |除 MAPI 定义的邮件和收件人外的对象的属性。  <br/> |
|4000 - 57FF  <br/> |由传输提供程序定义的邮件信封属性。  <br/> |
|5800 - 5FFF  <br/> |由传输和通讯簿提供程序定义的收件人属性。  <br/> |
|6000 - 65FF  <br/> |客户端定义的不可传输邮件属性。  <br/> |
|6600 - 67FF  <br/> |服务提供商定义的不可传输属性。 这些属性对于用户可见或不可见。  <br/> |
|6800 - 7BFF  <br/> |由这些类的创建者定义的自定义邮件类的邮件内容属性。  <br/> |
|7C00 - 7FFF  <br/> |由这些类的创建者定义的自定义邮件类的不可传输属性。  <br/> |
|8000 - FFFE  <br/> |由客户端和有时通过 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 和 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法按名称标识的属性。  <br/> |
|FFFF  <br/> |由 MAPI 保留，用于特殊错误PROP_ID_INVALID。  <br/> |
   
3000 到 3FFF 之间的范围为与邮件或收件人不相关的属性保留。 MAPI 按对象类型将此范围划分为子范围;下表显示了此进一步细分。 
  
|**标识符范围**|**属性类型**|
|:-----|:-----|
|3000 - 33FF  <br/> |出现在多个对象上的常见属性，如 **PR_DISPLAY_NAME** 和 **PR_ENTRYID**。  <br/> |
|3400 - 35FF  <br/> |邮件存储属性  <br/> |
|3600 - 36FF  <br/> |文件夹和通讯簿容器属性  <br/> |
|3700 - 38FF  <br/> |附件属性  <br/> |
|3900 - 39FF  <br/> |通讯簿属性  <br/> |
|3A00 - 3BFF  <br/> |邮件传递用户属性  <br/> |
|3C00 - 3CFF  <br/> |通讯组列表属性  <br/> |
|3D00 - 3DFF  <br/> |配置文件属性  <br/> |
|3E00 - 3FFF  <br/> |Status 对象属性  <br/> |
   

