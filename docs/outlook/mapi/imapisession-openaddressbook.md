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
ms.openlocfilehash: 51bf5f8455d4cb790d0c955e96249b0f9deef1af
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329419"
---
# <a name="imapisessionopenaddressbook"></a>IMAPISession::OpenAddressBook

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开 MAPI 集成通讯簿，返回 [IAddrBook](iaddrbookimapiprop.md) 指针以进一步访问。 
  
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
  
> [in]常见地址对话框和其他相关显示器的父窗口的句柄。
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问通讯簿的接口。 传递 **null** 将返回一个指向通讯簿的标准接口 [IAddrBook ： IMAPIProp 的指针](iaddrbookimapiprop.md)。 
    
 _ulFlags_
  
> [in]控制通讯簿打开的标志的位掩码。 可以设置以下标志：
    
AB_NO_DIALOG 
  
> 禁止显示对话框。 如果未AB_NO_DIALOG，则参与集成通讯簿的通讯簿提供程序可以提示用户输入任何必要信息。 
    
 _lppAdrBook_
  
> [out]指向指向通讯簿的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通讯簿已成功打开。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但无法打开一个或多个通讯簿提供程序的容器。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPISession：：OpenAddressBook** 方法打开 MAPI 集成通讯簿，该通讯簿是配置文件中所有通讯簿提供程序的顶级容器的集合。 _lppAdrBook_ 参数中返回的指针提供对通讯簿内容的进一步访问。 这允许呼叫者执行任务，如打开单个容器、查找邮件用户和显示公用地址对话框。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **OpenAddressBook** 返回MAPI_W_ERRORS_RETURNED如果无法在配置文件中加载一个或多个通讯簿提供程序，则返回该设置。 此值是警告，而不是错误值;处理它，就像处理S_OK。 **OpenAddressBook** 始终在  _lppAdrBook_ 参数中返回一个有效指针，而不管有多少通讯簿提供程序未能加载。 因此，在注销之前，必须始终在一些时候调用通讯簿的 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法。 
  
当 **OpenAddressBook** 返回MAPI_W_ERRORS_RETURNED时，调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 以获取包含有关失败提供程序信息的 [MAPIERROR](mapierror.md) 结构。 返回一 **个 MAPIERROR** 结构，其中包含所有提供程序所提供的信息。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIObjects.cpp  <br/> |CMapiObjects：：GetAddrBook  <br/> |MFCMAPI 使用 **IMAPISession：：OpenAddressBook** 方法获取集成通讯簿。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[IMAPISession::GetLastError](imapisession-getlasterror.md)
  
[MAPIERROR](mapierror.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

