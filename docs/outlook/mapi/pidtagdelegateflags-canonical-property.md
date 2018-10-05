---
title: PidTagDelegateFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDelegateFlags
api_type:
- HeaderDef
ms.assetid: 3a504594-204c-472c-8be7-dca154c94ea2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 20ffc6f7f4d21f980e5f0f387464430ba187192a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392275"
---
# <a name="pidtagdelegateflags-canonical-property"></a>PidTagDelegateFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定代理人是否可查看 delegator 私有消息对象。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DELEGATE_FLAGS  <br/> |
|标识符：  <br/> |0x686B  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |类定义消息可传送  <br/> |
   
## <a name="remarks"></a>说明

每个条目的此属性必须设置为下列值之一。
  
|**Flag**|**值**|**说明**|
|:-----|:-----|:-----|
|HidePrivate  <br/> |0  <br/> |该委托不应允许查看私有消息对象。  <br/> |
|ShowPrivate  <br/> |1  <br/> |应允许委托查看私有消息对象。  <br/> |
   
此属性必须设置委托信息对象中。 "ShowPrivate"的值指示代理者希望公开私有消息对象。 适用于所有文件夹委托有审阅者、 作者或编辑器角色此首选项。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。
    
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

