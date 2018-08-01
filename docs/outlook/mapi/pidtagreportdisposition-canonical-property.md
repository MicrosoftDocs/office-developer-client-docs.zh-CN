---
title: PidTagReportDisposition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 56b9e7bd-eece-4264-8ee5-a1bcbec4f35c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 62d5b04086e45b6b3d2cfa960472010827d60d6b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778213"
---
# <a name="pidtagreportdisposition-canonical-property"></a>PidTagReportDisposition 规范属性

  
  
**适用于**： Outlook 
  
指示请求收款的消息的回执状态。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REPORT_DISPOSITION，PR_REPORT_DISPOSITION_A，PR_REPORT_DISPOSITION_W  <br/> |
|标识符：  <br/> |0x0080  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>说明

有效值如下：
  
- "已删除"
    
- "处理"
    
- "发送"
    
- "拒绝"
    
- "failed"
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供了相关的 Exchange Server 协议规范参考。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

