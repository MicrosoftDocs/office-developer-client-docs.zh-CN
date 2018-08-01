---
title: PidTagServiceEntryName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceEntryName
api_type:
- COM
ms.assetid: 783f08aa-fb5a-432d-b8bd-48d69f0e5c38
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0d75616aaa6599709828d32393a316c642bc613b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778396"
---
# <a name="pidtagserviceentryname-canonical-property"></a>PidTagServiceEntryName 规范属性

  
  
**适用于**： Outlook 
  
包含消息服务的配置的入口点函数的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_ENTRY_NAME  <br/> |
|标识符：  <br/> |0x3D0B  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>说明

建议的消息服务实施提供邮件服务入口点，但的入口点，则不需要。 但是，仅当存在相关的配置属性，则应提供的入口点。 如果不存在这些属性，MAPI 假定原样的入口点。
  
动态链接库 (DLL) 中的入口点函数显示名为**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 属性。
  
消息服务入口点的详细信息，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。
  
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

