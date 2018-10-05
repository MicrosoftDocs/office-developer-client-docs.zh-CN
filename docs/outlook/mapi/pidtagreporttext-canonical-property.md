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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396020"
---
# <a name="pidtagreporttext-canonical-property"></a>PidTagReportText 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含可选文字由消息系统生成的报告。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REPORT_TEXT，PR_REPORT_TEXT_A，PR_REPORT_TEXT_W  <br/> |
|标识符：  <br/> |0x1001  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 邮件  <br/> |
   
## <a name="remarks"></a>说明

通常，这些属性中包含的文本，以响应传递或原件报表或读取或从基础的消息系统，收到 nonread 的报告生成，但本身不是通过该系统已传输的文本。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件中允许的操作。
    
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

