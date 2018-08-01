---
title: ACCT_VARIANT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4664df83-cf81-36d4-189d-4a09be371638
description: 此数据类型变量包含的一个属性，它是 variant 数据类型的值。
ms.openlocfilehash: c85af4bd4fefffb4fadf671bb7cf5b7f072d5e95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774172"
---
# <a name="acctvariant"></a>ACCT_VARIANT

此数据类型变量包含的一个属性，它是 variant 数据类型的值。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct 
    { 
        DWORD dwType; 
        union  
            { 
            DWORD dw; 
            WCHAR *pwsz; 
            ACCT_BIN bin; 
            } Val; 
    } ACCT_VARIANT; 

```

## <a name="members"></a>Members

_dwType_
  
> Variant 类型：
    
    - PT_LONG
    
    - PT_UNICODE
    
    - PT_BINARY
    
_数据仓库_
  
> Variant 的 DWORD 值。
    
_pwsz_
  
> Variant 类型的值的字符串值。
    
_回收站_
  
> 二进制值的 variant。
    

