---
title: PidTagProfileName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProfileName
api_type:
- COM
ms.assetid: 13ca726d-ae7a-4da9-9c8e-3db3c479f839
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 992b3a6a30e15d267ffeda11ec98c7b4aeacb2c4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435647"
---
# <a name="pidtagprofilename-canonical-property"></a>PidTagProfileName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含配置文件的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_NAME、PR_PROFILE_NAME_A、PR_PROFILE_NAME_W  <br/> |
|标识符:  <br/> |0x3D12  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>备注

这些属性由服务提供商计算。 提供程序的 **ServiceEntry** 函数实现可以使用这些属性来发现配置文件名称。 
  
通过检查 MAPI 子系统的状态表行中的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性，客户端应用程序可以使用这些属性作为获取配置文件名称的便捷替代方法。
  
这些属性在一定时间之间可能并不唯一，例如删除配置文件，然后使用相同的名称重新创建配置文件。 MAPI 在名为 MUID_PROFILE_INSTANCE的硬编码配置文件PR_SEARCH_KEY ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性提供一个 **完全唯一MUID_PROFILE_INSTANCE。**
  
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

