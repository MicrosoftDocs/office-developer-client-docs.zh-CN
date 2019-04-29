---
title: CancelOutstandingRequests
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0de9d4e2-eb3f-40e7-aa24-f430892eb9ec
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 882458ab096cbced8e0635dab65fe0b1d680388f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414716"
---
# <a name="canceloutstandingrequests"></a>CancelOutstandingRequests

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
通知群集连接器已取消某个 Excel 计算, 因此该会话中的所有挂起的函数调用也可能会被取消 (并且 Excel 不希望回调与其结果一起)。
  
```cpp
int CancelOutstandingRequests(int SessionId)
```

## <a name="parameters"></a>参数

_SessionID_
  
> 已取消的计算所使用的会话的 ID。 此值与[OpenSession](opensession.md)返回的值相匹配。
    
## <a name="return-value"></a>返回值

如果_SessionId_参数有效, 则为**xlHpcRetSuccess** , 否则为 false。**xlHpcRetInvalidSessionId**如果_SessionId_参数无效, 则为有关其他故障的**xlHpcRetCallFailed** 。 
  
## <a name="remarks"></a>说明

实施者应停止会话的所有进程以提高性能, 因为 Excel 将放弃在此调用之后收到的任何结果。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

