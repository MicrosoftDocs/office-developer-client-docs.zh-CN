---
title: 使用包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 98f08432-e86c-cba6-45fd-5a6c94d50aaf
description: 上次修改时间：2012 年 7 月 3 日
ms.openlocfilehash: b7c651044ab7f4cad7032db69e157c9a3589bde9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420820"
---
# <a name="using-a-wrapped-pst-store-provider"></a>使用包装的 PST 存储区提供程序

**适用于**：Outlook 2013 | Outlook 2016 
  
在 PST 存储提供程序中可以使用包装的个人 (文件) ，必须初始化和配置包装的 PST 存储提供程序。 配置包装的 PST 存储提供程序后，必须实现函数，以便 MAPI 和 MAPI 后台处理程序可以登录到邮件存储提供程序。 有关初始化封装 PST 存储提供程序并登录到包装 [的 PST](initializing-a-wrapped-pst-store-provider.md) 存储提供程序的信息，请参阅初始化封装的 PST 存储提供程序和登录到封装的 PST [存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)。
  
**[IMAPISupport：：IUnknown](imapisupportiunknown.md)** 接口为邮件存储提供程序通常执行的任务提供实现。 必须包装此接口，示例封装 PST 存储提供程序工作。 **[IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)** 函数需要特殊实现。 所有其他函数都可以将参数传递给基础封装对象。 
  
在本主题中，使用示例封装 PST 存储提供程序中的代码示例演示 **了 IMAPISupport：：OpenProfileSection** 函数。 该示例实现一个包装的 PST 提供程序，旨在与复制 API 结合使用。 有关下载和安装包装的示例 PST 存储提供程序详细信息，请参阅安装包装的 PST 存储 [提供程序示例](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 API 的信息，请参阅[关于复制 API。](about-the-replication-api.md)
  
使用包装的 PST 存储提供程序完成后，必须正确关闭包装的 PST 存储提供程序。 有关详细信息，请参阅 [关闭封装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)。
  
## <a name="open-profile-section-routine"></a>Open Profile Section 例程

**[IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)** 函数打开当前配置文件的一部分。 该函数需要在封装的 PST 存储提供程序实现中进行特殊处理。 请求  `pgNSTGlobalProfileSectionGuid` 时，函数将返回缓存的配置文件节。 
  
### <a name="csupportopenprofilesection-example"></a>CSupport：：OpenProfileSection () 示例

```cpp
STDMETHODIMP CSupport::OpenProfileSection( 
    LPMAPIUID lpUid,     
    ULONG ulFlags, 
    LPPROFSECT * lppProfileObj) 
{ 
    Log(true,"CSupport::OpenProfileSection\n"); 
    if (lpUid &&  
        IsEqualMAPIUID(lpUid, (void *)&pbNSTGlobalProfileSectionGuid) &&  
        m_lpProfSect) 
    {      
        // Allow the opening of the Global Section 
        if (m_lpProfSect) 
        { 
            *lppProfileObj = m_lpProfSect; 
            (*lppProfileObj)->AddRef(); 
            return S_OK; 
        } 
    } 
    return m_pMAPISup->OpenProfileSection(lpUid, ulFlags, lppProfileObj); 
}
```

## <a name="see-also"></a>另请参阅

- [关于包装的 PST 存储提供程序示例](about-the-sample-wrapped-pst-store-provider.md)
- [安装包装的 PST 存储提供程序示例](installing-the-sample-wrapped-pst-store-provider.md)
- [初始化包装的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
- [登录到包装的 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
- [关闭包装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)

