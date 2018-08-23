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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eabcaaf1db6149ef200e640f5af152758261581b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582249"
---
# <a name="pidtagserviceuid-canonical-property"></a>PidTagServiceUid 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含消息服务的[MAPIUID](mapiuid.md)结构。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_UID  <br/> |
|标识符：  <br/> |0x3D0C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>注解

此属性通过 MAPI 配置文件部分对象上计算。 MAPI 使用它组属于同一消息服务的所有提供商。 此属性是作为大部分[IMsgServiceAdmin](imsgserviceadminiunknown.md)方法的参数提供的。 它必须 Mapisvc.inf 中不显示。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

