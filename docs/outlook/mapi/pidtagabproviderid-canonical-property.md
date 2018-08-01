---
title: PidTagAbProviderId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagAbProviderId
api_type:
- HeaderDef
ms.assetid: 23cfd1d0-8e9d-4508-93dd-a88c0ef77c51
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 84a2d5517d405ac6deb61f7c4679d6816e802404
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777270"
---
# <a name="pidtagabproviderid-canonical-property"></a>PidTagAbProviderId 规范属性

  
  
**适用于**： Outlook 
  
包含通讯簿提供程序的[MAPIUID](mapiuid.md)结构。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_AB_PROVIDER_ID  <br/> |
|标识符：  <br/> |0x3615  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>说明

**MAPIUID**结构标识的通讯簿提供程序提供此容器层次结构中的特定容器。 值是唯一的每个提供程序。 
  
通讯簿提供程序可以提供多个标识符。 例如，提供两个不同的容器的提供程序可以发布**PR_AB_PROVIDER_ID**对每个容器的唯一标识符。 
  
 **PR_AB_PROVIDER_ID**是类似于邮件存储的**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性。 客户端应用程序可以使用**PR_AB_PROVIDER_ID**通讯簿层次结构表中查找相关的行。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[PidTagStoreProvider 规范属性](pidtagstoreprovider-canonical-property.md)


[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

