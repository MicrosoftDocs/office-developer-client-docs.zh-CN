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
ms.openlocfilehash: 708e77e4df097f5a0de008e09808ffcbc0289f61
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574578"
---
# <a name="pidtagprofilename-canonical-property"></a>PidTagProfileName 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含配置文件的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_NAME，PR_PROFILE_NAME_A，PR_PROFILE_NAME_W  <br/> |
|标识符：  <br/> |0x3D12  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>注解

通过服务提供商，这些属性来计算。 **ServiceEntry**函数的提供程序实现可以使用这些属性来发现的配置文件名称。 
  
客户端应用程序可以使用这些属性，作为一个便捷的替代方式，通过检查 MAPI 子系统的状态表格行中的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性来获取的配置文件名称。
  
不随时间，例如其中一个配置文件删除和更高版本具有相同名称重新创建都是唯一这些属性。 MAPI 提供调用硬编码的配置文件一节中的完全唯一**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性**MUID_PROFILE_INSTANCE。**
  
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

