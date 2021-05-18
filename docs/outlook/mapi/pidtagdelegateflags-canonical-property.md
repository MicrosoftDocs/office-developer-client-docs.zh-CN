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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359897"
---
# <a name="pidtagdelegateflags-canonical-property"></a>PidTagDelegateFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定代理是否可以查看代理者的私人邮件对象。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DELEGATE_FLAGS  <br/> |
|标识符:  <br/> |0x686B  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |邮件类定义的可传输  <br/> |
   
## <a name="remarks"></a>备注

此属性的每个条目必须设置为下列值之一。
  
|**Flag**|**值**|**说明**|
|:-----|:-----|:-----|
|HidePrivate  <br/> |0  <br/> |不应允许代理查看私人邮件对象。  <br/> |
|ShowPrivate  <br/> |1  <br/> |应允许代理查看私人邮件对象。  <br/> |
   
此属性必须在委托信息对象中设置。 "ShowPrivate"的值指示委派者希望使私人邮件对象可见。 此首选项适用于代理具有审阅者、作者或编辑者角色的所有文件夹。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。
    
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

