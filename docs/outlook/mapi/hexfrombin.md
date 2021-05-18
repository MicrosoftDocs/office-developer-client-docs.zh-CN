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
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
void HexFromBin(
  LPBYTE pb,
  int cb,
  LPSTR sz
);
```

## <a name="parameters"></a>参数

 _pb_
  
> [in]指向要转换的二进制数据的指针。 
    
 _cb_
  
> [in]pb 参数指向的二进制数据的大小（以  _字节_ 为单位）。 
    
 _sz_
  
> [out]指向以 null 结尾的 ASCII 字符串的指针，该字符串代表十六进制数字中的二进制数据。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

**HexFromBin** 函数采用指向二进制数据单位的指针，其大小由 _cb_ 参数指示。 它在  _sz_ 字符串中返回， (2*  _cb_) +1 字节的内存，以十六进制数表示此二进制信息。 例如，如果字节值为十进制 10，则十六进制字符串将为 0A，因此字符串中的一个字节转换为两个字节。 
  

