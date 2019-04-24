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
ms.openlocfilehash: ff5d35104e9effc27c405b716cb61cf4643677b3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359953"
---
# <a name="pidtagdefcreatedl-canonical-property"></a>PidTagDefCreateDl 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含默认通讯组列表的模板条目标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEF_CREATE_DL  <br/> |
|标识符:  <br/> |0x3611  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>注解

客户端应用程序使用此属性在容器中创建通讯组列表。 对 "条目创建" 的支持对于通讯簿容器是可选的;不支持它的方法不需要公开此属性。 
  
此属性指定可显示在通讯组列表的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性中的条目。 获取标识符后, 客户端将在调用[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法时使用它。 条目表示默认通讯组列表的模板。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IABLogon::CompareEntryIDs](iablogon-compareentryids.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

