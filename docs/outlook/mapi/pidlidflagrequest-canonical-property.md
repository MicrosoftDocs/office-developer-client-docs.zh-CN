---
title: PidLidFlagRequest 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFlagRequest
api_type:
- COM
ms.assetid: 38981f07-14b8-47c2-93df-e6aed91896e4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ddcf32df716fe2b0a02655278ff0cd8d821de1f4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357804"
---
# <a name="pidlidflagrequest-canonical-property"></a>PidLidFlagRequest 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示会议请求的状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidRequest  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008530  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |标记  <br/> |
   
## <a name="remarks"></a>备注

在Microsoft Office Outlook中，会议请求是约会项目。
  
此属性包含要与标志关联的用户可指定文本，如果邮件对象已标记或已完成，但与会议相关的对象不应存在，则应该设置该属性。 客户端可以选择不支持此属性，并始终编写"跟进" (翻译为用户语言（如果适用) ）作为应设置此属性的字符串值。 应基于 **dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) 和 **dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md)) 属性的值有条件地忽略此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

