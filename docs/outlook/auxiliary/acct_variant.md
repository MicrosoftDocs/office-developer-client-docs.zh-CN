---
title: ACCT_VARIANT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4664df83-cf81-36d4-189d-4a09be371638
description: 此数据类型的变量包含一个 variant 数据类型的属性值。
ms.openlocfilehash: 124cfaef40e63d60e2e9c6681884bfb57a043dde
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424397"
---
# <a name="acctvariant"></a>ACCT_VARIANT

此数据类型的变量包含一个 variant 数据类型的属性值。
  
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

## <a name="members"></a>成员

_dwType_
  
> 变量类型:
    
    - PT_LONG
    
    - PT_UNICODE
    
    - PT_BINARY
    
_仓库_
  
> variant 的 DWORD 值。
    
_pwsz_
  
> variant 的字符串值。
    
_区间_
  
> 变量的二进制值。
    

