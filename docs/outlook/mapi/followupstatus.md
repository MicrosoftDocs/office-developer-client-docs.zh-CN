---
title: FollowUpStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c3d0f6c4-4597-784f-8d44-6e5d905895b4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2280ae9271ca73af33f395bf9e41a9ee8fa62f96
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327522"
---
# <a name="followupstatus"></a>FollowUpStatus

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定邮件的不同跟进状态。
  
## <a name="quick-info"></a>快速信息

```cpp
enum FollowUpStatus { 
    flwupNone = 0, 
    flwupComplete, 
    flwupMarked, 
    flwupMAX}; 

```

## <a name="members"></a>成员

 _flwupNone_
  
> 未指定跟进。
    
 _flwupComplete_
  
> 邮件已完成。
    
 _flwupMarked_
  
> 将邮件标记为待跟踪状态。
    
 _flwupMAX_
  
> 支持的不同状态的跟踪次数。
    
## <a name="see-also"></a>另请参阅



[PidTagFlagStatus 规范属性](pidtagflagstatus-canonical-property.md)

