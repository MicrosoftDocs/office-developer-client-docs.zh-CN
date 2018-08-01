---
title: OpenSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cfd3513-800f-4602-b3e6-6430920718d6
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 782843f11643e203488b313181d224443a1d36c5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773807"
---
# <a name="opensession"></a>OpenSession

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
创建可在其中执行用户定义函数的会话。
  
```cpp
int OpenSession(WCHAR *Params)
```

## <a name="parameters"></a>参数

_参数_
  
> 一个指向以分号分隔的会话的参数的 UNICODE 字符串。 Excel 不使用此参数。
    
## <a name="return-value"></a>返回值

要会话已成功创建; 如果在到群集连接器，而其他呼叫中使用的会话 ID否则为**xlHpcRetCallFailed**。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

