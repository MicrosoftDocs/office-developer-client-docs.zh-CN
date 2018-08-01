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
ms.openlocfilehash: 3f13a4d278b85ffae33e8f44f3a15eb499fb11b3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775269"
---
# <a name="iaddrbooksetpab"></a>IAddrBook::SetPAB

  
  
**适用于**： Outlook 
  
指定为个人通讯簿 (PAB) 特定的容器。
  
```cpp
HRESULT SetPAB(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要指定为 PAB 的容器的项标识符的指针。 _LpEntryID_参数不能为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 作为 PAB 建立了指定的容器。
    
## <a name="remarks"></a>说明

客户端和服务提供商调用**SetPAB**方法将指定为 PAB 某个特定的容器。 PAB 是从其他容器以及新条目复制的项组成的容器。 
  
调用**SetPAB**建立容器作为 PAB，直到该容器进行不可用或新容器成为通过后续调用**SetPAB**PAB。 
  
客户端和提供程序不需要调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法进行永久 PAB 更改。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|AbContDlg.cpp  <br/> |CAbContDlg::OnSetPAB  <br/> |MFCMAPI 使用**SetPAB**方法使指定的容器 PAB。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::GetPAB](iaddrbook-getpab.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

