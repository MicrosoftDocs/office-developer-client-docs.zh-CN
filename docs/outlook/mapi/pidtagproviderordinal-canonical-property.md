---
title: PidTagProviderOrdinal 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderOrdinal
api_type:
- COM
ms.assetid: d062b54d-7c32-4369-ab69-f7193773a1c0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fbeb63bbae23f8f7f78c92d3abed6bea1c3ac85d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438349"
---
# <a name="pidtagproviderordinal-canonical-property"></a>PidTagProviderOrdinal 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含服务提供商在提供程序表中位置的从零开始编制的索引。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_ORDINAL  <br/> |
|标识符:  <br/> |0x300D  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI common  <br/> |
   
## <a name="remarks"></a>备注

此属性由 MAPI 计算。
  
通过调用 [IMsgServiceAdmin：：GetProviderTable 方法获取提供程序](imsgserviceadmin-getprovidertable.md) 表。 对此属性上的提供程序表进行排序以显示传输顺序。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

