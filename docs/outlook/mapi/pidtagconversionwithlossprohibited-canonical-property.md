---
title: PidTagConversionWithLossProhibited 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagConversionWithLossProhibited
api_type:
- HeaderDef
ms.assetid: a18b560a-e054-45b3-946d-6504465db5b7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eee70d97c35c7f115e424905b9e36f3dfa392c02
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777523"
---
# <a name="pidtagconversionwithlossprohibited-canonical-property"></a>PidTagConversionWithLossProhibited 规范属性

  
  
**适用于**： Outlook 
  
包含 TRUE，则邮件传输代理 (MTA) 禁止进行丢失信息的文本转换的消息。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONVERSION_WITH_LOSS_PROHIBITED  <br/> |
|标识符：  <br/> |0x000D  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |常规配置  <br/> |
   
## <a name="remarks"></a>说明

被禁止的转换类型的示例为"有损"映射 Unicode （每个字符的两个字节） 到单字节字符集。 
  
## <a name="related-resources"></a>相关资源

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

