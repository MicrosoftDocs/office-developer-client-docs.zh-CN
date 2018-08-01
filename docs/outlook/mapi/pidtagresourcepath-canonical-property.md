---
title: PidTagResourcePath 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourcePath
api_type:
- COM
ms.assetid: ac49538e-6ee8-4ab4-9d79-88a83c7d0149
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d7385ea403e7ea45c97f6fd98e422ad7eb762c4c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778227"
---
# <a name="pidtagresourcepath-canonical-property"></a>PidTagResourcePath 规范属性

  
  
**适用于**： Outlook 
  
包含服务提供商的服务器的路径。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOURCE_PATH，PR_RESOURCE_PATH_A，PR_RESOURCE_PATH_W  <br/> |
|标识符：  <br/> |0x3E07  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>说明

这些属性中包含的路径代表所建议的路径，用户可以在何处找到资源。 提供程序特定的这些属性定义。 例如，计划应用程序使用这些属性来指定其日程安排的应用程序文件的建议的位置。
  
消息的用户配置文件提供这些属性为方便起见，以便客户端应用程序不必提示消息用户输入的网络路径或网络驱动器号。
  
MAPI 仅适用于协会 (ANSI) 字符集中的文件名。 使用文件名的原始设备制造商 (OEM) 字符集中的应用程序必须将其转换为 ANSI 调用 MAPI 之前。
  
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

