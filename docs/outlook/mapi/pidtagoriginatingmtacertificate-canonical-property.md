---
title: PidTagOriginatingMtaCertificate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatingMtaCertificate
api_type:
- COM
ms.assetid: f6b7ff0c-19a0-4cad-8868-c05397fcebf4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f78609537b85a89617e7b2fa8f30a4ba952805b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414807"
---
# <a name="pidtagoriginatingmtacertificate-canonical-property"></a>PidTagOriginatingMtaCertificate 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含发出邮件的邮件传输代理 (MTA) 的标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINATING_MTA_CERTIFICATE  <br/> |
|标识符:  <br/> |0x0E25  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |服务器  <br/> |
   
## <a name="remarks"></a>说明

如果设置此属性, 则该属性在 "已发送邮件" 文件夹中的已发送邮件中可用。
  
此属性对应于每个邮件的400个报告属性。
  
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

