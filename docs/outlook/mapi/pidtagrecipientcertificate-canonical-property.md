---
title: PidTagRecipientCertificate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientCertificate
api_type:
- COM
ms.assetid: 7c5c749e-5463-4935-85b5-32219d06f782
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c659b77767fddc4c783732082c2eb65c68af8dbf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431664"
---
# <a name="pidtagrecipientcertificate-canonical-property"></a>PidTagRecipientCertificate 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个邮件收件人的 ASN. 1 个用于报表的证书。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_CERTIFICATE  <br/> |
|标识符:  <br/> |0x0C13  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 收件人  <br/> |
   
## <a name="remarks"></a>说明

此属性是收件人的**PR_USER_CERTIFICATE** ([PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) 属性的副本, 用于在报表中使用。 它可用于向发信人证明收件人实际收到的邮件, 但传递报告并不一定表示。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

