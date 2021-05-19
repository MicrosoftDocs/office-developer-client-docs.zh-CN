---
title: IAddrBookSetDefaultDir
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.SetDefaultDir
api_type:
- COM
ms.assetid: d5d60150-15e4-41ff-bfb0-0c67e2abcacc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ab01f189734ac30b4c027f4e5596c88031b5f99
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341697"
---
# <a name="iaddrbooksetdefaultdir"></a>IAddrBook::SetDefaultDir

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将指定的容器建立为默认通讯簿容器。
  
```cpp
HRESULT SetDefaultDir(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向默认通讯簿容器的条目标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置默认通讯簿容器。
    
## <a name="remarks"></a>备注

客户端和服务提供商调用 **SetDefaultDir** 方法来建立一个新的默认通讯簿容器。 默认容器是用户在首次打开通讯簿时在通讯簿中显示的容器。 **SetDefaultDir** 将默认容器保存为配置文件中的条目。 容器保持为默认值，直到在同一会话中或其他会话中对 **SetDefaultDir** 进行另一次调用，或者容器被删除。 
  
> [!NOTE]
> The [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) property corresponds to the **Choose automatically setting** in the Address Book Options dialog. 当此属性存在于 [IID_CAPONE_PROF](https://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx)配置文件部分，并设置为 **true** 时，通讯簿对话框不再默认为 **SetDefaultDir** 指定的容器，而是选择 Microsoft Outlook 认为适合显示对话框的上下文的通讯簿。 请注意，这可能会导致第三方通讯簿提供商体验不佳。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|Abcontdlg.cpp  <br/> |CAbContDlg：：OnSetDefaultDir  <br/> |MFCMAPI 使用 **SetDefaultDir** 方法将指定的通讯簿容器设置为默认容器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[IMAPISession::Logoff](imapisession-logoff.md)
  
[MAPILogonEx](mapilogonex.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

