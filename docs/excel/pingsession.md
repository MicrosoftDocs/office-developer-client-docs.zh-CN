---
title: PingSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4646659b-f932-4d11-a46f-4231bb397243
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0fa5fe57e537a7b8c7d880b934809a6f68ce27a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408360"
---
# <a name="pingsession"></a>PingSession

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
检查会话是否有效。 此函数通常在用户需要Excel返回的会话 ID 是否仍处于活动状态且可以使用时调用。
  
```cpp
int PingSession(int SessionId)
```

## <a name="parameters"></a>参数

_SessionID_
  
> 要 ping 的会话的 ID。 此值必须与上一次调用 [OpenSession](opensession.md)时返回的 ID 匹配。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess（** 如果  _SessionId_ 参数有效）;否则 **为 xlHpcRetInvalidSessionId**。
  
## <a name="see-also"></a>另请参阅

- [OpenSession](opensession.md)
- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

