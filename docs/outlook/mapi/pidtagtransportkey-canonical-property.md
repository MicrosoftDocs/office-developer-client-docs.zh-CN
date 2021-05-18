---
title: PidTagTransportKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTransportKey
api_type:
- COM
ms.assetid: 131211b3-e6f9-4dd4-b6d9-b65361bff775
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 05db434ddabbd5f60fccdfeb1a2df8b3fcd0d96a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405546"
---
# <a name="pidtagtransportkey-canonical-property"></a>PidTagTransportKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 MAPI 后台处理程序用于通过传出传输提供程序跟踪出站邮件进度的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TRANSPORT_KEY  <br/> |
|标识符:  <br/> |0x0E16  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 不可传输  <br/> |
   
## <a name="remarks"></a>备注

不要使用此属性。 它保留供 MAPI 使用。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagTransportProviders 规范属性](pidtagtransportproviders-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

