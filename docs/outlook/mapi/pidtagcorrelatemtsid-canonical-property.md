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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359932"
---
# <a name="pidtagcorrelatemtsid-canonical-property"></a>PidTagCorrelateMtsid 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于将报告与已发送邮件关联的邮件传输系统 (MTS) 标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CORRELATE_MTSID  <br/> |
|标识符:  <br/> |0x0E0D  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>注解

如果传输提供程序遇到此属性设置为 TRUE 的已提交邮件, 则会将此属性设置为该邮件的 MTS 标识符。 在传输之后, 此属性将与邮件一起存储在人际邮件 (IPM) 的 "已发送邮件" 文件夹中。
  
支持按 MTS 标识符进行关联的邮件系统 (如 X. 400) 将标识符保留为原始邮件的传输信封的一部分, 还保留为响应它而生成的任何报告。 当报告通过此类邮件系统传递时, 传输提供程序会将此属性设置为报告传输信封中的原始 MTS 标识符。 然后, 将该属性与报表存储在一起。
  
客户端应用程序可以维护具有此属性的所有邮件的搜索结果文件夹。 当报告收到此类邮件时, 客户端可以对搜索结果文件夹应用限制, 查找邮件的原始版本, 并将原始邮件信息与新信息关联。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

