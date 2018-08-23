---
title: 登录到换行的 PST 存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 364bc5fd-2199-0bb2-142b-9b3b686b2268
description: 上次修改时间： 2012 年 7 月 2 日
ms.openlocfilehash: 0716017788239c22f31007438089118d109010a3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570476"
---
# <a name="logging-on-to-a-wrapped-pst-store-provider"></a><span data-ttu-id="eda2a-103">登录到换行的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="eda2a-103">Logging on to a wrapped PST store provider</span></span>

<span data-ttu-id="eda2a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eda2a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eda2a-105">您可以日志上 MAPI 到换行的 PST 存储提供程序之前，您必须初始化并配置的换行的个人文件夹文件 (PST) 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="eda2a-105">Before you can log on MAPI to a wrapped PST store provider, you must initialize and configure the wrapped Personal Folders file (PST) store provider.</span></span> <span data-ttu-id="eda2a-106">有关详细信息，请参阅[初始化自动换行 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="eda2a-106">For more information, see [Initializing a Wrapped PST Store Provider](initializing-a-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="eda2a-107">已初始化并配置换行的 PST 存储提供程序后，您必须实现两个登录例程。</span><span class="sxs-lookup"><span data-stu-id="eda2a-107">After you have initialized and configured a wrapped PST store provider, you must implement two logon routines.</span></span> <span data-ttu-id="eda2a-108">**[IMSProvider::Logon](imsprovider-logon.md)** 函数登录到的换行的 PST 存储提供程序的 MAPI。</span><span class="sxs-lookup"><span data-stu-id="eda2a-108">The **[IMSProvider::Logon](imsprovider-logon.md)** function logs on MAPI to the wrapped PST store provider.</span></span> <span data-ttu-id="eda2a-109">**[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)** 函数登录到的换行的 PST 存储提供程序 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="eda2a-109">The **[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)** function logs on the MAPI spooler to the wrapped PST store provider.</span></span> 
  
<span data-ttu-id="eda2a-110">本主题中使用从示例自动换行 PST 存储提供程序的代码示例演示了**IMSProvider::Logon**函数和**IMSProvider::SpoolerLogon**函数。</span><span class="sxs-lookup"><span data-stu-id="eda2a-110">In this topic, the **IMSProvider::Logon** function and the **IMSProvider::SpoolerLogon** function are demonstrated by using code examples from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="eda2a-111">本示例实现的换行的太平洋标准时间提供程序旨在与复制 API 结合使用。</span><span class="sxs-lookup"><span data-stu-id="eda2a-111">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="eda2a-112">有关下载并安装示例自动换行 PST 存储提供程序的详细信息，请参阅[安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="eda2a-112">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="eda2a-113">有关复制 API 的详细信息，请参阅[有关复制 API](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="eda2a-113">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
<span data-ttu-id="eda2a-114">MAPI 和 MAPI 后台处理程序都将记录后换行 PST 到存储提供程序，系统已准备好使用。</span><span class="sxs-lookup"><span data-stu-id="eda2a-114">After MAPI and the MAPI spooler are logged on to the wrapped PST store provider, it is ready to be used.</span></span> <span data-ttu-id="eda2a-115">有关详细信息，请参阅[使用自动换行 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="eda2a-115">For more information, see [Using a Wrapped PST Store Provider](using-a-wrapped-pst-store-provider.md).</span></span>
  
## <a name="mapi-logon-routine"></a><span data-ttu-id="eda2a-116">MAPI 登录例程</span><span class="sxs-lookup"><span data-stu-id="eda2a-116">MAPI Logon routine</span></span>

<span data-ttu-id="eda2a-117">初始化的换行的 PST 存储提供程序后，您必须实现要登录到换行的 PST 存储 MAPI 的**[IMSProvider::Logon](imsprovider-logon.md)** 函数。</span><span class="sxs-lookup"><span data-stu-id="eda2a-117">After the wrapped PST store provider is initialized, you must implement the **[IMSProvider::Logon](imsprovider-logon.md)** function to log on MAPI to the wrapped PST store.</span></span> <span data-ttu-id="eda2a-118">此函数验证用户凭据，并获取提供程序的配置属性。</span><span class="sxs-lookup"><span data-stu-id="eda2a-118">This function validates user credentials and gets the configuration properties for the provider.</span></span> <span data-ttu-id="eda2a-119">您还必须实现`SetOLFIInOST`函数设置脱机文件信息 (**[OLFI](olfi.md)** )。</span><span class="sxs-lookup"><span data-stu-id="eda2a-119">You must also implement the  `SetOLFIInOST` function to set the Offline File Info (**[OLFI](olfi.md)** ).</span></span> <span data-ttu-id="eda2a-120">**OLFI**是长期 ID 结构的换行 PST 存储提供程序用于分配新的邮件或文件夹在脱机模式下的条目 ID 的队列。</span><span class="sxs-lookup"><span data-stu-id="eda2a-120">**OLFI** is a queue of long-term ID structures that is used by the wrapped PST store provider to assign an Entry ID for a new message or folder in offline mode.</span></span> <span data-ttu-id="eda2a-121">最后，该**IMSProvider::Logon**函数返回的 MAPI 后台处理程序和客户端应用程序中可以登录到的消息存储对象`ppMDB`参数。</span><span class="sxs-lookup"><span data-stu-id="eda2a-121">Finally, the **IMSProvider::Logon** function returns a message store object that the MAPI spooler and client applications can log on to in the  `ppMDB` parameter.</span></span> 
  
### <a name="cmsproviderlogon-example"></a><span data-ttu-id="eda2a-122">CMSProvider::Logon() 示例</span><span class="sxs-lookup"><span data-stu-id="eda2a-122">CMSProvider::Logon() example</span></span>

```cpp
STDMETHODIMP CMSProvider::Logon( 
    LPMAPISUP pSupObj, 
    ULONG ulUIParam, 
    LPTSTR pszProfileName, 
    ULONG cbEntryID, 
    LPENTRYID pEntryID, 
    ULONG ulFlags, 
    LPCIID pInterface, 
    ULONG * pcbSpoolSecurity, 
    LPBYTE * ppbSpoolSecurity, 
    LPMAPIERROR * ppMAPIError, 
    LPMSLOGON * ppMSLogon, 
    LPMDB * ppMDB) 
{ 
    HRESULT hRes = S_OK; 
    LPMDB lpPSTMDB = NULL; 
    CMsgStore* pWrappedMDB = NULL; 
 
    Log(true,"CMSProvider::Logon Pst logon Called\n"); 
 
    LPPROFSECT lpProfSect = NULL; 
    CSupport * pMySup = NULL; 
    hRes = GetGlobalProfileObject(pSupObj,&lpProfSect); 
    pMySup = new CSupport(pSupObj, lpProfSect); 
    if (!pMySup) 
    { 
        Log(true,"CMSProvider::Logon: Failed to allocate new CSupport object\n"); 
        hRes = E_OUTOFMEMORY; 
    } 
    if (SUCCEEDED(hRes)) 
    { 
        ulFlags = (ulFlags & ~MDB_OST_LOGON_ANSI) | MDB_OST_LOGON_UNICODE; 
        hRes = m_pPSTMS->Logon( 
            pMySup, 
            ulUIParam,  
            pszProfileName,  
            cbEntryID, 
            pEntryID,  
            ulFlags,  
            pInterface,  
            pcbSpoolSecurity, 
            ppbSpoolSecurity,  
            ppMAPIError,  
            ppMSLogon,  
            &lpPSTMDB); 
    } 
    Log(true,"CMSProvider::Logon returned 0x%08X\n", hRes); 
 
    // Set up the MDB to allow synchronization 
    if (SUCCEEDED(hRes)) 
    { 
        hRes = SetOLFIInOST(lpPSTMDB); 
        Log(true,"SetOLFIInOST returned 0x%08X\n", hRes); 
    } 
    // Wrap the outgoing MDB 
    pWrappedMDB = new CMsgStore (lpPSTMDB); 
    if (NULL == pWrappedMDB) 
    { 
        Log(true,"CMSProvider::Logon: Failed to allocate new CMsgStore object\n"); 
        hRes = E_OUTOFMEMORY; 
    } 
    // Copy pointer to the allocated object back into the return LPMDB object pointer 
    *ppMDB = pWrappedMDB; 
    if (lpProfSect) lpProfSect->Release(); 
 
    return hRes; 
}
```

## <a name="mapi-spooler-logon-routine"></a><span data-ttu-id="eda2a-123">MAPI 后台处理程序登录例程</span><span class="sxs-lookup"><span data-stu-id="eda2a-123">MAPI Spooler Logon routine</span></span>

<span data-ttu-id="eda2a-124">类似于**IMSProvider::Logon**，您必须实现**[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)** 函数以登录到的换行的 PST 存储 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="eda2a-124">Similar to **IMSProvider::Logon**, you must implement the **[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)** function to log the MAPI spooler on to the wrapped PST store.</span></span> <span data-ttu-id="eda2a-125">MAPI 后台处理程序和客户端应用程序可以登录到的消息存储对象返回在`ppMDB`参数。</span><span class="sxs-lookup"><span data-stu-id="eda2a-125">A message store object that the MAPI spooler and client applications can log on to is returned in the  `ppMDB` parameter.</span></span> 
  
### <a name="cmsproviderspoolerlogon-example"></a><span data-ttu-id="eda2a-126">CMSProvider::SpoolerLogon() 示例</span><span class="sxs-lookup"><span data-stu-id="eda2a-126">CMSProvider::SpoolerLogon() example</span></span>

```cpp
STDMETHODIMP CMSProvider::SpoolerLogon ( 
    LPMAPISUP pSupObj, 
    ULONG ulUIParam, 
    LPTSTR pszProfileName, 
    ULONG cbEntryID, 
    LPENTRYID pEntryID, 
    ULONG ulFlags, 
    LPCIID pInterface, 
    ULONG cbSpoolSecurity, 
    LPBYTE pbSpoolSecurity, 
    LPMAPIERROR * ppMAPIError, 
    LPMSLOGON * ppMSLogon, 
    LPMDB * ppMDB) 
{ 
    HRESULT hRes = S_OK; 
     
    Log(true,"CMSProvider::SpoolerLogon\n"); 
    LPPROFSECT lpProfSect = NULL; 
    CSupport * pMySup = NULL; 
    hRes = GetGlobalProfileObject(pSupObj,&lpProfSect); 
    pMySup = new CSupport(pSupObj, lpProfSect); 
    if (!pMySup) 
    { 
        Log(true,"CMSProvider::SpoolerLogon: " + 
            "Failed to allocate new CSupport object\n"); 
        hRes = E_OUTOFMEMORY; 
    } 
    if (SUCCEEDED(hRes)) 
    { 
        hRes = m_pPSTMS->SpoolerLogon(  
            pMySup,//pSupObj, 
            ulUIParam, 
            pszProfileName, 
            cbEntryID, 
            pEntryID, 
            ulFlags, 
            pInterface, 
            cbSpoolSecurity, 
            pbSpoolSecurity, 
            ppMAPIError, 
            ppMSLogon, 
            ppMDB); 
    } 
    Log(true,"CMSProvider::SpoolerLogon returned 0x%08X\n", hRes); 
 
    return hRes; 
}
```

## <a name="see-also"></a><span data-ttu-id="eda2a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eda2a-127">See also</span></span>

- [<span data-ttu-id="eda2a-128">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="eda2a-128">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md) 
- [<span data-ttu-id="eda2a-129">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="eda2a-129">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md) 
- [<span data-ttu-id="eda2a-130">初始化包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="eda2a-130">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="eda2a-131">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="eda2a-131">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="eda2a-132">关闭包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="eda2a-132">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)

