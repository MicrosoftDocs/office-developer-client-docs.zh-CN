---
title: CloseSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2c2371c8-b0e0-4992-b7ac-3949eadf1ebe
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9186fb14c33d507b8c9ae709a67f1b43e6206d5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304135"
---
# <a name="closesession"></a>CloseSession

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
结束与群集的会话。
  
```cpp
int CloseSession(int SessionId)
```

## <a name="parameters"></a>参数

_SessionId_
  
> 要关闭的会话的 ID。 此值必须与[OpenSession](opensession.md)返回的值相匹配。
    
## <a name="return-value"></a>返回值

如果会话已关闭, 则为**xlHpcRetSuccess** ;**xlHpcRetInvalidSessionId**如果_SessionId_参数无效, 则为有关其他故障的**xlHpcRetCallFailed** 。 
  
## <a name="see-also"></a>另请参阅

- [OpenSession](opensession.md)
- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

