---
title: 更新 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: faafde3d-3989-4182-91f1-a0cf0f1b5388
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5cff3a6cbf4bfca7b414f9663e71834da71926d7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779031"
---
# <a name="updating-mapi-properties"></a>更新 MAPI 属性

**适用于**： Outlook 
  
客户端和服务提供商可以通过调用更新的属性值：
  
- 若要更新的一个或多个对象的属性值的对象的[IMAPIProp::SetProps](imapiprop-setprops.md)方法。 
    
- 用于更新一次只有一个属性的[HrSetOneProp](hrsetoneprop.md)函数。 仅在本地; 目标对象是否使用**HrSetOneProp**此函数可能会导致与远程对象一起使用时的性能下降。 
    
下面的过程说明如何使用**SetProps**更新的邮件类或 PR_MESSAGE_CLASS_A ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性，一条消息。 
  
### <a name="to-update-the-message-class-of-a-message"></a>若要更新的邮件的邮件类 
  
1. 为邮件类分配[SPropValue](spropvalue.md)结构，并根据需要设置及其成员。 
    
  ```cpp
    SPropValue spvMsgClass;
    spvMsgClass.ulPropTag = PR_MESSAGE_CLASS_A;
    spvMsgClass.Value.lpszA = "IPM.NewClass";
    
  ```

2. 调用消息的**IMAPIProp::SetProps**方法，以设置新的邮件类。 
    
  ```cpp
    hRes = lpMessage->SetProps(1, (LPSPropValue) &spvMsgClass, NULL);
  ```

## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

