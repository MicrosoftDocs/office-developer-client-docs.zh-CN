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
ms.openlocfilehash: 4d3a38f55fa2869df3f8afa1301cf1ad0c7b0737
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778215"
---
# <a name="pidtagreportname-canonical-property"></a>PidTagReportName 规范属性

  
  
**适用于**： Outlook 
  
包含应获得此消息报告的收件人的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REPORT_NAME，PR_REPORT_NAME_A，PR_REPORT_NAME_W  <br/> |
|标识符：  <br/> |0x003A  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>说明

这些属性是发件人已委派接收此消息生成任何报告的收件人的地址属性的示例。
  
必须将报表路由到另一个用户的客户端应用程序应在消息提交时设置这些属性。 如果未设置这些属性，报告将发送给邮件发件人。
  
## <a name="related-resources"></a>相关资源

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

