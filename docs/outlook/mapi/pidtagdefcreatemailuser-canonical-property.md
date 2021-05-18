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
ms.openlocfilehash: cd09c85e4f44bbea29807d72a273ccf6980ca6df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407478"
---
# <a name="pidtagdefcreatemailuser-canonical-property"></a>PidTagDefCreateMailuser 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含默认消息传递用户对象的模板项标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEF_CREATE_MAILUSER  <br/> |
|标识符:  <br/> |0x3612  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>备注

客户端应用程序使用此属性在容器中创建消息用户对象。 对于通讯簿容器，支持条目创建是可选的;不支持此属性的项不需要公开此属性。 
  
此属性指定可以在邮件用户的[PidTagCreateTemplates PR_CREATE_TEMPLATES (PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 条目。  获取标识符后，客户端在调用 [IABContainer：：CreateEntry 方法时使用它](iabcontainer-createentry.md) 。 条目表示默认邮件用户的模板。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

