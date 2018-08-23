---
title: PidTagServiceDllName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceDllName
api_type:
- COM
ms.assetid: a651af84-1711-449e-ba7e-5ce09cafa02b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d2917f2119fde38686397b65956113bc430b2e31
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570812"
---
# <a name="pidtagservicedllname-canonical-property"></a>PidTagServiceDllName 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含要配置的呼叫的 dll 包含消息服务提供程序入口点函数的文件名。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_DLL_NAME，PR_SERVICE_DLL_NAME_A，PR_SERVICE_DLL_NAME_W  <br/> |
|标识符：  <br/> |0x3D0A  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>注解

当入口点函数名称出现在**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 方法时，它指示存在的入口点。
  
MAPI 使用 DLL 文件命名约定。 基文件名包含唯一标识 DLL 的最多包含 6 个字符。 MAPI 将字符串 32 追加到基的 DLL 名称，来确定在 32 位平台运行的版本。 例如，当 MAPI 的名称。指定 DLL，MAPI 构造 MAPI32 的名称。表示的 dll 的相应 32 位版本的 DLL。
  
这些属性应指定的基名称。 MAPI 将根据 32 字符串。 这些属性会导致出错的一部分包括 32 的字符串。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagProviderDllName 规范属性](pidtagproviderdllname-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

