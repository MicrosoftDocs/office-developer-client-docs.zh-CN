---
title: PidTagSearchRecipientEmailBcc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d9561d13-8d52-500c-5369-15a2cf5c92c3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5b0db4b3bc7903aae74fa7275d3e27e22d628514
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359155"
---
# <a name="pidtagsearchrecipientemailbcc-canonical-property"></a>PidTagSearchRecipientEmailBcc 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 Unicode 字符串，该字符串正在电子邮件地址列表中查询，或在存储上未发送邮件的 **"BCC"** 行中显示收件人的姓名。 
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEARCH_RECIP_EMAIL_BCC_W  <br/> |
|标识符:  <br/> |0x0EA8  <br/> |
|属性类型  <br/> |PT_UNICODE  <br/> |
|访问权限  <br/> |搜索  <br/> |
   
## <a name="remarks"></a>备注

此属性仅与存储上尚未发送的邮件相关，因为已发送或接收的邮件不包含 BCC 信息。
  
> [!NOTE]
> 此 MAPI 限制标记（在搜索电子邮件地址或显示邮件将作为副本发送到的名称）时可能未在当前具有的可下载头文件中定义。 可以使用以下值将其添加到代码中：>  `#define PR_SEARCH_RECIP_EMAIL_BCC_W PROP_TAG(PT_UNICODE, 0x0EA8)`
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Microsoft Exchange Server的引用。
    
[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)
  
> 指定用于操作搜索文件夹列表配置的属性和操作。
    
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

