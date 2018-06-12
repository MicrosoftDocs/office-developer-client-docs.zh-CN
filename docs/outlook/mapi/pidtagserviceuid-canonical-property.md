---
title: PidTagServiceUid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceUid
api_type:
- COM
ms.assetid: 9d99a3b6-d0b4-4e8a-8f08-f46fdeb6b3e7
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 304efc3f4ea903f9ed0e9fcf95c7100fa6ebfc95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778422"
---
# <a name="pidtagserviceuid-canonical-property"></a>PidTagServiceUid 规范属性

  
  
**适用于**： Outlook 
  
包含消息服务的[MAPIUID](mapiuid.md)结构。 
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_SERVICE_UID  <br/> |
|标识符:  <br/> |0x3D0C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>备注

此属性通过 MAPI 配置文件部分对象上计算。 MAPI 使用它组属于同一消息服务的所有提供商。 此属性是作为大部分[IMsgServiceAdmin](imsgserviceadminiunknown.md)方法的参数提供的。 它必须 Mapisvc.inf 中不显示。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin: IUnknown](imsgserviceadminiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

