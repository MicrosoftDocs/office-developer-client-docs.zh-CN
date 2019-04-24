---
title: PidTagJunkAddRecipientsToSafeSendersList 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkAddRecipientsToSafeSendersList
api_type:
- HeaderDef
ms.assetid: 78543caa-e6ec-4ac7-bfdd-70c56f8fd955
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3a87beaa3873b5ccb449e5b1497262bad5bf1497
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282366"
---
# <a name="pidtagjunkaddrecipientstosafesenderslist-canonical-property"></a>PidTagJunkAddRecipientsToSafeSendersList 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示是否要将邮件收件人添加到 "安全发件人" 列表中。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_JUNK_ADD_RECIPS_TO_SSL  <br/> |
|标识符:  <br/> |0x6103  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="remarks"></a>注解

如果存在此属性, 则必须将此属性设置为0或1。 值为1表示要将邮件收件人添加到安全发件人列表中。 值为0表示不将邮件收件人添加到安全发件人列表中。
  
如果此属性的值为 1, 则必须将电子邮件收件人的 SMTP 地址添加到垃圾邮件规则条件的受信任发件人子句中。 如果此属性为 0, 则无需执行任何操作。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 启用对允许/阻止列表的处理以及确定垃圾邮件。
    
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

