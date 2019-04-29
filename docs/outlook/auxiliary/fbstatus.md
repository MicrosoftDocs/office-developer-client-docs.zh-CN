---
title: FBStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f2d6a11e-847d-6bbe-cd77-e78ee961cb12
description: "\"忙/闲\" 块的 \"忙/闲\" 状态的枚举。"
ms.openlocfilehash: 2a08ef142f9baddd453166c0ebcb989e69a51ceb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424089"
---
# <a name="fbstatus"></a>FBStatus

"忙/闲" 块的 "忙/闲" 状态的枚举。
  
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

## <a name="remarks"></a>说明

一段时间的忙/闲状态决定了它在日历中的显示方式:**闲**、**忙**、**暂定**或外出。 **** 
  
## <a name="see-also"></a>另请参阅

- [FBBlock_1](fbblock_1.md)
- [IEnumFBBlock::Next](ienumfbblock-next.md)

