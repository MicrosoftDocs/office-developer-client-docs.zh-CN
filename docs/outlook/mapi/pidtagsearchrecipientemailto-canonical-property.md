---
title: PidTagSearchRecipientEmailTo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f5de77c3-5912-f7bc-8e8c-3a053545c359
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d254df132db5542ce5235c1c3ab42ea768399f0a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358917"
---
# <a name="pidtagsearchrecipientemailto-canonical-property"></a>PidTagSearchRecipientEmailTo 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 Unicode 字符串，该字符串正在电子邮件地址列表中查询，或显示在存储上邮件的"收件人"行中地址的收件人姓名。 
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEARCH_RECIP_EMAIL_TO_W  <br/> |
|标识符:  <br/> |0x0EA6  <br/> |
|属性类型  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |搜索  <br/> |
   
## <a name="related-resources"></a>相关资源

> [!NOTE]
> 当您搜索电子邮件地址或显示邮件发送到的名称时，可能不会在当前具有的可下载头文件中定义此 MAPI 限制标记。 可以使用以下值将其添加到代码中：>  `#define PR_SEARCH_RECIP_EMAIL_TO_W PROP_TAG(PT_UNICODE, 0x0EA6)`
  
### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Microsoft Exchange Server的引用。
    
[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)
  
> 指定用于操作搜索文件夹列表配置的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为备用名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

