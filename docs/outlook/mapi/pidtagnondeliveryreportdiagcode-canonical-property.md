---
title: PidTagNonDeliveryReportDiagCode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNonDeliveryReportDiagCode
api_type:
- HeaderDef
ms.assetid: a39c0f54-bdca-498f-a75c-dd8702e5385a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 528e18964cacfb59f30667295b792e850353f3ea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579023"
---
# <a name="pidtagnondeliveryreportdiagcode-canonical-property"></a>PidTagNonDeliveryReportDiagCode 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含诊断代码的表单原件报表中的一部分。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_NDR_DIAG_CODE  <br/> |
|标识符：  <br/> |0x0C05  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

此属性可以具有完全下列值之一：
  
MAPI_DIAG_ALPHABETIC_CHARACTER_LOST 
  
> 
    
MAPI_DIAG_CONTENT_SYNTAX_IN_ERROR 
  
> 
    
MAPI_DIAG_CONTENT_TOO_LONG 
  
> 
    
MAPI_DIAG_CONTENT_TYPE_UNSUPPORTED 
  
> 
    
MAPI_DIAG_CONVERSION_LOSS_PROHIB 
  
> 
    
MAPI_DIAG_CONVERSION_UNSUBSCRIBED 
  
> 
    
MAPI_DIAG_CRITICAL_FUNC_UNSUPPORTED 
  
> 
    
MAPI_DIAG_EITS_UNSUPPORTED 
  
> 
    
MAPI_DIAG_EXPANSION_FAILED 
  
> 
    
MAPI_DIAG_EXPANSION_PROHIBITED 
  
> 
    
MAPI_DIAG_IMPRACTICAL_TO_CONVERT 
  
> 
    
MAPI_DIAG_LENGTH_CONSTRAINT_VIOLATD 
  
> 
    
MAPI_DIAG_LINE_TOO_LONG 
  
> 
    
MAPI_DIAG_LOOP_DETECTED 
  
> 
    
MAPI_DIAG_MAIL_ADDRESS_INCOMPLETE 
  
> 
    
MAPI_DIAG_MAIL_ADDRESS_INCORRECT 
  
> 
    
MAPI_DIAG_MAIL_FORWARDING_PROHIB 
  
> 
    
MAPI_DIAG_MAIL_FORWARDING_UNWANTED 
  
> 
    
MAPI_DIAG_MAIL_NEW_ADDRESS_UNKNOWN 
  
> 
    
MAPI_DIAG_MAIL_OFFICE_INCOR_OR_INVD 
  
> 
    
MAPI_DIAG_MAIL_ORGANIZATION_EXPIRED 
  
> 
    
MAPI_DIAG_MAIL_RECIPIENT_DECEASED 
  
> 
    
MAPI_DIAG_MAIL_RECIPIENT_DEPARTED 
  
> 
    
MAPI_DIAG_MAIL_RECIPIENT_MOVED 
  
> 
    
MAPI_DIAG_MAIL_RECIPIENT_TRAVELLING 
  
> 
    
MAPI_DIAG_MAIL_RECIPIENT_UNKNOWN 
  
> 
    
MAPI_DIAG_MAIL_REFUSED 
  
> 
    
MAPI_DIAG_MAIL_UNCLAIMED 
  
> 
    
MAPI_DIAG_MAXIMUM_TIME_EXPIRED 
  
> 
    
MAPI_DIAG_MTS_CONGESTED 
  
> 
    
MAPI_DIAG_MULTIPLE_INFO_LOSSES 
  
> 
    
MAPI_DIAG_NO_BILATERAL_AGREEMENT 
  
> 
    
MAPI_DIAG_NO_DIAGNOSTIC 
  
> 
    
MAPI_DIAG_NUMBER_CONSTRAINT_VIOLATD 
  
> 
    
MAPI_DIAG_OR_NAME_AMBIGUOUS 
  
> 
    
MAPI_DIAG_OR_NAME_UNRECOGNIZED 
  
> 
    
MAPI_DIAG_PAGE_TOO_LONG 
  
> 
    
MAPI_DIAG_PARAMETERS_INVALID 
  
> 
    
MAPI_DIAG_PICTORIAL_SYMBOL_LOST 
  
> 
    
MAPI_DIAG_PROHIBITED_TO_CONVERT 
  
> 
    
MAPI_DIAG_PUNCTUATION_SYMBOL_LOST 
  
> 
    
MAPI_DIAG_REASSIGNMENT_PROHIBITED 
  
> 
    
MAPI_DIAG_RECIPIENT_UNAVAILABLE 
  
> 
    
MAPI_DIAG_REDIRECTION_LOOP_DETECTED 
  
> 
    
MAPI_DIAG_RENDITION_UNSUPPORTED 
  
> 
    
MAPI_DIAG_SECURE_MESSAGING_ERROR 
  
> 
    
MAPI_DIAG_SUBMISSION_PROHIBITED 
  
> 
    
MAPI_DIAG_TOO_MANY_RECIPIENTS 
  
> 
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagNonDeliveryReportReasonCode 规范属性](pidtagnondeliveryreportreasoncode-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

