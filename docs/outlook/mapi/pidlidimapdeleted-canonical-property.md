---
title: PidLidImapDeleted 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidImapDeleted
api_type:
- COM
ms.assetid: ee929306-8962-494d-bc47-9b4069f01267
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 790aa363522b9562f8f06c0806c87bba3816f566
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415787"
---
# <a name="pidlidimapdeleted-canonical-property"></a>PidLidImapDeleted 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示 Internet 邮件访问协议 (IMAP) 标记为删除的项目。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidImapDeleted  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008570  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |IMAP  <br/> |
   
## <a name="remarks"></a>备注

如果设置为非零值，则该项目已标记为删除。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

