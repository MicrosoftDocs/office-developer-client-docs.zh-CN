---
title: MAPI 属性标记
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 380dad4c-7fbf-4c49-b67c-ab612c923499
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 96211d3b6e1e4dfbd4c93a98c8dd04de10eac884
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328231"
---
# <a name="mapi-property-tags"></a>MAPI 属性标记
  
**适用于**：Outlook 2013 | Outlook 2016 
  
属性标记是一个32位数, 其中包含位16到31中的唯一属性标识符和从0到15的属性类型, 如下图所示。 
  
**属性标记元素**
  
![属性标记元素](media/amapi_10.gif "属性标记元素")
  
属性标记用于标识 mapi 属性, 并且每个属性都必须有一个, 而不考虑属性是由 MAPI、客户端还是服务提供程序定义的。 MAPI 为 Mapitags 头文件中的属性定义一组属性标记常量;这些属性称为 "MAPI 定义的属性"。 
  
属性标记常量遵循用于一致性和易用性的命名约定。 每个属性标记的名称都有两个部分: 一个 PR_ 前缀和一个或多个描述该属性内容的字符字符串。 多个字符字符串之间用下划线分隔。 例如, 邮件收件人的地址类型的属性标记为**PR\_ADDRTYPE** ([PidTagOrgAddrtype](https://msdn.microsoft.com/library/d40b5707-e4d5-4746-88d4-8616a3789789%28Office.15%29.aspx)), 并且指定接收每个出站邮件副本的文件夹的条目标识符为**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))。
  
有几个宏可用于帮助处理属性标记, 其中包括[PROP_TYPE](prop_type.md)、 [PROP_ID](prop_id.md)和[PROP_TAG](prop_tag.md)。 **属性\_类型**从属性标记中提取属性类型;**"\_ID" ID**提取标识符。 **PROP_TAG**从属性类型和标识符生成属性标记。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

