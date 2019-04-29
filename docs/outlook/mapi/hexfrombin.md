---
title: HexFromBin
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HexFromBin
api_type:
- COM
ms.assetid: 12b95657-1926-4a24-be63-40305ea6f990
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a1bf02de914865e27c8c018aba8695c858888ae2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412574"
---
# <a name="hexfrombin"></a>HexFromBin

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将二进制数转换为十六进制数的字符串表示形式。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
void HexFromBin(
  LPBYTE pb,
  int cb,
  LPSTR sz
);
```

## <a name="parameters"></a>参数

 _pb_
  
> 实时指向要转换的二进制数据的指针。 
    
 _cb_
  
> 实时_pb_参数指向的二进制数据的大小 (以字节为单位)。 
    
 _sz_
  
> 排除指向以十六进制数字表示二进制数据的以 null 结尾的 ASCII 字符串的指针。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

**HexFromBin**函数获取指向二进制数据单位的指针, 该数据单位的大小由_cb_参数指示。 它在_sz_字符串中返回 (2 * _cb_) + 1 字节的内存, 这是十六进制数中的此二进制信息的表示形式。 例如, 如果字节值为十进制数 10, 则十六进制字符串将为 0A, 因此一个字节将转换为字符串中的两个字节。 
  

