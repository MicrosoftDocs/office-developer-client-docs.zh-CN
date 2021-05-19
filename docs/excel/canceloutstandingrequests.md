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
  
通知群集连接器已取消 Excel 计算，因此该会话内的所有待定函数调用可能也被取消 (并且 Excel 不需要具有其结果) 的回调。
  
```cpp
int CancelOutstandingRequests(int SessionId)
```

## <a name="parameters"></a>参数

_SessionID_
  
> 已取消计算使用的会话的 ID。 此值与 [OpenSession 返回的值匹配](opensession.md)。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess（** 如果 _SessionId_ 参数有效）;**xlHpcRetInvalidSessionId** 如果 _SessionId_ 参数无效;**其他故障时为 xlHpcRetCallFailed。** 
  
## <a name="remarks"></a>备注

实现者应停止会话的所有进程，以提高性能，因为在此调用后收到的任何结果将被Excel。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

