---
title: PidTagDefCreateDl 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefCreateDl
api_type:
- HeaderDef
ms.assetid: 172dc15b-7bda-403f-a93a-446b2f9ff1d3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3fb86fba3b0ff8a79858fad59dca61069aff6db9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777543"
---
# <a name="pidtagdefcreatedl-canonical-property"></a>PidTagDefCreateDl 规范属性

  
  
**适用于**： Outlook 
  
包含默认通讯组列表的模板条目标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEF_CREATE_DL  <br/> |
|标识符：  <br/> |0x3611  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>说明

客户端应用程序使用此属性来创建通讯组列表容器中。 支持的条目创建是可选的通讯簿容器;不支持的那些无需公开此属性。 
  
此属性指定通讯组列表的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性中可显示一个条目。 获取后标识符，客户端使用它对[IABContainer::CreateEntry](iabcontainer-createentry.md)方法的调用中。 条目代表在默认通讯组列表的模板。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IABLogon::CompareEntryIDs](iablogon-compareentryids.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

