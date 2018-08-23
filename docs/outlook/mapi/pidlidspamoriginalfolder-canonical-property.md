---
title: PidLidSpamOriginalFolder 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSpamOriginalFolder
api_type:
- COM
ms.assetid: 45846fe3-7ab3-4019-98bb-fe615889c31c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 639d5e96eb56fb543d6a6026b1c9400631cee819
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593338"
---
# <a name="pidlidspamoriginalfolder-canonical-property"></a>PidLidSpamOriginalFolder 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示一条消息之前已在哪个文件夹而被筛选出到垃圾邮件文件夹。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSpamOriginalFolder  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x0000859C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性的值是文件夹的包含邮件之前它已移动的**EntryID** 。 邮件标记为垃圾邮件时，应设置该属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许处理的允许/阻止列表，并确定的垃圾邮件。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

