---
title: PidTagServiceExtraUids 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceExtraUids
api_type:
- COM
ms.assetid: 4838a9af-7818-49aa-ace8-cb94dda8471f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 71f802014200d4b767c346c14df53f1193d44b0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778406"
---
# <a name="pidtagserviceextrauids-canonical-property"></a>PidTagServiceExtraUids 规范属性

  
  
**适用于**： Outlook 
  
包含标识邮件服务的其他配置文件部分的[MAPIUID](mapiuid.md)结构的列表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_EXTRA_UIDS  <br/> |
|标识符：  <br/> |0x3D0D  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>说明

可以为每个邮件筛选器创建新的配置文件部分。 当邮件服务的信息复制到另一个配置文件时，务必要复制的筛选器以及其他配置文件部分。 使用其他配置文件节的服务提供商可以存储这些配置文件节的**MAPIUID**结构中**PR_SERVICE_EXTRA_UIDS**，它允许 MAPI 复制其他消息服务信息。
  
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

