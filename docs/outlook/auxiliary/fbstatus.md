---
title: FBStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f2d6a11e-847d-6bbe-cd77-e78ee961cb12
description: 忙/闲状态的忙/闲块枚举。
ms.openlocfilehash: 67d710f82856dc8ff4839c926018eef88d355f73
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19774185"
---
# <a name="fbstatus"></a>FBStatus

忙/闲状态的忙/闲块枚举。
  
## <a name="quick-info"></a>快速信息

```cpp
enum  
    { 
      fbFree      = 0, 
      fbTentative = fbFree + 1, 
      fbBusy      = fbTentative + 1, 
      fbOutOfOffice = fbBusy + 1 
    }

```

## <a name="remarks"></a>注解

一段时间的忙/闲状态确定它在日历上的显示方式：**免费**、**忙碌**、**暂定**，或**外出时的**。 
  
## <a name="see-also"></a>另请参阅

- [FBBlock_1](fbblock_1.md)
- [IEnumFBBlock::Next](ienumfbblock-next.md)

