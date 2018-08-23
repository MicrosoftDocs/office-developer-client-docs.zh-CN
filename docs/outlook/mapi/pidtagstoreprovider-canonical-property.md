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
ms.openlocfilehash: 02d2c30fede7e554910a1bedb01b79c488447bb3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595354"
---
# <a name="pidtagstoreprovider-canonical-property"></a>PidTagStoreProvider 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个提供程序定义[MAPIUID](mapiuid.md)结构，指示邮件存储的类型。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MDB_PROVIDER  <br/> |
|标识符：  <br/> |0x3414  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>注解

[MAPIUID](mapiuid.md)结构标识消息存储库的类型。 此值计算的消息存储对象上的消息存储提供程序，并且是唯一的每个提供程序。 它通常用于浏览消息存储表如公用文件夹中查找所需类型的存储区。 
  
此属性是类似于通讯簿的**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。 
  
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

