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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429857"
---
# <a name="pidtagresourcepath-canonical-property"></a>PidTagResourcePath 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指向服务提供商服务器的路径。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOURCE_PATH、PR_RESOURCE_PATH_A、PR_RESOURCE_PATH_W  <br/> |
|标识符:  <br/> |0x3E07  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>备注

这些属性中包含的路径表示建议的路径，用户可以在路径中查找资源。 这些属性的定义特定于提供程序。 例如，计划应用程序使用这些属性来指定其计划应用程序文件的建议位置。
  
邮件传递用户配置文件提供这些属性是一种便利，以便客户端应用程序无需提示消息用户输入网络路径或网络驱动器号。
  
MAPI 仅适用于美国国家标准协会的文件名 (ANSI) 字符集。 使用原始设备制造商中的文件名的应用程序 (OEM) 集必须先将其转换为 ANSI，然后才能调用 MAPI。
  
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

