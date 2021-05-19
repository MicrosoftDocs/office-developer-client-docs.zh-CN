---
title: 关闭包装的 PST 存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 0c9e5917-1b96-323d-bf8b-1d3aa1f677d0
description: 上次修改时间：2012 年 7 月 2 日
ms.openlocfilehash: fa918920213ee77c4d0c1d3ccc239ae7cffe81fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409942"
---
# <a name="shutting-down-a-wrapped-pst-store-provider"></a>关闭包装的 PST 存储提供程序

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在使用包装的个人文件夹文件 (PST) 提供程序后，必须正确关闭包装的 PST 存储提供程序。 有关使用包装的 PST 存储提供程序的信息，请参阅 [使用封装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)。
  
若要关闭包装的 PST 存储提供程序，必须调用 **[IMSProvider：：Shutdown](imsprovider-shutdown.md)** 函数。 此功能会有序关闭包装的 PST 存储提供程序。 
  
在本主题中，使用包装 PST 存储提供程序示例中的代码示例演示 **了 IMSProvider：：Shutdown** 函数。 该示例实现一个包装的 PST 提供程序，旨在与复制 API 结合使用。 有关下载和安装包装的示例 PST 存储提供程序详细信息，请参阅安装包装的 PST 存储 [提供程序示例](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 API 的信息，请参阅[关于复制 API。](about-the-replication-api.md)
  
## <a name="shut-down-routine"></a>关闭例程

MAPI 后台处理程序在释放包装的 PST 存储提供程序之前调用 **[IMSProvider：：Shutdown](imsprovider-shutdown.md)** 函数，以便封装的 PST 存储提供程序可以正确关闭。 函数将终止与包装的 PST 存储提供程序关联的所有会话对象。 
  
## <a name="cmsprovidershutdown-example"></a>CMSProvider：：ShutDown () 示例

```cpp
STDMETHODIMP CMSProvider::Shutdown(ULONG * pulFlags) 
{ 
    HRESULT hRes = S_OK; 
    Log(true,"CMSProvider::Shutdown\n"); 
    hRes =m_pPSTMS->Shutdown(pulFlags); 
    Log(true,"CMSProvider::Shutdown returned: 0x%08X\n", hRes); 
    return hRes ;  
}
```

## <a name="see-also"></a>另请参阅



[关于包装的 PST 存储提供程序示例](about-the-sample-wrapped-pst-store-provider.md)
  
[安装包装的 PST 存储提供程序示例](installing-the-sample-wrapped-pst-store-provider.md)
  
[初始化包装的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
  
[登录到包装的 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
  
[使用包装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)

