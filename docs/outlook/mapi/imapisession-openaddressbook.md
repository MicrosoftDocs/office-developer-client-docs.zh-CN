---
title: IMAPISessionOpenAddressBook
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenAddressBook
api_type:
- COM
ms.assetid: 2b6a4c6a-bb71-4ea1-a3b6-90a2722880fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0902aeb71ed66381772a808d21d77edb7e0e2da8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589873"
---
# <a name="imapisessionopenaddressbook"></a>IMAPISession::OpenAddressBook

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开 MAPI 集成的通讯簿中，返回进一步访问[IAddrBook](iaddrbookimapiprop.md)指针。 
  
```cpp
HRESULT OpenAddressBook(
  ULONG_PTR ulUIParam,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPADRBOOK FAR * lppAdrBook
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]通用的地址对话框和其他的父窗口的句柄相关显示。
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问通讯簿的接口的指针。 传递**null**将指针返回到通讯簿的标准接口[IAddrBook: IMAPIProp](iaddrbookimapiprop.md)。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制打开的通讯簿。 可以设置以下标记：
    
AB_NO_DIALOG 
  
> 禁止显示的对话框。 如果未设置 AB_NO_DIALOG 标志，参与集成的通讯簿通讯簿提供程序可以提示用户输入任何必要的信息。 
    
 _lppAdrBook_
  
> [输出]指向与通讯簿的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开通讯簿。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但无法打开一个或多个地址簿提供程序的容器。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPISession::OpenAddressBook**方法打开 MAPI 集成的通讯簿中，所有配置文件中的地址簿提供程序的顶级容器的集合。 _LppAdrBook_参数中返回的指针进一步提供访问通讯簿的内容。 这样呼叫者进行执行任务，如打开各个容器、 查找邮件用户和显示常见地址对话框。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **OpenAddressBook**返回 MAPI_W_ERRORS_RETURNED，如果它无法加载一个或多个配置文件中的地址簿提供程序。 此值是一条警告，不是一个错误值;就像 S_OK 处理它。 **OpenAddressBook**始终_lppAdrBook_参数，无论多少的通讯簿提供程序无法加载中返回一个有效的指针。 因此，您必须始终在通讯簿[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法某个时间点之前调用注销。 
  
当**OpenAddressBook**返回 MAPI_W_ERRORS_RETURNED 时，调用[IMAPISession::GetLastError](imapisession-getlasterror.md)获取[MAPIERROR](mapierror.md)结构，其中包含有关失败提供商信息。 包含由所有提供商提供的信息，则返回的单个**MAPIERROR**结构。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIObjects.cpp  <br/> |CMapiObjects::GetAddrBook  <br/> |MFCMAPI 使用**IMAPISession::OpenAddressBook**方法获取集成的通讯簿。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[IMAPISession::GetLastError](imapisession-getlasterror.md)
  
[MAPIERROR](mapierror.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

