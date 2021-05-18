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
  
属性标记是一个 32 位数字，其中包含位 16 到 31 中的唯一属性标识符，以及位 0 到 15 的属性类型，如下图所示。 
  
**属性标记元素**
  
![属性标记元素](media/amapi_10.gif "属性标记元素")
  
属性标记用于标识 MAPI 属性，并且每个属性都必须有一个，无论该属性是由 MAPI、客户端还是服务提供商定义的。 MAPI 为 Mapitags.h 头文件中的属性定义一组属性标记常量;这些属性称为"MAPI 定义属性"。 
  
属性标记常量遵循命名约定，以确保一致性和易用性。 每个属性标记的名称有两个部分：一个PR_前缀和一个或多个描述属性内容的字符串。 用下划线分隔多个字符串。 例如，邮件收件人的地址类型的属性标记是 **PR \_ ADDRTYPE** ([PidTagOrgAddrtype](https://msdn.microsoft.com/library/d40b5707-e4d5-4746-88d4-8616a3789789%28Office.15%29.aspx)) 指定为接收每个出站邮件副本的文件夹的条目标识符为 **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) 。
  
可以使用一些宏来帮助处理属性标记，其中包括PROP_TYPE、PROP_ID 和[](prop_type.md) [PROP_TAG](prop_tag.md)。 [](prop_id.md) **PROP \_TYPE** 从属性标记中提取属性类型; **PROP \_ID** 提取标识符。 **PROP_TAG** 属性类型和标识符生成属性标记。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

