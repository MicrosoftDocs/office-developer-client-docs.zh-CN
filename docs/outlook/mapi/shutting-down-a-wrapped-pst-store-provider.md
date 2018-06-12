---
title: 关机的情况下被环绕的 PST 存储提供程序
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
# <a name="shutting-down-a-wrapped-pst-store-provider"></a><span data-ttu-id="e28f3-103">关机的情况下被环绕的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e28f3-103">Shutting Down a Wrapped PST Store Provider</span></span>

 
  
<span data-ttu-id="e28f3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e28f3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e28f3-105">使用换行的个人文件夹文件 (PST) 存储提供程序之后，您必须正确关闭的换行的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="e28f3-105">After you finish using a wrapped Personal Folders file (PST) store provider, you must properly shut down the wrapped PST store provider.</span></span> <span data-ttu-id="e28f3-106">有关使用换行的 PST 存储提供程序的详细信息，请参阅[使用自动换行 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e28f3-106">For more information about using the wrapped PST store provider, see [Using a Wrapped PST Store Provider](using-a-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="e28f3-107">若要关闭换行的 PST 存储提供程序，必须调用**[IMSProvider::Shutdown](imsprovider-shutdown.md)** 函数。</span><span class="sxs-lookup"><span data-stu-id="e28f3-107">To shut down a wrapped PST store provider, you must call the **[IMSProvider::Shutdown](imsprovider-shutdown.md)** function.</span></span> <span data-ttu-id="e28f3-108">此功能将关闭中有序的方式换行 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="e28f3-108">This functions closes down the wrapped PST store provider in an orderly fashion.</span></span> 
  
<span data-ttu-id="e28f3-109">本主题中，使用从示例自动换行 PST 存储提供程序的代码示例演示了**IMSProvider::Shutdown**函数。</span><span class="sxs-lookup"><span data-stu-id="e28f3-109">In this topic, the **IMSProvider::Shutdown** function is demonstrated by using a code example from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="e28f3-110">本示例实现的换行的太平洋标准时间提供程序旨在与复制 API 结合使用。</span><span class="sxs-lookup"><span data-stu-id="e28f3-110">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="e28f3-111">有关下载并安装示例自动换行 PST 存储提供程序的详细信息，请参阅[安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e28f3-111">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="e28f3-112">有关复制 API 的详细信息，请参阅[有关复制 API](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="e28f3-112">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
## <a name="shut-down-routine"></a><span data-ttu-id="e28f3-113">关闭例程</span><span class="sxs-lookup"><span data-stu-id="e28f3-113">Shut Down Routine</span></span>

<span data-ttu-id="e28f3-114">MAPI 后台处理程序调用**[IMSProvider::Shutdown](imsprovider-shutdown.md)** 函数，其释放的换行的 PST 存储提供程序，以便换行的 PST 存储提供程序可以正确地关闭之前。</span><span class="sxs-lookup"><span data-stu-id="e28f3-114">The MAPI spooler calls the **[IMSProvider::Shutdown](imsprovider-shutdown.md)** function just before it releases the wrapped PST store provider so that the wrapped PST store provider can shut down properly.</span></span> <span data-ttu-id="e28f3-115">函数终止的换行的 PST 存储提供程序相关联的所有会话对象。</span><span class="sxs-lookup"><span data-stu-id="e28f3-115">The function terminates all session objects associated with the wrapped PST store provider.</span></span> 
  
## <a name="cmsprovidershutdown-example"></a><span data-ttu-id="e28f3-116">CMSProvider::ShutDown() 示例</span><span class="sxs-lookup"><span data-stu-id="e28f3-116">CMSProvider::ShutDown() Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e28f3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e28f3-117">See also</span></span>



[<span data-ttu-id="e28f3-118">有关示例包装 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e28f3-118">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="e28f3-119">安装示例自动换行 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e28f3-119">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="e28f3-120">初始化换行的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e28f3-120">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="e28f3-121">登录到换行的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e28f3-121">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="e28f3-122">使用包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e28f3-122">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)

