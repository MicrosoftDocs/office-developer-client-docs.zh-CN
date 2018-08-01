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
ms.openlocfilehash: 01a65306e5e0d34ed6f1ce7231227224868ff5cb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778454"
---
# <a name="pidtagstatus-canonical-property"></a>PidTagStatus 规范属性

  
  
**适用于**： Outlook 
  
包含定义文件夹的状态标志的 32 位位掩码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STATUS  <br/> |
|标识符：  <br/> |0x360B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>说明

文件夹此属性是类似于邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性。 它的标志为客户端应用程序仅提供并不影响消息存储库。 客户端可以使用或忽略这些设置。 客户端还可以定义自己的此属性的客户端贴合位的值。
  
可以为位掩码设置一个或多个以下标志：
  
FLDSTATUS_DELMARKED 
  
> 文件夹标记为删除。 客户端应用程序设置此标志。
    
FLDSTATUS_HIDDEN 
  
> 文件夹处于隐藏状态。
    
FLDSTATUS_HIGHLIGHTED 
  
> 文件夹突出显示，例如，反向中显示视频。
    
FLDSTATUS_TAGGED 
  
> 文件夹被标记。
    
消息存储提供程序将此属性设置在到一个文件夹或多个这些值和客户端解释根据其应用程序的状态。 例如，客户端可以使用文件夹状态直观地区分在相同的方式显示相同状态的文件夹的层次结构表中的文件夹。 突出显示的文件夹可以显示反向视频、 标记文件夹中标记为删除文件夹可以显示包含有意义的图标，并可以隐藏隐藏的文件夹。
  
位 16 到 31 (通过"0x80000000"的"0x10000")，此属性是可供使用 IPM 客户端应用程序。 所有其他位供使用通过 MAPI;未定义上述列表中的值应最初设置为零并不会改动。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
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

