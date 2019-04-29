---
title: 使用包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 98f08432-e86c-cba6-45fd-5a6c94d50aaf
description: 上次修改时间:03 月3日, 2012
ms.openlocfilehash: b7c651044ab7f4cad7032db69e157c9a3589bde9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420820"
---
# <a name="using-a-wrapped-pst-store-provider"></a><span data-ttu-id="58a93-103">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="58a93-103">Using a wrapped PST store provider</span></span>

<span data-ttu-id="58a93-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58a93-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58a93-105">在可以使用包装的个人文件夹文件 (PST) 存储提供程序之前, 您必须初始化和配置打包的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="58a93-105">Before you can use a wrapped Personal Folders file (PST) store provider, you must initialize and configure the wrapped PST store provider.</span></span> <span data-ttu-id="58a93-106">在配置包装的 PST 存储区提供程序后, 必须实现功能, 以便 mapi 和 mapi 后台处理程序可以登录到邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="58a93-106">After the wrapped PST store provider is configured, you must implement functions so that MAPI and the MAPI spooler can log on to the message store provider.</span></span> <span data-ttu-id="58a93-107">有关初始化和登录到包装的 pst 存储区提供程序的详细信息, 请参阅[初始化包装的 pst 存储提供程序](initializing-a-wrapped-pst-store-provider.md), 并[登录到包装的 pst 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="58a93-107">For more information about initializing and logging on to a wrapped PST store provider, see [Initializing a Wrapped PST Store Provider](initializing-a-wrapped-pst-store-provider.md) and [Logging On to a Wrapped PST Store Provider](logging-on-to-a-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="58a93-108">**[IMAPISupport:: IUnknown](imapisupportiunknown.md)** 接口提供通常由邮件存储提供程序执行的任务的实现。</span><span class="sxs-lookup"><span data-stu-id="58a93-108">The **[IMAPISupport::IUnknown](imapisupportiunknown.md)** interface provides implementations for tasks that are commonly performed by message store providers.</span></span> <span data-ttu-id="58a93-109">若要使示例包装的 PST 存储区提供程序正常工作, 必须包装此接口。</span><span class="sxs-lookup"><span data-stu-id="58a93-109">This interface must be wrapped for the Sample Wrapped PST Store Provider to work.</span></span> <span data-ttu-id="58a93-110">**[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)** 函数需要特殊实现。</span><span class="sxs-lookup"><span data-stu-id="58a93-110">The **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** function requires special implementation.</span></span> <span data-ttu-id="58a93-111">所有其他函数都可以将其参数传递给基础包装对象。</span><span class="sxs-lookup"><span data-stu-id="58a93-111">All other functions can pass their parameters to the underlying wrapped object.</span></span> 
  
<span data-ttu-id="58a93-112">在本主题中, 使用示例包装的 PST 存储提供程序中的代码示例演示了**IMAPISupport:: OpenProfileSection**函数。</span><span class="sxs-lookup"><span data-stu-id="58a93-112">In this topic, the **IMAPISupport::OpenProfileSection** function is demonstrated by using a code example from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="58a93-113">此示例实现了一个用于与复制 API 结合使用的打包的 PST 提供程序。</span><span class="sxs-lookup"><span data-stu-id="58a93-113">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="58a93-114">有关下载和安装示例包装的 pst 存储区提供程序的详细信息, 请参阅[安装示例包装的 pst 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="58a93-114">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="58a93-115">有关复制 api 的详细信息, 请参阅[关于复制 api](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="58a93-115">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
<span data-ttu-id="58a93-116">使用包装的 pst 存储区提供程序完成后, 必须正确关闭包装的 pst 存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="58a93-116">When you finish using a wrapped PST store provider, you must properly shut down the wrapped PST store provider.</span></span> <span data-ttu-id="58a93-117">有关详细信息, 请参阅[关闭包装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="58a93-117">For more information, see [Shutting Down a Wrapped PST Store Provider](shutting-down-a-wrapped-pst-store-provider.md).</span></span>
  
## <a name="open-profile-section-routine"></a><span data-ttu-id="58a93-118">打开配置文件部分例程</span><span class="sxs-lookup"><span data-stu-id="58a93-118">Open Profile Section routine</span></span>

<span data-ttu-id="58a93-119">**[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)** 函数打开当前配置文件的节。</span><span class="sxs-lookup"><span data-stu-id="58a93-119">The **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** function opens a section of the current profile.</span></span> <span data-ttu-id="58a93-120">该函数需要在包装的 PST 存储区提供程序实现中进行特殊处理。</span><span class="sxs-lookup"><span data-stu-id="58a93-120">The function requires special handling in the wrapped PST store provider implementation.</span></span> <span data-ttu-id="58a93-121">`pgNSTGlobalProfileSectionGuid`请求时, 该函数将返回缓存的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="58a93-121">When the  `pgNSTGlobalProfileSectionGuid` is requested, the function returns the profile section that is cached.</span></span> 
  
### <a name="csupportopenprofilesection-example"></a><span data-ttu-id="58a93-122">CSupport:: OpenProfileSection () 示例</span><span class="sxs-lookup"><span data-stu-id="58a93-122">CSupport::OpenProfileSection() example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="58a93-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58a93-123">See also</span></span>

- [<span data-ttu-id="58a93-124">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="58a93-124">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="58a93-125">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="58a93-125">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="58a93-126">初始化打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="58a93-126">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="58a93-127">登录到打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="58a93-127">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="58a93-128">关闭打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="58a93-128">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)

