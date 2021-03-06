---
title: IAddrBookGetPAB
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.GetPAB
api_type:
- COM
ms.assetid: 9830e09c-700f-469b-a54d-4e4e0583aa84
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6c565c088fd4ef7d5df141bf770c560f79535998
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419896"
---
# <a name="iaddrbookgetpab"></a>IAddrBook::GetPAB

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回指定为 PAB 用户的个人通讯簿的容器 (标识符) 。
  
```cpp
HRESULT GetPAB(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a>参数

 _lpcbEntryID_
  
> [out]指向  _lppEntryID_ 参数指向的条目标识符中的字节计数的指针。 
    
 _lppEntryID_
  
> [out]指向指向 PAB 条目标识符的指针的指针。 如果尚未将容器指定为 PAB，  _则 lppEntryID_ 参数包含零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回 PAB 的条目标识符。
    
## <a name="remarks"></a>备注

客户端调用 **GetPAB** 方法来检索指定为 PAB 的容器的条目标识符。 如果在配置文件中尚未建立 PAB，MAPI 将选择作为允许修改的通讯簿层次结构中第一个容器的 PAB。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnOpenPAB  <br/> |MFCMAPI 使用 **GetPAB** 方法获取用户的个人通讯簿的 ID。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

