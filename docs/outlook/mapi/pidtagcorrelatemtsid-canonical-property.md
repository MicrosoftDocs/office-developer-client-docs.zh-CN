---
title: PidTagCorrelateMtsid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCorrelateMtsid
api_type:
- HeaderDef
ms.assetid: d0fc4e91-ed90-4d27-bd23-f01e99728e2d
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 57da2d4c78914323b5dafa4f5ba5b7628d0e2f2f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777522"
---
# <a name="pidtagcorrelatemtsid-canonical-property"></a>PidTagCorrelateMtsid 规范属性

  
  
**适用于**： Outlook 
  
包含用于将报告与已发送邮件关联的邮件传输系统 (MTS) 标识符。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_CORRELATE_MTSID  <br/> |
|标识符:  <br/> |0x0E0D  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>备注

当传输提供程序遇到该属性设置为 TRUE 已提交的邮件时，它将此属性设置为该消息的 MTS 标识符。 以下传输，此属性与人际邮件 (IPM) 发送邮件文件夹中的消息存储。
  
通过 MTS 标识符，如 X.400，支持相关的邮件系统保留的传输信封的原始邮件以及任何响应其生成报告的一部分的标识符。 从系统消息传递报表，传输提供程序将该属性与原始 MTS 标识符设置从报表的传输信封。 此属性与报表然后存储。
  
客户端应用程序可以维护搜索结果文件夹具有此属性的所有消息。 当报表时，此类邮件时，客户端可以限制应用于的搜索结果文件夹、 查找邮件的原始版本和关联的新信息的原始消息信息。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

