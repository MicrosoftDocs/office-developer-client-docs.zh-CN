---
title: CloseSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2c2371c8-b0e0-4992-b7ac-3949eadf1ebe
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9186fb14c33d507b8c9ae709a67f1b43e6206d5b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422535"
---
# <a name="closesession"></a>CloseSession

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
结束与群集的会话。
  
```cpp
int CloseSession(int SessionId)
```

## <a name="parameters"></a>参数

_SessionId_
  
> 要关闭的会话的 ID。 此值必须与 [OpenSession 返回的值匹配](opensession.md)。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess（** 如果会话已关闭）;**xlHpcRetInvalidSessionId** 如果 _SessionId_ 参数无效;**其他故障时为 xlHpcRetCallFailed。** 
  
## <a name="see-also"></a>另请参阅

- [OpenSession](opensession.md)
- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

