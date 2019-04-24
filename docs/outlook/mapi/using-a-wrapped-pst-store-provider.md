---
title: 使用包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 98f08432-e86c-cba6-45fd-5a6c94d50aaf
description: 上次修改时间:03 月3日, 2012
ms.openlocfilehash: b7c651044ab7f4cad7032db69e157c9a3589bde9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329685"
---
# <a name="using-a-wrapped-pst-store-provider"></a>使用包装的 PST 存储区提供程序

**适用于**：Outlook 2013 | Outlook 2016 
  
在可以使用包装的个人文件夹文件 (PST) 存储提供程序之前, 您必须初始化和配置打包的 PST 存储提供程序。 在配置包装的 PST 存储区提供程序后, 必须实现功能, 以便 mapi 和 mapi 后台处理程序可以登录到邮件存储提供程序。 有关初始化和登录到包装的 pst 存储区提供程序的详细信息, 请参阅[初始化包装的 pst 存储提供程序](initializing-a-wrapped-pst-store-provider.md), 并[登录到包装的 pst 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)。
  
**[IMAPISupport:: IUnknown](imapisupportiunknown.md)** 接口提供通常由邮件存储提供程序执行的任务的实现。 若要使示例包装的 PST 存储区提供程序正常工作, 必须包装此接口。 **[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)** 函数需要特殊实现。 所有其他函数都可以将其参数传递给基础包装对象。 
  
在本主题中, 使用示例包装的 PST 存储提供程序中的代码示例演示了**IMAPISupport:: OpenProfileSection**函数。 此示例实现了一个用于与复制 API 结合使用的打包的 PST 提供程序。 有关下载和安装示例包装的 pst 存储区提供程序的详细信息, 请参阅[安装示例包装的 pst 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 api 的详细信息, 请参阅[关于复制 api](about-the-replication-api.md)。
  
使用包装的 pst 存储区提供程序完成后, 必须正确关闭包装的 pst 存储区提供程序。 有关详细信息, 请参阅[关闭包装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)。
  
## <a name="open-profile-section-routine"></a>打开配置文件部分例程

**[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)** 函数打开当前配置文件的节。 该函数需要在包装的 PST 存储区提供程序实现中进行特殊处理。 `pgNSTGlobalProfileSectionGuid`请求时, 该函数将返回缓存的配置文件部分。 
  
### <a name="csupportopenprofilesection-example"></a>CSupport:: OpenProfileSection () 示例

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

- [关于示例包装的 PST 存储区提供程序](about-the-sample-wrapped-pst-store-provider.md)
- [安装示例包装的 PST 存储区提供程序](installing-the-sample-wrapped-pst-store-provider.md)
- [初始化打包的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)
- [登录到打包的 PST 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
- [关闭打包的 PST 存储区提供程序](shutting-down-a-wrapped-pst-store-provider.md)

