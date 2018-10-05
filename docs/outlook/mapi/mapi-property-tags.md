---
title: MAPI 属性标记
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 380dad4c-7fbf-4c49-b67c-ab612c923499
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 96211d3b6e1e4dfbd4c93a98c8dd04de10eac884
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390014"
---
# <a name="mapi-property-tags"></a>MAPI 属性标记
  
**适用于**：Outlook 2013 | Outlook 2016 
  
属性标记为包含 16 至 31 唯一属性标识符和 0 到 15 下图中所示位中的属性类型 32 位数字。 
  
**属性标记元素**
  
![属性标记元素](media/amapi_10.gif "属性标记元素")
  
属性标记用于确定 MAPI 属性，并且每个属性必须具有一个，无论是否通过 MAPI、 客户端或服务提供商定义属性。 MAPI Mapitags.h 头文件; 中定义其属性的属性标记常量的一组这些属性被称为"MAPI 定义属性"。 
  
属性标记常量按照以保证一致性和易用性的命名约定。 有两个部分每个属性标记的名称： PR_ 前缀和一个或多个字符字符串，用于描述属性的内容。 使用下划线分隔多个字符的字符串。 例如，邮件收件人的地址类型的属性标记为**PR\_ADDRTYPE** ([PidTagOrgAddrtype](https://msdn.microsoft.com/library/d40b5707-e4d5-4746-88d4-8616a3789789%28Office.15%29.aspx)) 并指定其接收的每个出站邮件的副本的文件夹的条目标识符是**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))。
  
几宏可供帮助[PROP_TYPE](prop_type.md)、 [PROP_ID](prop_id.md)和[PROP_TAG](prop_tag.md)处理属性标记，它们之间。 **属性\_类型**属性标记; 中提取的属性类型**属性\_ID**提取标识符。 **PROP_TAG**构建属性标记从属性类型和标识符。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

