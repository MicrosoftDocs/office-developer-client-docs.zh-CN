---
title: PidTagDisplayTo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayTo
api_type:
- HeaderDef
ms.assetid: 700cc03b-5d98-40ce-adb5-a11fdac8aa28
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0c7ae8951b02f099161871b17ff59ea23f8fbcc4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360786"
---
# <a name="pidtagdisplayto-canonical-property"></a>PidTagDisplayTo 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含主 (收件人) 邮件收件人的显示名称列表, 用分号 (;) 分隔)。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISPLAY_TO、PR_DISPLAY_TO_A、PR_DISPLAY_TO_W  <br/> |
|标识符:  <br/> |0x0E04  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |消息  <br/> |
   
## <a name="remarks"></a>注解

邮件存储区使用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法计算邮件对象上的这些属性。 邮件存储区还将维护这些属性, 以便它始终反映邮件的上次保存状态。 值在每次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法时进行同步。 
  
如果邮件没有主收件人, 则邮件存储应响应返回值 S_OK 的[IMAPIProp:: GetProps](imapiprop-getprops.md)调用和**PR_DISPLAY_TO**的空字符串。 
  
出于本地化的可能需要, MAPI 为所有收件人名称提供了以下准则:
  
- 所有名称都应能够本地化。 
    
- 分号应为用于分隔**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))、 **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和**PR_DISPLAY_TO**属性中的名称的字符。 MAPI 中的收件人名称内不允许使用分号。 
    
- 客户端应将在**PR_DISPLAY_TO**和相关属性中遇到的每个分号转换为本地化的分隔符, 然后再使信息在用户界面中可见。 
    
- 转发邮件时, 客户端无需翻译主收件人行上的分隔符。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
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

