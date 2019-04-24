---
title: IAddrBookSetPAB
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.SetPAB
api_type:
- COM
ms.assetid: 75daf9d4-6975-435f-91e5-1b41e0047ab7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 29677ce74f405e8ca03f1639f3d98288532e9653
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287012"
---
# <a name="iaddrbooksetpab"></a>IAddrBook::SetPAB

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定特定的容器作为个人通讯簿 (PAB)。
  
```cpp
HRESULT SetPAB(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向要指定为 PAB 的容器的条目标识符的指针。 _lpEntryID_参数不能为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 指定的容器已被建立为 PAB。
    
## <a name="remarks"></a>注解

客户端和服务提供程序调用**SetPAB**方法, 以将特定容器指定为 PAB。 PAB 是一个容器, 它由从其他容器复制的条目以及新条目组成。 
  
对**SetPAB**的调用在将容器用作 PAB 之前将其建立, 直到将容器变为不可用, 或者新的容器通过对**SetPAB**的后续调用成为 pab。 
  
客户端和提供程序无需调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法来使 PAB 更改永久。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|AbContDlg  <br/> |CAbContDlg:: OnSetPAB  <br/> |MFCMAPI 使用**SetPAB**方法使指定容器成为 PAB。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::GetPAB](iaddrbook-getpab.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

