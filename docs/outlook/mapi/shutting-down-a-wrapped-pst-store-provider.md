---
title: 关闭包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 0c9e5917-1b96-323d-bf8b-1d3aa1f677d0
description: 上次修改时间： 2012 年 7 月 2 日
ms.openlocfilehash: 5c8ad7443b0c1aa05f48284e4b09859ab53dd2c3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778779"
---
# <a name="shutting-down-a-wrapped-pst-store-provider"></a>关闭包装的 PST 存储区提供程序

 
  
**适用于**： Outlook 
  
使用换行的个人文件夹文件 (PST) 存储提供程序之后，您必须正确关闭的换行的 PST 存储提供程序。 有关使用换行的 PST 存储提供程序的详细信息，请参阅[使用自动换行 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)。
  
若要关闭换行的 PST 存储提供程序，必须调用**[IMSProvider::Shutdown](imsprovider-shutdown.md)** 函数。 此功能将关闭中有序的方式换行 PST 存储提供程序。 
  
本主题中，使用从示例自动换行 PST 存储提供程序的代码示例演示了**IMSProvider::Shutdown**函数。 本示例实现的换行的太平洋标准时间提供程序旨在与复制 API 结合使用。 有关下载并安装示例自动换行 PST 存储提供程序的详细信息，请参阅[安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 API 的详细信息，请参阅[有关复制 API](about-the-replication-api.md)。
  
## <a name="shut-down-routine"></a>关闭例程

MAPI 后台处理程序调用**[IMSProvider::Shutdown](imsprovider-shutdown.md)** 函数，其释放的换行的 PST 存储提供程序，以便换行的 PST 存储提供程序可以正确地关闭之前。 函数终止的换行的 PST 存储提供程序相关联的所有会话对象。 
  
## <a name="cmsprovidershutdown-example"></a>CMSProvider::ShutDown() 示例

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
  
[初始化包装的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)
  
[登录包装的 PST 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
  
[使用包装的 PST 存储区提供程序](using-a-wrapped-pst-store-provider.md)

