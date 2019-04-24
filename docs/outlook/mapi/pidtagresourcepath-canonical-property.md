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
ms.openlocfilehash: 32d150e508f5c208e15d5ee5f0b8c800a1e597f9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330168"
---
# <a name="pidtagresourcepath-canonical-property"></a>PidTagResourcePath 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含服务提供程序的服务器的路径。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOURCE_PATH、PR_RESOURCE_PATH_A、PR_RESOURCE_PATH_W  <br/> |
|标识符:  <br/> |0x3E07  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

这些属性中包含的路径表示用户可以在其中查找资源的建议路径。 这些属性的定义是特定于提供程序的。 例如, 计划应用程序使用这些属性为其计划应用程序文件指定建议的位置。
  
邮件用户配置文件提供这些属性的目的是为了方便客户端应用程序不必提示消息用户输入网络路径或网络驱动器号。
  
MAPI 仅适用于美国国家标准协会 (ANSI) 字符集中的文件名。 使用原始设备制造商 (OEM) 字符集中的文件名的应用程序必须先将其转换为 ANSI, 然后再调用 MAPI。
  
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

