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
ms.openlocfilehash: 3d67d71effde87711e3be9aca1b979627acda37d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775258"
---
# <a name="iaddrbookgetpab"></a>IAddrBook::GetPAB

  
  
**适用于**： Outlook 
  
返回的项标识符指定为个人通讯簿 (PAB) 的容器。
  
```cpp
HRESULT GetPAB(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a>参数

 _lpcbEntryID_
  
> [输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。 
    
 _lppEntryID_
  
> [输出]指向 PAB 的项标识符的指针的指针。 如果没有容器被指定为 PAB， _lppEntryID_参数包含零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回 PAB 的项标识符。
    
## <a name="remarks"></a>说明

客户端调用**GetPAB**方法检索的项标识符指定为 PAB 的容器。 如果尚未配置文件中建立 PAB，MAPI 选择作为 PAB 第一个容器允许进行修改的通讯簿层次结构中。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnOpenPAB  <br/> |MFCMAPI 使用**GetPAB**方法来获取用户的个人通讯簿的 ID。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

