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
  
将指定的容器建立为默认的通讯簿容器。
  
```cpp
HRESULT SetDefaultDir(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向默认通讯簿容器的条目标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置默认的通讯簿容器。
    
## <a name="remarks"></a>注解

客户端和服务提供程序调用**SetDefaultDir**方法以建立新的默认通讯簿容器。 默认容器是首次打开通讯簿时用户看到的在通讯簿中显示的容器。 **SetDefaultDir**将默认容器保存为配置文件中的条目。 容器将一直保留为默认值, 直到在同一会话中或在另一个会话中对**SetDefaultDir**进行了另一个调用, 或者删除了容器。 
  
> [!NOTE]
> [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)属性对应于 "通讯簿选项" 对话框中的 "**自动选择**" 设置。 当[IID_CAPONE_PROF](https://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx)配置文件部分中存在此属性并将其设置为**true**时, 通讯簿对话框不再默认为**SetDefaultDir**指定的容器, 而是选择 Microsoft Outlook 认为的通讯簿适合在其中显示对话框的上下文。 请注意, 这可能会导致第三方通讯簿提供程序的体验不佳。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|Abcontdlg  <br/> |CAbContDlg:: OnSetDefaultDir  <br/> |MFCMAPI 使用**SetDefaultDir**方法将指定的通讯簿容器设为默认容器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[IMAPISession::Logoff](imapisession-logoff.md)
  
[MAPILogonEx](mapilogonex.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

