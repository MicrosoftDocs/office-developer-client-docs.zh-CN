---
title: PidTagJunkThreshold 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkThreshold
api_type:
- HeaderDef
ms.assetid: 8067e2b5-02df-4b96-8f66-509f5a48c8aa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d4337105b2dcae94956f0b1badf66c663467dc3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565660"
---
# <a name="pidtagjunkthreshold-canonical-property"></a>PidTagJunkThreshold 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
力度指示应将传入邮件发送到垃圾邮件文件夹。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_JUNK_THRESHOLD  <br/> |
|标识符：  <br/> |0x6101  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性对应于高 / 低/无筛选设置。 "0xFFFFFFFF"的值表示的垃圾邮件筛选不应将应用，但仍必须应用阻止列表。 "0x80000000"值表示的所有邮件是除这些来自受信任的发件人列表上的发件人的邮件的垃圾邮件或发送到受信任的收件人列表上的收件人。 参数的值如下所示：
  
|**值**|**说明**|
|:-----|:-----|
|0xFFFFFFFF  <br/> |无垃圾邮件筛选  <br/> |
|0x00000006  <br/> |低垃圾邮件筛选  <br/> |
|0x00000003  <br/> |高垃圾邮件筛选  <br/> |
|0x80000000  <br/> |仅受信任的列表  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许处理的允许/阻止列表，并确定的垃圾邮件。
    
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

