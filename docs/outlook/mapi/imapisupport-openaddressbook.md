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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 26550691ef959fa7cefa83827dd1391538bd2d38
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588172"
---
# <a name="imapisupportopenaddressbook"></a>IMAPISupport::OpenAddressBook

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供对通讯簿访问。
  
```cpp
HRESULT OpenAddressBook(
LPCIID lpInterface,
ULONG ulFlags,
LPADRBOOK FAR * lppAdrBook
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问通讯簿的接口的指针。 有效值为 NULL，表明标准地址簿接口[IAddrBook](iaddrbookimapiprop.md)和 IID_IAddrBook。
    
 _ulFlags_
  
> 保留;必须为零。
    
 _lppAdrBook_
  
> [输出]指向与通讯簿的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 提供对通讯簿的访问。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但无法加载一个或多个地址簿提供程序。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPISupport::OpenAddressBook**方法将执行所有服务提供商支持对象。 服务提供商，通常紧密耦合的消息存储和传输提供程序，调用**OpenAddressBook**才能访问通讯簿。 返回的**IAddrBook**指针可用于各种地址簿任务，包括打开通讯簿容器，查找邮件用户和显示地址对话框。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **OpenAddressBook**可以返回 MAPI_W_ERRORS_RETURNED，如果它无法加载一个或多个当前配置文件中的地址簿提供程序。 此值是一条警告，您应视为呼叫成功。 即使所有通讯簿提供程序无法加载， **OpenAddressBook**仍成功， _lppAdrBook_参数中返回 MAPI_W_ERRORS_RETURNED 和**IAddrBook**指针。 由于**OpenAddressBook**始终返回有效的**IAddrBook**指针，您必须释放其完后使用它。 
  
如果一个或多个地址簿提供程序无法加载，调用[IMAPISupport::GetLastError](imapisupport-getlasterror.md)获取[MAPIERROR](mapierror.md)结构，其中包含系统未加载提供程序的信息。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

