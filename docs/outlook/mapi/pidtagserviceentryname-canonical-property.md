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
ms.openlocfilehash: 2c771f1d97305271b70102c148e62f30512974fb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432469"
---
# <a name="pidtagserviceentryname-canonical-property"></a>PidTagServiceEntryName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于配置邮件服务的入口点函数的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_ENTRY_NAME  <br/> |
|标识符:  <br/> |0x3D0B  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>备注

建议邮件服务实施者提供邮件服务入口点，但不需要该入口点。 但是，只有在存在相关的配置属性时，才应提供入口点。 如果这些属性不存在，MAPI 将假定未提供入口点。
  
动态链接库 (DLL) ，其中入口点函数由 **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 命名。
  
有关邮件服务入口点的信息，请参阅 [实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

