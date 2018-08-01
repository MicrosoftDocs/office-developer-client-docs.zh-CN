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
ms.openlocfilehash: 7309f65965fe3c88f927eeba0bbcccff97c479af
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775252"
---
# <a name="iaddrbookgetdefaultdir"></a>IAddrBook::GetDefaultDir

  
  
**适用于**： Outlook 
  
返回初始的通讯簿容器的项标识符。
  
```cpp
HRESULT GetDefaultDir(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a>参数

 _lpcbEntryID_
  
> [输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。 
    
 _lppEntryID_
  
> [输出]指向默认容器的项标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的默认容器的项标识符。
    
## <a name="remarks"></a>说明

客户端应用程序和服务提供商调用**GetDefaultDir**方法检索默认通讯簿容器的项标识符。 默认容器是用户看到的第一次打开通讯簿时显示在通讯簿中。 如果尚未通过调用[IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md)方法来设置默认容器，MAPI 分配名称的第一个容器不是个人通讯簿 (PAB) 作为默认容器。 如果找不到此类容器，PAB 将成为默认容器。 
  
设置默认目录，客户端或提供程序，请调用**SetDefaultDir**方法。 客户端和提供程序不需要调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法;因为到通讯簿的更改不事务处理，立即进行永久更改。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnOpenDefaultDir  <br/> |MFCMAPI 使用**GetDefaultDir**方法获取默认通讯簿容器的 ID。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

