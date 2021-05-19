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
ms.openlocfilehash: 55e6c8fb013e544ae04740aeaeb23ac23949cffb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425636"
---
# <a name="pidtagprovidericon-canonical-property"></a>PidTagProviderIcon 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 Unicode 字符串，该字符串指定在处于联机和脱机状态的 Microsoft Office Outlook 状态栏中为 MAPI 提供程序显示的自定义图标。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_ICON、PR_PROVIDER_ICON_W  <br/> |
|标识符:  <br/> |0x3417  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 邮件存储  <br/> |
   
## <a name="remarks"></a>备注

这些属性指定包含表示处于联机状态 MAPI 提供程序的自定义图标的资源文件，以及另一个处于脱机状态（可选）的自定义图标。 Outlook Unicode 表示形式始终请求这些属性。 
  
例如，以下属性值指示Outlook模块加载图标 ID 1001，mymod32.dll该图标用于联机状态 `mymod32.dll,#1001` ：。 由于脱机状态没有提供程序特定的图标，因此在这种情况下，状态Outlook使用标准脱机图标。 
  
以下属性值指示 Outlook 从模块 mymod32.dll 加载图标 ID 1001，并使用该图标实现联机状态，并从此同一模块加载图标 ID 1002 以用于脱机状态 `mymod32.dll,#1001,#1002` ：。 状态Outlook没有使用图标。 
  
默认情况下，如果未指定自定义图标，则提供程序由Outlook状态和脱机状态的默认图标表示。 提供程序可以选择指定显示名称图标旁边显示的图标。 有关详细信息，请参阅 **PR_PROVIDER_DISPLAY_NAME_W** ([PidTagProviderDisplayName](pidtagproviderdisplayname-canonical-property.md)) 。
  
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

