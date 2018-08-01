---
title: PingSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4646659b-f932-4d11-a46f-4231bb397243
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 165be9eada54b2030471fc10e7a0bf0c7dcc7c8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773820"
---
# <a name="pingsession"></a>PingSession

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
检查会话是否有效。 当需要确定是否以前返回的会话 ID 仍处于活动状态，可以使用 Excel 通常调用此函数。
  
```cpp
int PingSession(int SessionId)
```

## <a name="parameters"></a>参数

_SessionID_
  
> Ping 会话的 ID。 此值必须匹配由[OpenSession](opensession.md)以前调用返回的 ID。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess** _SessionId_参数是否有效;否则为**xlHpcRetInvalidSessionId**。
  
## <a name="see-also"></a>另请参阅

- [OpenSession](opensession.md)
- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

