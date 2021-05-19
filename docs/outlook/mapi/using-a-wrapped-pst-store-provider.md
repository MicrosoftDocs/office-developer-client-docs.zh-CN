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
# <a name="using-a-wrapped-pst-store-provider"></a><span data-ttu-id="7ee4f-103">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="7ee4f-103">Using a wrapped PST store provider</span></span>

<span data-ttu-id="7ee4f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ee4f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ee4f-105">在 PST 存储提供程序中可以使用包装的个人 (文件) ，必须初始化和配置包装的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-105">Before you can use a wrapped Personal Folders file (PST) store provider, you must initialize and configure the wrapped PST store provider.</span></span> <span data-ttu-id="7ee4f-106">配置包装的 PST 存储提供程序后，必须实现函数，以便 MAPI 和 MAPI 后台处理程序可以登录到邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-106">After the wrapped PST store provider is configured, you must implement functions so that MAPI and the MAPI spooler can log on to the message store provider.</span></span> <span data-ttu-id="7ee4f-107">有关初始化封装 PST 存储提供程序并登录到包装 [的 PST](initializing-a-wrapped-pst-store-provider.md) 存储提供程序的信息，请参阅初始化封装的 PST 存储提供程序和登录到封装的 PST [存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-107">For more information about initializing and logging on to a wrapped PST store provider, see [Initializing a Wrapped PST Store Provider](initializing-a-wrapped-pst-store-provider.md) and [Logging On to a Wrapped PST Store Provider](logging-on-to-a-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="7ee4f-108">**[IMAPISupport：：IUnknown](imapisupportiunknown.md)** 接口为邮件存储提供程序通常执行的任务提供实现。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-108">The **[IMAPISupport::IUnknown](imapisupportiunknown.md)** interface provides implementations for tasks that are commonly performed by message store providers.</span></span> <span data-ttu-id="7ee4f-109">必须包装此接口，示例封装 PST 存储提供程序工作。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-109">This interface must be wrapped for the Sample Wrapped PST Store Provider to work.</span></span> <span data-ttu-id="7ee4f-110">**[IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)** 函数需要特殊实现。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-110">The **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** function requires special implementation.</span></span> <span data-ttu-id="7ee4f-111">所有其他函数都可以将参数传递给基础封装对象。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-111">All other functions can pass their parameters to the underlying wrapped object.</span></span> 
  
<span data-ttu-id="7ee4f-112">在本主题中，使用示例封装 PST 存储提供程序中的代码示例演示 **了 IMAPISupport：：OpenProfileSection** 函数。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-112">In this topic, the **IMAPISupport::OpenProfileSection** function is demonstrated by using a code example from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="7ee4f-113">该示例实现一个包装的 PST 提供程序，旨在与复制 API 结合使用。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-113">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="7ee4f-114">有关下载和安装包装的示例 PST 存储提供程序详细信息，请参阅安装包装的 PST 存储 [提供程序示例](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-114">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="7ee4f-115">有关复制 API 的信息，请参阅[关于复制 API。](about-the-replication-api.md)</span><span class="sxs-lookup"><span data-stu-id="7ee4f-115">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
<span data-ttu-id="7ee4f-116">使用包装的 PST 存储提供程序完成后，必须正确关闭包装的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-116">When you finish using a wrapped PST store provider, you must properly shut down the wrapped PST store provider.</span></span> <span data-ttu-id="7ee4f-117">有关详细信息，请参阅 [关闭封装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-117">For more information, see [Shutting Down a Wrapped PST Store Provider](shutting-down-a-wrapped-pst-store-provider.md).</span></span>
  
## <a name="open-profile-section-routine"></a><span data-ttu-id="7ee4f-118">Open Profile Section 例程</span><span class="sxs-lookup"><span data-stu-id="7ee4f-118">Open Profile Section routine</span></span>

<span data-ttu-id="7ee4f-119">**[IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)** 函数打开当前配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-119">The **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** function opens a section of the current profile.</span></span> <span data-ttu-id="7ee4f-120">该函数需要在封装的 PST 存储提供程序实现中进行特殊处理。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-120">The function requires special handling in the wrapped PST store provider implementation.</span></span> <span data-ttu-id="7ee4f-121">请求  `pgNSTGlobalProfileSectionGuid` 时，函数将返回缓存的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="7ee4f-121">When the  `pgNSTGlobalProfileSectionGuid` is requested, the function returns the profile section that is cached.</span></span> 
  
### <a name="csupportopenprofilesection-example"></a><span data-ttu-id="7ee4f-122">CSupport：：OpenProfileSection () 示例</span><span class="sxs-lookup"><span data-stu-id="7ee4f-122">CSupport::OpenProfileSection() example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7ee4f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ee4f-123">See also</span></span>

- [<span data-ttu-id="7ee4f-124">关于包装的 PST 存储提供程序示例</span><span class="sxs-lookup"><span data-stu-id="7ee4f-124">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="7ee4f-125">安装包装的 PST 存储提供程序示例</span><span class="sxs-lookup"><span data-stu-id="7ee4f-125">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="7ee4f-126">初始化包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="7ee4f-126">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="7ee4f-127">登录到包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="7ee4f-127">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="7ee4f-128">关闭包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="7ee4f-128">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)

