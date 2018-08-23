---
title: PidTagMessageCodepage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageCodepage
api_type:
- HeaderDef
ms.assetid: eef73e34-470c-4c37-94ce-ea95fe83bc10
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f75a5e10a59d7c6db4e43d2552a38d523b537790
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580199"
---
# <a name="pidtagmessagecodepage-canonical-property"></a>PidTagMessageCodepage 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含用于消息的代码页。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_CODEPAGE  <br/> |
|标识符：  <br/> |0x3FFD  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Common  <br/> |
   
## <a name="remarks"></a>注解

如果此属性设置为零 (0)，则使用的文件夹对象代码页。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXPFOAB]](http://msdn.microsoft.com/library/258a07a7-34a7-4373-87c1-cddf51447d00%28Office.15%29.aspx)
  
> 指定从服务器的脱机通讯簿 (OAB) 数据交付给客户端的方法。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

