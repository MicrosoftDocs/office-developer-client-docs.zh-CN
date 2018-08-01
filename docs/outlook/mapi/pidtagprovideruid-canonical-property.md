---
title: PidTagProviderUid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderUid
api_type:
- COM
ms.assetid: 993f5bca-58a6-455d-8a25-6e08b441ad31
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7a42a3b50cfa5630ac66cb03caac06dd7cb00e6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778081"
---
# <a name="pidtagprovideruid-canonical-property"></a>PidTagProviderUid 规范属性

  
  
**适用于**： Outlook 
  
包含正在处理一条消息的服务提供商**MAPIUID**结构。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_UID  <br/> |
|标识符：  <br/> |0x300C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常见的 MAPI  <br/> |
   
## <a name="remarks"></a>说明

此属性由所有服务提供商计算。 它包含提供商的[MAPIUID](mapiuid.md)结构相关联，且通常硬编码。 通常使用感仅特定的提供商所提供的通讯簿容器中的客户端应用程序。 
  
此属性仅显示为提供程序表中的列条目。
  
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

