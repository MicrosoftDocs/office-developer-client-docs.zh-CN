---
title: PidTagDisplayBcc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayBcc
api_type:
- HeaderDef
ms.assetid: ab5bcd67-d54e-46e9-b94e-a652aac3e81c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 74669d102462e1a825568615d1d30346e99e90a6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360814"
---
# <a name="pidtagdisplaybcc-canonical-property"></a>PidTagDisplayBcc 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含任何"BCC"邮件收件人的"BCC (") 的显示名称的 ASCII 列表，用分号 (;) 。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISPLAY_BCC、PR_DISPLAY_BCC_A、PR_DISPLAY_BCC_W  <br/> |
|标识符:  <br/> |0x0E02  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |邮件  <br/> |
   
## <a name="remarks"></a>备注

邮件存储使用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法计算 message 对象上的这些属性。 邮件存储还维护这些属性，以便它始终反映邮件的上次保存状态。 每次调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法时，将同步该值。 
  
如果邮件没有"无邮件副本"收件人，则邮件存储应响应 [IMAPIProp：：GetProps](imapiprop-getprops.md) 调用，其返回值为 S_OK 且空字符串表示 **PR_DISPLAY_BCC**。 
  
由于可能需要进行本地化，MAPI 针对所有收件人姓名提供了以下指南：
  
- 所有名称都应能够本地化。 
    
- 分号应为用于分隔 **PR_DISPLAY_BCC、PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和 PR_DISPLAY_TO ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 属性中的名称的字符。 MAPI 中的收件人名称中不允许使用分号。 
    
- 客户端应在用户界面中显示属性信息之前，将此属性中遇到的每个分号转换为本地化分隔符。 
    
- 转发邮件时，客户端无需翻译"抄稿收件人行"上的分隔符。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 描述用于发送与客户端上的共享文件夹有关的信息的邮件的格式。
    
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

