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
ms.openlocfilehash: 4cc97647c60322783050abbebd18726434632a43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777829"
---
# <a name="pidtagmailpermission-canonical-property"></a>PidTagMailPermission 规范属性

  
  
**适用于**： Outlook 
  
包含 TRUE，则允许消息的用户发送和接收消息。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MAIL_PERMISSION  <br/> |
|标识符：  <br/> |0x3A0E  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>说明

如果未设置此属性，MAPI 会将其视为 TRUE 值。 
  
其中某些条目不启用电子邮件的此属性设置为 FALSE 企业目录中。 
  
## <a name="related-resources"></a>相关资源

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

