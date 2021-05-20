---
title: UFromSz
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UFromSz
api_type:
- COM
ms.assetid: 4a67faa2-8c2e-49a7-8c92-690a0a65c8f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9947558975098316a547abfaefcdf5e7d4cd2f41
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439007"
---
# <a name="ufromsz"></a>UFromSz

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将小数位数的以 null 结尾的字符串转换为无符号整数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
UINT UFromSz(
  LPCSTR lpsz
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向要转换的以 null 结尾的字符串的指针。 _lpsz_ 参数不能超过 65536 个字符。 
    
## <a name="return-value"></a>返回值

 **UFromSz** 返回无符号整数。 如果字符串不以至少一个十进制数字开头，则返回零。 
  
## <a name="remarks"></a>备注

**UFromSz** 函数在到达字符串中不是十进制数字的第一个字符时停止转换。 例如，在给定字符串"55"后 **，UFromSz** 将返回整数值 55。 如果给定字符串"5a5b"，函数将返回整数值 5。 在给定字符串"a5b5"后 **，UFromSz 将** 返回零。 
  
 **UFromSz** 对音调差异敏感。 支持 Unicode 和 DBCS 格式的字符串。 _lpsz_ 的长度限制为字符，不一定是字节。 
  

