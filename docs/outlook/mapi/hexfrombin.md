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
ms.openlocfilehash: 8f68de5e18d84c728241c188b932f99456f5be8c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584833"
---
# <a name="hexfrombin"></a>HexFromBin

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将二进制数转换为十六进制数的字符串表示形式。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]大小 （以字节为单位， _pb_参数指向的二进制数据）。 
    
 _sz_
  
> [输出]以 null 结尾的 ASCII 字符串表示的十六进制数字中的二进制数据的指针。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

**HexFromBin**函数对其大小由_cb_参数的二进制数据的单位采用一个指针。 它在返回_sz_字符串中 (2 * _cb_) + 1 字节的内存，用十六进制数字此二进制信息的表示形式。 如果字节值为小数 10，例如的十六进制字符串将 0A，这样一个字节转换为字符串中的两个字节。 
  

