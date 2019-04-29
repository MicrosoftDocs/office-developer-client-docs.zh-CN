---
title: 使用筛选器设置表位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0d66124b-a018-4db4-b55b-a0e5ed467e14
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6b21d6746baf438af438787d966d9af886d4a74f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425468"
---
# <a name="setting-a-table-position-with-a-filter"></a>使用筛选器设置表位置

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表用户可以将光标移动到与一组筛选条件相匹配的行。 筛选器可以基于各种准则, 如列属性值、位掩码或子数据子数据。 使用[SRestriction](srestriction.md)结构在 MAPI 中指定筛选器。 
  
 **将表定位到与限制中建立的条件相匹配的第一行**
  
- 调用[IMAPITable:: FindRow](imapitable-findrow.md)方法。 从特定书签表示的行开始, **FindRow**搜索向前或向后方向, 以定位与限制中指定的条件匹配的行。 **FindRow**可用于实现基于字符字符串 (而不是小数值) 的滚动条。 例如, 在搜索集成通讯簿以启用用户 (通过输入一个或多个字符以查找以指定字符开头的名字) 时, 客户端可以调用 MAPI 的**FindRow**实现。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

