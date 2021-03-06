---
title: PidTagSpamTrustedRecipients 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 59f43316-3ff6-4ed0-bc29-b31039192b08
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 521bdb280776be28d3526471888834bbd7da0b9f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359449"
---
# <a name="pidtagspamtrustedrecipients-canonical-property"></a>PidTagSpamTrustedRecipients 规范属性
 
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个以分号分隔的电子邮件地址和域的列表，这些地址和域代表受信任的收件人。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SPAM_TRUSTED_RECIPIENTS_W  <br/> |
|LONG ID (的一) ：  <br/> |0x0419  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Microsoft Exchange Server引用。
    
[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许/阻止列表的处理和垃圾邮件的确定。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为备用名称的属性的定义。
    
## <a name="see-also"></a>另请参阅

- [MAPI 属性](mapi-properties.md) 
- [MAPI 规范属性](mapi-canonical-properties.md)  
- [将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)  
- [将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

