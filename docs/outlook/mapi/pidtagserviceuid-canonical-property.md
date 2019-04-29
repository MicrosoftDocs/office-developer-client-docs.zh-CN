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
ms.openlocfilehash: d5c6e1dc30c3ee7862341bce204b4a78bd6d379b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426525"
---
# <a name="pidtagserviceuid-canonical-property"></a>PidTagServiceUid 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件服务的[MAPIUID](mapiuid.md)结构。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_UID  <br/> |
|标识符:  <br/> |0x3D0C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>说明

此属性由 MAPI 的 profile 节对象计算。 MAPI 使用它对属于同一邮件服务的所有提供程序进行分组。 此属性作为参数提供给大多数[IMsgServiceAdmin](imsgserviceadminiunknown.md)方法。 它不得出现在 mapisvc.inf 中。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

