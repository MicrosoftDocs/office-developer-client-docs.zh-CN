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
ms.openlocfilehash: 68cca0b483aca91001f8ee71289f4b1673fb2888
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564652"
---
# <a name="iaddrbooksetdefaultdir"></a>IAddrBook::SetDefaultDir

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
建立默认通讯簿容器为指定的容器。
  
```cpp
HRESULT SetDefaultDir(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向默认通讯簿容器的项标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置默认通讯簿容器。
    
## <a name="remarks"></a>注解

客户端和服务提供商调用**SetDefaultDir**方法建立新的默认通讯簿容器。 默认容器是首次打开通讯簿时显示在通讯簿中的用户看到的容器。 **SetDefaultDir**将默认容器保存为配置文件中的条目。 容器将保持为默认值，直到在同一个会话或另一个会话中进行**SetDefaultDir**到另一个呼叫，或者删除容器。 
  
> [!NOTE]
> [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)属性对应于在通讯簿选项对话框的**自动选择**设置。 不再通讯簿对话框时该属性存在[IID_CAPONE_PROF](http://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx)配置文件一节，但将设置为**true**，默认为**SetDefaultDir**，指定的容器，但选择 Microsoft Outlook 会认为通讯簿适用于在其中显示对话框中的上下文。 请注意，这可能会导致不好的体验的第三方通讯簿提供程序。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|Abcontdlg.cpp  <br/> |CAbContDlg::OnSetDefaultDir  <br/> |MFCMAPI 使用**SetDefaultDir**方法将一个默认的指定在通讯簿容器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[IMAPISession::Logoff](imapisession-logoff.md)
  
[MAPILogonEx](mapilogonex.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

