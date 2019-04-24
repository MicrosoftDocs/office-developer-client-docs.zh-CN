---
title: PidTagStoreProvider 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreProvider
api_type:
- COM
ms.assetid: 6f6cc66f-a08e-4f8e-b33a-d3674319248e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6266c9293f54ce764c5b5b0e41d43767490abcf7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278706"
---
# <a name="pidtagstoreprovider-canonical-property"></a>PidTagStoreProvider 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含提供程序定义的[MAPIUID](mapiuid.md)结构, 该结构指示邮件存储区的类型。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MDB_PROVIDER  <br/> |
|标识符:  <br/> |0x3414  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>注解

[MAPIUID](mapiuid.md)结构标识邮件存储的类型。 值由邮件存储区对象的邮件存储提供程序计算, 并且每个提供程序都是唯一的。 它通常用于浏览邮件存储区表以查找所需类型的存储, 例如公用文件夹。 
  
此属性类似于通讯簿的**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。 
  
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

