---
title: 关闭打包的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 0c9e5917-1b96-323d-bf8b-1d3aa1f677d0
description: '上次修改时间: 2012 年7月2日'
ms.openlocfilehash: fa918920213ee77c4d0c1d3ccc239ae7cffe81fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409942"
---
# <a name="shutting-down-a-wrapped-pst-store-provider"></a><span data-ttu-id="352dd-103">关闭打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="352dd-103">Shutting Down a Wrapped PST Store Provider</span></span>

 
  
<span data-ttu-id="352dd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="352dd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="352dd-105">使用包装的个人文件夹文件 (PST) 存储提供程序完成后, 必须正确关闭包装的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="352dd-105">After you finish using a wrapped Personal Folders file (PST) store provider, you must properly shut down the wrapped PST store provider.</span></span> <span data-ttu-id="352dd-106">有关使用包装的 pst 存储区提供程序的详细信息, 请参阅[使用打包的 pst 存储提供程序](using-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="352dd-106">For more information about using the wrapped PST store provider, see [Using a Wrapped PST Store Provider](using-a-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="352dd-107">若要关闭包装的 PST 存储区提供程序, 必须调用**[IMSProvider:: Shutdown](imsprovider-shutdown.md)** 函数。</span><span class="sxs-lookup"><span data-stu-id="352dd-107">To shut down a wrapped PST store provider, you must call the **[IMSProvider::Shutdown](imsprovider-shutdown.md)** function.</span></span> <span data-ttu-id="352dd-108">此函数以有序的方式关闭包装的 PST 存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="352dd-108">This functions closes down the wrapped PST store provider in an orderly fashion.</span></span> 
  
<span data-ttu-id="352dd-109">在本主题中, 使用示例包装的 PST 存储提供程序中的代码示例演示了**IMSProvider:: Shutdown**函数。</span><span class="sxs-lookup"><span data-stu-id="352dd-109">In this topic, the **IMSProvider::Shutdown** function is demonstrated by using a code example from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="352dd-110">此示例实现了一个用于与复制 API 结合使用的打包的 PST 提供程序。</span><span class="sxs-lookup"><span data-stu-id="352dd-110">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="352dd-111">有关下载和安装示例包装的 pst 存储区提供程序的详细信息, 请参阅[安装示例包装的 pst 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="352dd-111">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="352dd-112">有关复制 api 的详细信息, 请参阅[关于复制 api](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="352dd-112">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
## <a name="shut-down-routine"></a><span data-ttu-id="352dd-113">关闭例程</span><span class="sxs-lookup"><span data-stu-id="352dd-113">Shut Down Routine</span></span>

<span data-ttu-id="352dd-114">MAPI 后台处理程序在释放包装的 pst 存储区提供程序之前调用**[IMSProvider:: Shutdown](imsprovider-shutdown.md)** 函数, 以便包装的 pst 存储区提供程序可以正确地关闭。</span><span class="sxs-lookup"><span data-stu-id="352dd-114">The MAPI spooler calls the **[IMSProvider::Shutdown](imsprovider-shutdown.md)** function just before it releases the wrapped PST store provider so that the wrapped PST store provider can shut down properly.</span></span> <span data-ttu-id="352dd-115">该函数终止与打包的 PST 存储区提供程序关联的所有会话对象。</span><span class="sxs-lookup"><span data-stu-id="352dd-115">The function terminates all session objects associated with the wrapped PST store provider.</span></span> 
  
## <a name="cmsprovidershutdown-example"></a><span data-ttu-id="352dd-116">CMSProvider:: ShutDown () 示例</span><span class="sxs-lookup"><span data-stu-id="352dd-116">CMSProvider::ShutDown() Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="352dd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="352dd-117">See also</span></span>



[<span data-ttu-id="352dd-118">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="352dd-118">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="352dd-119">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="352dd-119">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="352dd-120">初始化打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="352dd-120">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="352dd-121">登录到打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="352dd-121">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="352dd-122">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="352dd-122">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)

