---
title: PidTagRoamingXmlStream 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRoamingXmlStream
api_type:
- COM
ms.assetid: ce55b50e-3dbf-4690-9102-c08f35ada82e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3e7ce1f810a1dd37cd4370ceb423b664d75878a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359540"
---
# <a name="pidtagroamingxmlstream-canonical-property"></a>PidTagRoamingXmlStream 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含任意 XML 流。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ROAMING_XMLSTREAM  <br/> |
|标识符:  <br/> |0x7C08  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |配置  <br/> |
   
## <a name="remarks"></a>注解

此属性包含 XML 数据的任意流。 邮件中的其他属性可能暗示了要在此属性中使用的特定架构。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)
  
> 指定客户端和服务器配置数据的位置和属性, 如共享类别列表和工作时间。
    
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

