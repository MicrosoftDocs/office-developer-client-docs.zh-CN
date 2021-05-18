---
title: OpenSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cfd3513-800f-4602-b3e6-6430920718d6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3e4df0c5772f28ab4ab8d84eaddfe4409a88061b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421835"
---
# <a name="opensession"></a>OpenSession

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建可在其中执行用户定义函数的会话。
  
```cpp
int OpenSession(WCHAR *Params)
```

## <a name="parameters"></a>参数

_参数_
  
> 指向会话参数的以分号分隔的 UNICODE 字符串的指针。 Excel不使用此参数。
    
## <a name="return-value"></a>返回值

要用于对群集连接器的其他调用的会话 ID（如果已成功创建会话）;否则 **为 xlHpcRetCallFailed**。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

