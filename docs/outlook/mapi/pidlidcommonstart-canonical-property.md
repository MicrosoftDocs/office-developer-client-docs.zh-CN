---
title: PidLidCommonStart 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCommonStart
api_type:
- COM
ms.assetid: d999852d-ce98-4c3c-a772-87f5db4aa04e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ec7c213d7eec9ab0ef5766442e3de59a24811d37
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345484"
---
# <a name="pidlidcommonstart-canonical-property"></a>PidLidCommonStart 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示邮件的开始日期和时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidCommonStart  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008516  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性指示项目的开始时间。 它必须小于或等于 **dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) 属性的值。
  
此属性的值必须是协调世界时 (UTC) 相当于 **dispidTaskStartDate** ([PidLidTaskStartDate](pidlidtaskstartdate-canonical-property.md)) 属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

