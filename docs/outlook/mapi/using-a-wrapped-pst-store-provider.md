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
# <a name="using-a-wrapped-pst-store-provider"></a><span data-ttu-id="e2ddd-103">使用换行的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e2ddd-103">Using a wrapped PST store provider</span></span>

<span data-ttu-id="e2ddd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e2ddd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e2ddd-105">您可以使用换行的个人文件夹文件 (PST) 存储提供程序之前，您必须初始化并配置的换行的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-105">Before you can use a wrapped Personal Folders file (PST) store provider, you must initialize and configure the wrapped PST store provider.</span></span> <span data-ttu-id="e2ddd-106">配置的换行的 PST 存储提供程序后，您必须实现函数，以便 MAPI 和 MAPI 后台处理程序可以登录到的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-106">After the wrapped PST store provider is configured, you must implement functions so that MAPI and the MAPI spooler can log on to the message store provider.</span></span> <span data-ttu-id="e2ddd-107">有关初始化和登录到换行的 PST 存储提供程序的详细信息，请参阅[初始化自动换行 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)和[日志记录上为一个自动换行 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-107">For more information about initializing and logging on to a wrapped PST store provider, see [Initializing a Wrapped PST Store Provider](initializing-a-wrapped-pst-store-provider.md) and [Logging On to a Wrapped PST Store Provider](logging-on-to-a-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="e2ddd-108">**[IMAPISupport::IUnknown](imapisupportiunknown.md)** 接口提供了实现任务的常执行的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-108">The **[IMAPISupport::IUnknown](imapisupportiunknown.md)** interface provides implementations for tasks that are commonly performed by message store providers.</span></span> <span data-ttu-id="e2ddd-109">必须为示例自动换行 PST 存储提供程序以包装此接口。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-109">This interface must be wrapped for the Sample Wrapped PST Store Provider to work.</span></span> <span data-ttu-id="e2ddd-110">**[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** 函数需要特殊的实现。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-110">The **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** function requires special implementation.</span></span> <span data-ttu-id="e2ddd-111">所有其他函数可以将其参数传递给基础被环绕对象。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-111">All other functions can pass their parameters to the underlying wrapped object.</span></span> 
  
<span data-ttu-id="e2ddd-112">本主题中，使用从示例自动换行 PST 存储提供程序的代码示例演示了**IMAPISupport::OpenProfileSection**函数。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-112">In this topic, the **IMAPISupport::OpenProfileSection** function is demonstrated by using a code example from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="e2ddd-113">本示例实现的换行的太平洋标准时间提供程序旨在与复制 API 结合使用。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-113">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="e2ddd-114">有关下载并安装示例自动换行 PST 存储提供程序的详细信息，请参阅[安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-114">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="e2ddd-115">有关复制 API 的详细信息，请参阅[有关复制 API](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-115">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
<span data-ttu-id="e2ddd-116">当您完成使用换行的 PST 存储提供程序时，您必须正确关闭换行 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-116">When you finish using a wrapped PST store provider, you must properly shut down the wrapped PST store provider.</span></span> <span data-ttu-id="e2ddd-117">有关详细信息，请参阅[关机的情况下自动换行 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-117">For more information, see [Shutting Down a Wrapped PST Store Provider](shutting-down-a-wrapped-pst-store-provider.md).</span></span>
  
## <a name="open-profile-section-routine"></a><span data-ttu-id="e2ddd-118">打开配置文件部分例程</span><span class="sxs-lookup"><span data-stu-id="e2ddd-118">Open Profile Section routine</span></span>

<span data-ttu-id="e2ddd-119">**[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** 函数将打开当前配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-119">The **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** function opens a section of the current profile.</span></span> <span data-ttu-id="e2ddd-120">该函数需要在换行 PST 存储提供程序实现的专门处理措施。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-120">The function requires special handling in the wrapped PST store provider implementation.</span></span> <span data-ttu-id="e2ddd-121">当`pgNSTGlobalProfileSectionGuid`请求时，此函数返回缓存配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="e2ddd-121">When the  `pgNSTGlobalProfileSectionGuid` is requested, the function returns the profile section that is cached.</span></span> 
  
### <a name="csupportopenprofilesection-example"></a><span data-ttu-id="e2ddd-122">CSupport::OpenProfileSection() 示例</span><span class="sxs-lookup"><span data-stu-id="e2ddd-122">CSupport::OpenProfileSection() example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e2ddd-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2ddd-123">See also</span></span>

- [<span data-ttu-id="e2ddd-124">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="e2ddd-124">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="e2ddd-125">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="e2ddd-125">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="e2ddd-126">初始化包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="e2ddd-126">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="e2ddd-127">登录包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="e2ddd-127">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="e2ddd-128">关闭包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="e2ddd-128">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)

