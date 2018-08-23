---
title: PidTagRtfSyncBodyCrc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfSyncBodyCrc
api_type:
- COM
ms.assetid: 95db4837-400f-476f-b313-60e8baa1c6d1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7c72b87eec6d0a14b0ebba10529ef5d898747028
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572975"
---
# <a name="pidtagrtfsyncbodycrc-canonical-property"></a>PidTagRtfSyncBodyCrc 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的邮件文本计算循环冗余检查 (CRC)。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RTF_SYNC_BODY_CRC  <br/> |
|标识符：  <br/> |0x1006  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 邮件  <br/> |
   
## <a name="remarks"></a>注解

[RTFSync](rtfsync.md)函数计算 CRC 使用其认为是重要邮件的字符。 例如，从 CRC 忽略一些空格和其他可忽略字符。 
  
此属性是一个富文本格式 (RTF) 辅助属性。 这些属性使用**RTFSync**函数，不能直接通过客户端应用程序使用。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

