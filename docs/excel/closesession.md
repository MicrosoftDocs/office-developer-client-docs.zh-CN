---
title: CloseSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2c2371c8-b0e0-4992-b7ac-3949eadf1ebe
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: af8f7398ed9d5edfbf1615930874a800d8835487
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773644"
---
# <a name="closesession"></a>CloseSession

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
结束与群集的会话。
  
```cpp
int CloseSession(int SessionId)
```

## <a name="parameters"></a>参数

_SessionId_
  
> 要关闭的会话 ID。 此值必须匹配[OpenSession](opensession.md)返回的值。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess**会话关闭; 如果**xlHpcRetInvalidSessionId** _SessionId_参数无效; 如果有关其他故障**xlHpcRetCallFailed** 。 
  
## <a name="see-also"></a>另请参阅

- [OpenSession](opensession.md)
- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

