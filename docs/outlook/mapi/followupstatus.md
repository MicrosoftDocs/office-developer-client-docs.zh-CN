---
title: FollowUpStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c3d0f6c4-4597-784f-8d44-6e5d905895b4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e59c0ba7810741943883b9e86e84c6fe141f3050
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774953"
---
# <a name="followupstatus"></a>FollowUpStatus

  
  
**适用于**： Outlook 
  
指定不同的后续状态邮件。
  
## <a name="quick-info"></a>快速信息

```cpp
enum FollowUpStatus { 
    flwupNone = 0, 
    flwupComplete, 
    flwupMarked, 
    flwupMAX}; 

```

## <a name="members"></a>Members

 _flwupNone_
  
> 已指定没有进行后续工作。
    
 _flwupComplete_
  
> 邮件已完成。
    
 _flwupMarked_
  
> 邮件标记为需要后续操作。
    
 _flwupMAX_
  
> 为需要后续操作支持的不同状态数。
    
## <a name="see-also"></a>另请参阅



[PidTagFlagStatus 规范属性](pidtagflagstatus-canonical-property.md)

