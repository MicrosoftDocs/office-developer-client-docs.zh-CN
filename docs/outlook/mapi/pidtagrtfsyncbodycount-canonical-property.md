---
title: PidTagRtfSyncBodyCount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfSyncBodyCount
api_type:
- COM
ms.assetid: b7267be4-8d5c-4dc7-86b2-651e03e84f9b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f6e687412dfce1e5fcee6b4a4d64f3e5106455f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331253"
---
# <a name="pidtagrtfsyncbodycount-canonical-property"></a>PidTagRtfSyncBodyCount 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件文本的重要字符的计数。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RTF_SYNC_BODY_COUNT  <br/> |
|标识符:  <br/> |0x1007  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 邮件  <br/> |
   
## <a name="remarks"></a>注解

[RTFSync](rtfsync.md)函数计算文本中的字符数, 仅使用它认为对邮件有意义的字符。 例如, 某些空格和其他可忽略字符将从 count 中省略。 
  
此属性是 rtf 格式 (rtf) 辅助属性。 这些属性由**RTFSync**函数使用, 不应由客户端应用程序直接使用。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码并解码为高效流表示形式。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

