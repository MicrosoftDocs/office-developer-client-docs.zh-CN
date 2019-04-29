---
title: PidTagProviderDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderDisplay
api_type:
- COM
ms.assetid: 62e96db8-4c3e-4f73-b695-99eb4b2396fd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 58db944720817491420f2bcb1774e51e3842b4a6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421590"
---
# <a name="pidtagproviderdisplay-canonical-property"></a>PidTagProviderDisplay 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含供应商定义的服务提供商的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_DISPLAY、PR_PROVIDER_DISPLAY_A、PR_PROVIDER_DISPLAY_W  <br/> |
|标识符:  <br/> |0x3006  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 通用  <br/> |
   
## <a name="remarks"></a>说明

这些属性和**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 仅在属于服务提供程序的配置文件节中进行定义。 它们必须存在于 mapisvc.inf 中。
  
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

