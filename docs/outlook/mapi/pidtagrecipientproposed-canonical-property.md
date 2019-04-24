---
title: PidTagRecipientProposed 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientProposed
api_type:
- COM
ms.assetid: 8cb0e46c-0937-482f-be78-1f2e5261b210
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1b09d8d7621121b3652ceb9824f6d36b53844206
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283133"
---
# <a name="pidtagrecipientproposed-canonical-property"></a>PidTagRecipientProposed 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示会议与会者是否已响应。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_PROPOSED  <br/> |
|标识符:  <br/> |0x5FE1  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |传输收件人  <br/> |
   
## <a name="remarks"></a>注解

如果此属性的值为 TRUE, 则表示与会者建议了新的日期和/或时间。 如果值为 FALSE 或缺少此属性, 则表示与会者尚未响应, 或者与会者的最近响应不包含新的日期/时间建议。 对于定期系列中的与会者, 此值不得为 TRUE。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
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

