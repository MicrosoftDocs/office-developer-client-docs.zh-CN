---
title: PidTagProviderItemId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderItemId
api_type:
- COM
ms.assetid: fadbf1af-32c2-43ea-8475-15b31b2a9e68
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 48653b86d625da963b655dbd1acc01a46f4687dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286472"
---
# <a name="pidtagprovideritemid-canonical-property"></a>PidTagProviderItemId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定存储区中的文件夹或项目的标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_ITEMID  <br/> |
|标识符:  <br/> |0x0EA3  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MapiNonTransmittable  <br/> |
   
## <a name="remarks"></a>注解

存储提供程序可以为文件夹或项目的此属性指定值, 但应保持会话之间的值相同。 存储提供程序使用此属性可标识从搜索引擎返回的搜索结果。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

