---
title: PidTagMailPermission 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMailPermission
api_type:
- HeaderDef
ms.assetid: f8270ef2-56d4-4b47-bdda-a39c966bbcba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b396cd326dd25fd72346f9f8037e8a712b84a196
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278870"
---
# <a name="pidtagmailpermission-canonical-property"></a>PidTagMailPermission 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果允许邮件用户发送和接收邮件, 则该参数为 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MAIL_PERMISSION  <br/> |
|标识符:  <br/> |0x3A0E  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>注解

如果未设置此属性, 则 MAPI 会将其视为具有真正的值。 
  
将此属性设置为 FALSE, 其中某些条目未启用电子邮件的公司目录。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

