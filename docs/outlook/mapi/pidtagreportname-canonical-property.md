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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422311"
---
# <a name="pidtagreportname-canonical-property"></a>PidTagReportName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含显示名称应获取此邮件的报告的收件人的邮箱。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REPORT_NAME、PR_REPORT_NAME_A、PR_REPORT_NAME_W  <br/> |
|标识符:  <br/> |0x003A  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

这些属性是发件人已委派接收为此邮件生成的任何报表的收件人的地址属性示例。
  
必须将报告路由到其他用户的客户端应用程序应在邮件提交时设置这些属性。 如果未设置报告，则报告将发送给邮件发件人。
  
## <a name="related-resources"></a>相关资源

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

