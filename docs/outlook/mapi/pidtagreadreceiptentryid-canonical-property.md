---
title: PidTagReadReceiptEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReadReceiptEntryId
api_type:
- COM
ms.assetid: 141d49c8-87cf-4d80-a33b-ccbf3eeae19e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 662c191f36f9ca30dcdf0f559ea5385bfe5fd305
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356504"
---
# <a name="pidtagreadreceiptentryid-canonical-property"></a>PidTagReadReceiptEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件用户条目标识符，邮件系统应在其中指示此邮件的阅读报告。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_READ_RECEIPT_ENTRYID  <br/> |
|标识符:  <br/> |0x0046  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

除非[PidTagReadReceiptRequested PR_READ_RECEIPT_REQUESTED (PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性设置为 TRUE，否则将忽略此属性。 
  
如果客户端应用程序想要接收阅读报告本身，它可以保持该属性未设置，或设置为邮件提交时 PR_SENDER_ENTRYID ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md) **)** 属性中包含的条目标识符。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许对电子邮件对象执行的属性和操作。
    
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

