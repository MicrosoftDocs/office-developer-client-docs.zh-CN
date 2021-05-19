---
title: ACCT_VARIANT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4664df83-cf81-36d4-189d-4a09be371638
description: 此变量的数据类型保留属性的值，该属性值是变量数据类型。
ms.openlocfilehash: 124cfaef40e63d60e2e9c6681884bfb57a043dde
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424397"
---
# <a name="acct_variant"></a>ACCT_VARIANT

此变量的数据类型保留属性的值，该属性值是变量数据类型。
  
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
  
> 变量类型：
    
    - PT_LONG
    
    - PT_UNICODE
    
    - PT_BINARY
    
_dw_
  
> 变量型的 DWORD 值。
    
_pwsz_
  
> variant 的字符串值。
    
_bin_
  
> 变量的二进制值。
    

