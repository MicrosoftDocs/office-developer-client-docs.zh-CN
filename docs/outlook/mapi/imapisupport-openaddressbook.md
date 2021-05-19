---
title: IMAPISupportOpenAddressBook
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.OpenAddressBook
api_type:
- COM
ms.assetid: d8da8be1-3efe-410a-bcce-49e522602d80
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 47a62b331ff9f1c96576d42797ebb23ed61cd362
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416879"
---
# <a name="imapisupportopenaddressbook"></a>IMAPISupport::OpenAddressBook

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对通讯簿的访问。
  
```cpp
HRESULT OpenAddressBook(
LPCIID lpInterface,
ULONG ulFlags,
LPADRBOOK FAR * lppAdrBook
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问通讯簿的接口。 有效值为 NULL，指示标准通讯簿接口 [IAddrBook](iaddrbookimapiprop.md)和 IID_IAddrBook。
    
 _ulFlags_
  
> 保留;必须为零。
    
 _lppAdrBook_
  
> [out]指向指向通讯簿的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 提供了对通讯簿的访问。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但无法加载一个或多个通讯簿提供程序。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPISupport：：OpenAddressBook** 方法针对所有服务提供商支持对象实现。 服务提供商（通常紧密耦合的邮件存储和传输提供程序）调用 **OpenAddressBook** 以访问通讯簿。 返回 **的 IAddrBook** 指针可用于各种通讯簿任务，包括打开通讯簿容器、查找邮件用户和显示地址对话框。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **如果 OpenAddressBook** 无法MAPI_W_ERRORS_RETURNED当前配置文件中的一个或多个通讯簿提供程序，则 OpenAddressBook 可以返回该地址。 此值是一条警告，您应该将调用视为成功。 即使所有通讯簿提供程序都未能加载 **，OpenAddressBook** 仍然成功，在 _lppAdrBook_ 参数中返回 MAPI_W_ERRORS_RETURNED 和 **IAddrBook** 指针。 由于 **OpenAddressBook** 始终返回有效的 **IAddrBook** 指针，因此在使用完它后必须释放它。 
  
如果加载一个或多个通讯簿提供程序失败，请调用 [IMAPISupport：：GetLastError](imapisupport-getlasterror.md) 以获取包含有关未加载的提供程序的信息的 [MAPIERROR](mapierror.md) 结构。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

