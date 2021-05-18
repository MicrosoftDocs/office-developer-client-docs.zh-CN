---
title: 更新 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: faafde3d-3989-4182-91f1-a0cf0f1b5388
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c2c733b87b85971fad8060040e713b41b0f5616
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407520"
---
# <a name="updating-mapi-properties"></a>更新 MAPI 属性

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端和服务提供商可以通过调用：
  
- 对象的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法，用于更新对象的一个或多个属性的值。 
    
- [HrSetOneProp](hrsetoneprop.md)函数一次仅更新一个属性。 仅在目标对象是本地对象时，才使用 **HrSetOneProp;** 当与远程对象一起使用时，此函数可能会导致性能下降。 
    
以下过程说明如何使用 **SetProps** 更新邮件的邮件类PR_MESSAGE_CLASS_A ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。 
  
### <a name="to-update-the-message-class-of-a-message"></a>更新邮件的邮件类 
  
1. 为邮件 [类分配 SPropValue](spropvalue.md) 结构并适当设置其成员。 
    
  ```cpp
    SPropValue spvMsgClass;
    spvMsgClass.ulPropTag = PR_MESSAGE_CLASS_A;
    spvMsgClass.Value.lpszA = "IPM.NewClass";
    
  ```

2. 调用邮件的 **IMAPIProp：：SetProps** 方法来设置新邮件类。 
    
  ```cpp
    hRes = lpMessage->SetProps(1, (LPSPropValue) &spvMsgClass, NULL);
  ```

## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

