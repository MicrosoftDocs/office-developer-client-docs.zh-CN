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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286458"
---
# <a name="pidtagprovidericon-canonical-property"></a>PidTagProviderIcon 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 Unicode 字符串, 该字符串指定要在联机和脱机状态的 Microsoft Office Outlook 状态栏中为 MAPI 提供程序显示的自定义图标或图标。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_ICON、PR_PROVIDER_ICON_W  <br/> |
|标识符:  <br/> |0x3417  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 邮件存储  <br/> |
   
## <a name="remarks"></a>注解

这些属性指定的资源文件中包含一个自定义图标, 该图标表示处于联机状态的 MAPI 提供程序, 也可以选择另一个自定义图标处于脱机状态。 Outlook 始终请求 Unicode 表示形式的这些属性。 
  
例如, 以下属性值指示 Outlook 从模块 mymod32 加载图标 ID 1001, 并将该图标用于联机状态: `mymod32.dll,#1001`。 由于脱机状态没有提供程序特定的图标, 在这种情况下, 将在状态栏中使用标准的 Outlook 脱机图标。 
  
下面的属性值指示 Outlook 从模块 mymod32 加载图标 id 1001, 并将该图标用于联机状态, 并从该相同的模块加载图标 id 1002, 以用于脱机状态: `mymod32.dll,#1001,#1002`。 状态栏中不使用 Outlook 图标。 
  
默认情况下, 如果未指定任何自定义图标, 提供程序将由 Outlook 默认图标用于联机状态和脱机状态。 提供程序可以根据需要指定显示名称, 该显示名称将显示在状态栏中的图标旁边。 有关详细信息, 请参阅**PR_PROVIDER_DISPLAY_NAME_W** ([PidTagProviderDisplayName](pidtagproviderdisplayname-canonical-property.md))。
  
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

