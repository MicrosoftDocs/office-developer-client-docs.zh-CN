---
title: PidTagReportText 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReportTag
api_type:
- COM
ms.assetid: 09bd3bdf-28d6-432c-9213-562a9a271adc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7173caa7a31bc3ad11a4785b6a1498aba139de7c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359190"
---
# <a name="pidtagreporttext-canonical-property"></a>PidTagReportText 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件系统生成的报告的可选文字。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REPORT_TEXT、PR_REPORT_TEXT_A、PR_REPORT_TEXT_W  <br/> |
|标识符:  <br/> |0x1001  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 邮件  <br/> |
   
## <a name="remarks"></a>注解

通常, 这些属性中包含的文本是为了响应传递或 nondelivery 报告或从基础邮件系统接收到的读取或未读报告而生成的, 但它本身并不是通过该系统传输的文本。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定在电子邮件中允许的属性和操作。
    
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

