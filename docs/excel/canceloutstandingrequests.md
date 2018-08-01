---
title: CancelOutstandingRequests
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0de9d4e2-eb3f-40e7-aa24-f430892eb9ec
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 65d4257037b18c8fa68cabe0c08091ec67343fa5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773634"
---
# <a name="canceloutstandingrequests"></a>CancelOutstandingRequests

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
通知的 Excel 计算已被取消，因此所有挂起的会话中的函数调用可能会取消以及群集连接器 （和 Excel 并不需要其结果的回调）。
  
```cpp
int CancelOutstandingRequests(int SessionId)
```

## <a name="parameters"></a>参数

_SessionID_
  
> 使用已取消计算会话的 ID。 此值匹配[OpenSession](opensession.md)返回的值。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess** _SessionId_参数是否有效;**xlHpcRetInvalidSessionId** _SessionId_参数无效; 如果有关其他故障**xlHpcRetCallFailed** 。 
  
## <a name="remarks"></a>说明

实施应以提高性能，作为此呼叫将被丢弃由 Excel 之后收到任何结果会话停止所有进程。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

