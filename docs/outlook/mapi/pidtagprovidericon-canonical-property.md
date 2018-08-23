---
title: PidTagProviderIcon 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderIcon
api_type:
- COM
ms.assetid: 59c84b1f-13b5-484b-b703-2fb9fcc6c7eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 61dc61872e8d1ed525d5ac3c46c56ccc3e45ea5e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593695"
---
# <a name="pidtagprovidericon-canonical-property"></a>PidTagProviderIcon 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含指定自定义图标或图标以显示在 Microsoft Office Outlook 的状态栏中联机和脱机状态 MAPI 提供程序的 Unicode 字符串。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_ICON PR_PROVIDER_ICON_W  <br/> |
|标识符：  <br/> |0x3417  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 邮件存储  <br/> |
   
## <a name="remarks"></a>注解

这些属性指定资源文件包含自定义图标表示处于联机状态，MAPI 提供程序和 （可选），另一个自定义图标处于脱机状态。 Outlook 始终请求 Unicode 表示这些属性。 
  
例如，以下属性值指示 Outlook 从模块 mymod32.dll 加载图标 ID 1001 并该图标用于联机状态： `mymod32.dll,#1001`。 没有为脱机状态提供程序特定的图标，因为在这种情况下，标准的 Outlook 脱机图标使用在状态栏中。 
  
以下属性值指示 Outlook 从模块 mymod32.dll 加载图标 ID 1001 和该图标用于联机状态，并为还从这一相同模块用于脱机状态加载图标 ID 1002: `mymod32.dll,#1001,#1002`。 在状态栏中不使用任何 Outlook 图标。 
  
默认情况下，如果未不指定任何自定义图标，则提供程序是由联机状态和脱机状态的 Outlook 默认图标表示。 提供程序 （可选） 可以指定要在状态栏中显示图标旁边显示名称。 有关详细信息，请参阅**PR_PROVIDER_DISPLAY_NAME_W** ([PidTagProviderDisplayName](pidtagproviderdisplayname-canonical-property.md))。
  
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

