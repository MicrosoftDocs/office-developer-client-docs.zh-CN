---
title: PidTagStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStatus
api_type:
- COM
ms.assetid: 8b947660-eafe-47e1-9595-bd3ab7d455bf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de2342ef4d3e9d06f198e06dc19c65b7b144624f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278790"
---
# <a name="pidtagstatus-canonical-property"></a>PidTagStatus 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含标志的32位位掩码, 用于定义文件夹状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STATUS  <br/> |
|标识符:  <br/> |0x360B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>注解

文件夹的此属性类似于邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性。 仅为客户端应用程序提供其标志, 而不会影响邮件存储区。 客户端可以使用或忽略这些设置。 客户端还可以为此属性的客户端可定义的位定义其自己的值。
  
可以为位掩码设置以下一个或多个标志:
  
FLDSTATUS_DELMARKED 
  
> 将文件夹标记为删除。 客户端应用程序设置此标志。
    
FLDSTATUS_HIDDEN 
  
> 文件夹已被隐藏。
    
FLDSTATUS_HIGHLIGHTED 
  
> 将突出显示该文件夹, 例如 "反向视频"。
    
FLDSTATUS_TAGGED 
  
> 该文件夹已标记。
    
邮件存储提供程序将文件夹的此属性设置为一个或多个这些值, 客户端会将状态解释为适用于其应用程序的状态。 例如, 客户端可以使用文件夹状态以直观方式区分层次结构表中的文件夹, 以相同的方式显示具有相同状态的文件夹。 突出显示的文件夹可以显示在反向视频中, 标记为删除的已标记文件夹和文件夹可以用有意义的图标显示, 并且隐藏的文件夹可以隐藏。
  
此属性的位16至 31 ("0x80000000") 可供 IPM 客户端应用程序使用。 保留所有其他位以供 MAPI 使用;前面的列表中未定义的那些值最初应设置为零且不会改变。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
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

