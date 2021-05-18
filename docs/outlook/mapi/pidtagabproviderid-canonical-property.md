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
ms.openlocfilehash: 820df61ec23e2dd1459582e5a7bb35ad9525e0b4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422241"
---
# <a name="pidtagabproviderid-canonical-property"></a>PidTagAbProviderId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含通讯簿提供程序的 [MAPIUID](mapiuid.md) 结构。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_AB_PROVIDER_ID  <br/> |
|标识符:  <br/> |0x3615  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>备注

**MAPIUID** 结构标识在容器层次结构中提供此特定容器的通讯簿提供程序。 该值对于每个提供程序都是唯一的。 
  
通讯簿提供程序可以提供多个标识符。 例如，提供两个不同容器的提供程序可以在每个容器PR_AB_PROVIDER_ID唯一标识符中发布。 
  
 **PR_AB_PROVIDER_ID** 邮件存储PR_MDB_PROVIDER ([PidTagStoreProvider) PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)属性。  客户端 **应用程序可以使用** PR_AB_PROVIDER_ID在通讯簿层次结构表中查找相关行。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[PidTagStoreProvider 规范属性](pidtagstoreprovider-canonical-property.md)


[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

