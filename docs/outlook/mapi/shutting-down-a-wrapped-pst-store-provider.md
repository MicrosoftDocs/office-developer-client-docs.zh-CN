---
title: 关闭打包的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 0c9e5917-1b96-323d-bf8b-1d3aa1f677d0
description: '上次修改时间: 2012 年7月2日'
ms.openlocfilehash: fa918920213ee77c4d0c1d3ccc239ae7cffe81fc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282780"
---
# <a name="shutting-down-a-wrapped-pst-store-provider"></a>关闭打包的 PST 存储区提供程序

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用包装的个人文件夹文件 (PST) 存储提供程序完成后, 必须正确关闭包装的 PST 存储提供程序。 有关使用包装的 pst 存储区提供程序的详细信息, 请参阅[使用打包的 pst 存储提供程序](using-a-wrapped-pst-store-provider.md)。
  
若要关闭包装的 PST 存储区提供程序, 必须调用**[IMSProvider:: Shutdown](imsprovider-shutdown.md)** 函数。 此函数以有序的方式关闭包装的 PST 存储区提供程序。 
  
在本主题中, 使用示例包装的 PST 存储提供程序中的代码示例演示了**IMSProvider:: Shutdown**函数。 此示例实现了一个用于与复制 API 结合使用的打包的 PST 提供程序。 有关下载和安装示例包装的 pst 存储区提供程序的详细信息, 请参阅[安装示例包装的 pst 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 api 的详细信息, 请参阅[关于复制 api](about-the-replication-api.md)。
  
## <a name="shut-down-routine"></a>关闭例程

MAPI 后台处理程序在释放包装的 pst 存储区提供程序之前调用**[IMSProvider:: Shutdown](imsprovider-shutdown.md)** 函数, 以便包装的 pst 存储区提供程序可以正确地关闭。 该函数终止与打包的 PST 存储区提供程序关联的所有会话对象。 
  
## <a name="cmsprovidershutdown-example"></a>CMSProvider:: ShutDown () 示例

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



[关于示例包装的 PST 存储区提供程序](about-the-sample-wrapped-pst-store-provider.md)
  
[安装示例包装的 PST 存储区提供程序](installing-the-sample-wrapped-pst-store-provider.md)
  
[初始化打包的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)
  
[登录到打包的 PST 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
  
[使用包装的 PST 存储区提供程序](using-a-wrapped-pst-store-provider.md)

