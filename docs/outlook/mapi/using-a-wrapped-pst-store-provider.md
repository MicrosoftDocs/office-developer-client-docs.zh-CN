---
title: 使用换行的 PST 存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 98f08432-e86c-cba6-45fd-5a6c94d50aaf
description: 上次修改时间： 2012 年 7 月 3 日
ms.openlocfilehash: 4a2ccbbcdd3459af6b69156d80b37695251ba8d6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779063"
---
# <a name="using-a-wrapped-pst-store-provider"></a>使用换行的 PST 存储提供程序

**适用于**： Outlook 
  
您可以使用换行的个人文件夹文件 (PST) 存储提供程序之前，您必须初始化并配置的换行的 PST 存储提供程序。 配置的换行的 PST 存储提供程序后，您必须实现函数，以便 MAPI 和 MAPI 后台处理程序可以登录到的消息存储提供程序。 有关初始化和登录到换行的 PST 存储提供程序的详细信息，请参阅[初始化自动换行 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)和[日志记录上为一个自动换行 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)。
  
**[IMAPISupport::IUnknown](imapisupportiunknown.md)** 接口提供了实现任务的常执行的消息存储提供程序。 必须为示例自动换行 PST 存储提供程序以包装此接口。 **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** 函数需要特殊的实现。 所有其他函数可以将其参数传递给基础被环绕对象。 
  
本主题中，使用从示例自动换行 PST 存储提供程序的代码示例演示了**IMAPISupport::OpenProfileSection**函数。 本示例实现的换行的太平洋标准时间提供程序旨在与复制 API 结合使用。 有关下载并安装示例自动换行 PST 存储提供程序的详细信息，请参阅[安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 API 的详细信息，请参阅[有关复制 API](about-the-replication-api.md)。
  
当您完成使用换行的 PST 存储提供程序时，您必须正确关闭换行 PST 存储提供程序。 有关详细信息，请参阅[关机的情况下自动换行 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)。
  
## <a name="open-profile-section-routine"></a>打开配置文件部分例程

**[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** 函数将打开当前配置文件的一部分。 该函数需要在换行 PST 存储提供程序实现的专门处理措施。 当`pgNSTGlobalProfileSectionGuid`请求时，此函数返回缓存配置文件一节。 
  
### <a name="csupportopenprofilesection-example"></a>CSupport::OpenProfileSection() 示例

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
- [初始化包装的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)
- [登录包装的 PST 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
- [关闭包装的 PST 存储区提供程序](shutting-down-a-wrapped-pst-store-provider.md)

