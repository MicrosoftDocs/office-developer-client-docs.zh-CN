---
title: PidTagReportName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReportName
api_type:
- COM
ms.assetid: 4ec3100f-7cf1-4702-b326-e6da586a7bb2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 33a7545f9b2719615617d46e2d5ed1f6952b5522
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335425"
---
# <a name="pidtagreportname-canonical-property"></a>PidTagReportName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含应获取此邮件报告的收件人的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REPORT_NAME、PR_REPORT_NAME_A、PR_REPORT_NAME_W  <br/> |
|标识符:  <br/> |0x003A  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>注解

这些属性是发件人为接收此邮件生成的任何报告而委派的收件人地址属性的示例。
  
必须将报告路由到另一个用户的客户端应用程序应在邮件提交时设置这些属性。 如果未设置, 则会将报告发送给邮件发件人。
  
## <a name="related-resources"></a>相关资源

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

