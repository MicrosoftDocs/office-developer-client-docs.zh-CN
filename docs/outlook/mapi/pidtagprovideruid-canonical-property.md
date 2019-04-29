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
ms.openlocfilehash: 0d79075ea1db451e0c3d327df9a662e5032ebb22
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422773"
---
# <a name="pidtagprovideruid-canonical-property"></a>PidTagProviderUid 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含正在处理邮件的服务提供程序的**MAPIUID**结构。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_UID  <br/> |
|标识符:  <br/> |0x300C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 通用  <br/> |
   
## <a name="remarks"></a>说明

此属性由所有服务提供程序计算。 它包含与提供程序关联的[MAPIUID](mapiuid.md)结构, 并且通常由该提供程序进行硬编码。 它通常由仅对特定提供程序所提供的通讯簿容器感兴趣的客户端应用程序使用。 
  
此属性仅显示为提供程序表中的列条目。
  
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

