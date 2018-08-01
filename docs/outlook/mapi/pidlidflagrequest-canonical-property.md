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
ms.openlocfilehash: df2e474206559dadf250bdf9a078c69da61187c8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776843"
---
# <a name="pidlidflagrequest-canonical-property"></a>PidLidFlagRequest 规范属性

  
  
**适用于**： Outlook 
  
表示会议请求的状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidRequest  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x00008530  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |标记  <br/> |
   
## <a name="remarks"></a>说明

在 Microsoft Office Outlook 会议请求是约会项目。
  
此属性包含用户并以此来与标志相关联的文本和应为设置消息对象是标记或完成，但不是应存在会议相关对象。 客户端可以选择不支持此属性，并始终编写"后续标志"（如果适用的用户的语言翻译） 作为字符串时应设置此属性的值。 应基于**dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) 和**dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md)) 属性的值有条件地忽略此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

