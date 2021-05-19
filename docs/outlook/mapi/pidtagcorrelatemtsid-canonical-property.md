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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96bfc184752b6a3e15434ad67ac8c2b4b26cac4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426833"
---
# <a name="pidtagcorrelatemtsid-canonical-property"></a>PidTagCorrelateMtsid 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于将报告与 (关联的 MTS) 传输系统标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CORRELATE_MTSID  <br/> |
|标识符:  <br/> |0x0E0D  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>备注

当传输提供程序遇到提交的邮件时，此属性设置为 TRUE，它会将此属性设置为该邮件的 MTS 标识符。 传输后，此属性与邮件一起存储在 IPM (") "文件夹中。
  
支持通过 MTS 标识符（如 X.400）进行关联的消息系统保留标识符作为原始邮件的传输信封的一部分，以及为响应邮件而生成的任何报告。 从此类邮件系统传递报告时，传输提供程序会从报表的传输信封将此属性设置为原始 MTS 标识符。 然后，此属性与报表一起存储。
  
客户端应用程序可以维护具有此属性的所有邮件的搜索结果文件夹。 当收到此类邮件的报告时，客户端可以将限制应用于搜索结果文件夹，查找邮件的原始版本，并将原始邮件信息与新信息关联。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

