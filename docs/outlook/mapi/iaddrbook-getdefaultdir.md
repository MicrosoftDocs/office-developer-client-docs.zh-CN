---
title: IAddrBookGetDefaultDir
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.GetDefaultDir
api_type:
- COM
ms.assetid: 7a9fdf3f-fd76-40fb-8217-967c6efba5f6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d9ad74d8ae02a49ee3c222394caedfd571f84b1c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436872"
---
# <a name="iaddrbookgetdefaultdir"></a>IAddrBook::GetDefaultDir

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回初始通讯簿容器的条目标识符。
  
```cpp
HRESULT GetDefaultDir(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a>参数

 _lpcbEntryID_
  
> [out]指向  _lppEntryID_ 参数指向的条目标识符中的字节计数的指针。 
    
 _lppEntryID_
  
> [out]指向指向默认容器的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回默认容器的条目标识符。
    
## <a name="remarks"></a>备注

客户端应用程序和服务提供商调用 **GetDefaultDir** 方法来检索默认通讯簿容器的条目标识符。 默认容器是用户在通讯簿中首次打开通讯簿时看到的内容。 如果尚未通过调用 [IAddrBook：：SetDefaultDir](iaddrbook-setdefaultdir.md) 方法设置默认容器，MAPI 将名称不是个人通讯簿的第一个容器分配为默认容器 (PAB) 。 如果找不到此类容器，PAB 将成为默认容器。 
  
若要设置默认目录，客户端或提供程序将调用 **SetDefaultDir** 方法。 客户端和提供程序不需要调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法;因为通讯簿更改未进行事务处理，所以更改会立即永久生效。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnOpenDefaultDir  <br/> |MFCMAPI 使用 **GetDefaultDir** 方法获取默认通讯簿容器的 ID。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

