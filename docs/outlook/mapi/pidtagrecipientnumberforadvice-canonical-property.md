---
title: PidTagRecipientNumberForAdvice 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientNumberForAdvice
api_type:
- COM
ms.assetid: 636c1e75-3024-43ca-a7dd-1bb480dfbb5b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ac4da2d4082cac632548594411528b7bf1d6dc64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778146"
---
# <a name="pidtagrecipientnumberforadvice-canonical-property"></a>PidTagRecipientNumberForAdvice 规范属性

  
  
**适用于**： Outlook 
  
此属性包含要呼叫的物理传送一条消息告知的邮件收件人的电话号码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_NUMBER_FOR_ADVICE，PR_RECIPIENT_NUMBER_FOR_ADVICE_A，PR_RECIPIENT_NUMBER_FOR_ADVICE_W  <br/> |
|标识符：  <br/> |0x0C14  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 收件人  <br/> |
   
## <a name="remarks"></a>说明

这些属性是为了时 human 收件人不应存在于传递与传递到物理目标，而不是电子邮箱，配合使用。 例如，传真封面工作表上的电话号码。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

