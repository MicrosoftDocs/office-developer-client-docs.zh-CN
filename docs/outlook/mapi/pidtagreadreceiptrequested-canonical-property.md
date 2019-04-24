---
title: PidTagReadReceiptRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReadReceiptRequested
api_type:
- COM
ms.assetid: 7db0645b-f3ab-4fc4-b865-68c952aeb359
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e49b73c777988ad3559a442af920af3d8f4bdbb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356467"
---
# <a name="pidtagreadreceiptrequested-canonical-property"></a>PidTagReadReceiptRequested 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件发件人希望邮件系统在收件人阅读邮件时生成阅读报告, 则该参数为 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_READ_RECEIPT_REQUESTED  <br/> |
|标识符:  <br/> |0x0029  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性必须设置为 TRUE, 以验证**PR_READ_RECEIPT_ENTRYID** ([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md)) 和**PR_READ_RECEIPT_SEARCH_KEY** ([PidTagReadReceiptSearchKey](pidtagreadreceiptsearchkey-canonical-property.md)) 属性中的值。
  
如果在邮件系统可以生成已读报告之前, **PR_READ_RECEIPT_REQUESTED**设置的邮件已被删除或过期, 则会生成未读报告。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
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

