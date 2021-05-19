---
title: PidTagDeferredSendNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredSendNumber
api_type:
- HeaderDef
ms.assetid: 8ada5c9b-bec5-42d8-bc58-f0411ec4e88b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e3a30dad433b255573e4e3f041e6475b9227a54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357734"
---
# <a name="pidtagdeferredsendnumber-canonical-property"></a>PidTagDeferredSendNumber 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含可用于计算邮件发送延迟的编号。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEFERRED_SEND_NUMBER  <br/> |
|标识符:  <br/> |0x3FEB  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>备注

此属性用于计算[PidTagDeferredSendTime PR_DEFERRED_SEND_TIME (不存在时) PidTagDeferredSendTime](pidtagdeferredsendtime-canonical-property.md)属性。  延迟发送邮件时 **，PR_DEFERRED_SEND_NUMBER** 属性应该与 **PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) 属性一起设置（ **如果缺少 PR_DEFERRED_SEND_TIME** 属性）。 
  
必须 **PR_DEFERRED_SEND_NUMBER** 0 到 999 之间的值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

