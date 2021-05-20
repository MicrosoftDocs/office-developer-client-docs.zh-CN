---
title: PidTagOriginCheck 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginCheck
api_type:
- COM
ms.assetid: 27e0ab2f-b373-41ae-b922-2f45f9671ac6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a82b1351c9d2d19c32e34b03a537a12bf93deb8a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435759"
---
# <a name="pidtagorigincheck-canonical-property"></a>PidTagOriginCheck 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个二进制验证值，它使送达报告收件人能够验证原始邮件的来源。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGIN_CHECK  <br/> |
|标识符:  <br/> |0x0027  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |服务器  <br/> |
   
## <a name="remarks"></a>备注

此属性为第三方（如邮件传输代理 (MTA) 或接收送达报告的邮件用户）提供了一种验证已提交邮件来源的方式。 如果收到的邮件上存在此属性，则此属性应复制到为响应邮件而生成的任何送达报告。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

