---
title: PidTagDefCreateMailuser 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefCreateMailuser
api_type:
- HeaderDef
ms.assetid: e8293dc9-f2f1-4065-89f4-e734a8db63df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 33c62b81982aaac3659ad4d41ea2cf5298b42287
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777536"
---
# <a name="pidtagdefcreatemailuser-canonical-property"></a>PidTagDefCreateMailuser 规范属性

  
  
**适用于**： Outlook 
  
包含消息用户对象的默认模板条目标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEF_CREATE_MAILUSER  <br/> |
|标识符：  <br/> |0x3612  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>说明

客户端应用程序使用此属性可创建容器内的邮件用户对象。 支持的条目创建是可选的通讯簿容器;不支持的那些无需公开此属性。 
  
此属性指定的条目可能出现的消息的用户的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性中。 获取后标识符，客户端使用它对[IABContainer::CreateEntry](iabcontainer-createentry.md)方法的调用中。 条目代表在模板默认消息用户。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

