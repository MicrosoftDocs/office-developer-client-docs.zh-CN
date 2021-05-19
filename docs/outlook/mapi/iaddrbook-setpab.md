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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424614"
---
# <a name="iaddrbooksetpab"></a>IAddrBook::SetPAB

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将特定容器指定为 PAB (个人通讯簿) 。
  
```cpp
HRESULT SetPAB(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要指定为 PAB 的容器的条目标识符的指针。 _lpEntryID_ 参数不能为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 指定的容器已建立为 PAB。
    
## <a name="remarks"></a>备注

客户端和服务提供商调用 **SetPAB** 方法以将特定容器指定为 PAB。 PAB 是包含从其他容器复制的条目和新条目的容器。 
  
调用 **SetPAB 会** 建立一个容器作为 PAB，直到该容器不可用，或者通过后续调用 **SetPAB，** 新容器成为 PAB。 
  
客户端和提供程序不需要调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来永久更改 PAB。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|AbContDlg.cpp  <br/> |CAbContDlg：：OnSetPAB  <br/> |MFCMAPI 使用 **SetPAB** 方法将指定的容器设置为 PAB。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::GetPAB](iaddrbook-getpab.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

