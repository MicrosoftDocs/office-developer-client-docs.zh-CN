---
title: 登录包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 364bc5fd-2199-0bb2-142b-9b3b686b2268
description: '上次修改时间: 2012 年7月2日'
ms.openlocfilehash: 96f472d67f144a451046ff61a3ed6c6ff2ff9acf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408984"
---
# <a name="logging-on-to-a-wrapped-pst-store-provider"></a><span data-ttu-id="08b7f-103">登录包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="08b7f-103">Logging on to a wrapped PST store provider</span></span>

<span data-ttu-id="08b7f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08b7f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08b7f-105">必须先初始化和配置包装的个人文件夹文件 (PST) 存储提供程序, 然后才能将 MAPI 登录到打包的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="08b7f-105">Before you can log on MAPI to a wrapped PST store provider, you must initialize and configure the wrapped Personal Folders file (PST) store provider.</span></span> <span data-ttu-id="08b7f-106">有关详细信息, 请参阅[初始化打包的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="08b7f-106">For more information, see [Initializing a Wrapped PST Store Provider](initializing-a-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="08b7f-107">初始化和配置打包的 PST 存储区提供程序后, 必须实现两个登录例程。</span><span class="sxs-lookup"><span data-stu-id="08b7f-107">After you have initialized and configured a wrapped PST store provider, you must implement two logon routines.</span></span> <span data-ttu-id="08b7f-108">**[IMSProvider:: Logon](imsprovider-logon.md)** 函数在 MAPI 上登录到打包的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="08b7f-108">The **[IMSProvider::Logon](imsprovider-logon.md)** function logs on MAPI to the wrapped PST store provider.</span></span> <span data-ttu-id="08b7f-109">**[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)** 函数将 MAPI 后台处理程序登录到打包的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="08b7f-109">The **[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)** function logs on the MAPI spooler to the wrapped PST store provider.</span></span> 
  
<span data-ttu-id="08b7f-110">在本主题中, 通过使用示例包装的 PST 存储区提供程序中的代码示例来演示**IMSProvider:: Logon**函数和**IMSProvider:: SpoolerLogon**函数。</span><span class="sxs-lookup"><span data-stu-id="08b7f-110">In this topic, the **IMSProvider::Logon** function and the **IMSProvider::SpoolerLogon** function are demonstrated by using code examples from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="08b7f-111">此示例实现了一个用于与复制 API 结合使用的打包的 PST 提供程序。</span><span class="sxs-lookup"><span data-stu-id="08b7f-111">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="08b7f-112">有关下载和安装示例包装的 pst 存储区提供程序的详细信息, 请参阅[安装示例包装的 pst 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="08b7f-112">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="08b7f-113">有关复制 api 的详细信息, 请参阅[关于复制 api](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="08b7f-113">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
<span data-ttu-id="08b7f-114">mapi 和 mapi 后台处理程序登录到包装的 PST 存储提供程序后, 即可使用它。</span><span class="sxs-lookup"><span data-stu-id="08b7f-114">After MAPI and the MAPI spooler are logged on to the wrapped PST store provider, it is ready to be used.</span></span> <span data-ttu-id="08b7f-115">有关详细信息, 请参阅[使用打包的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="08b7f-115">For more information, see [Using a Wrapped PST Store Provider](using-a-wrapped-pst-store-provider.md).</span></span>
  
## <a name="mapi-logon-routine"></a><span data-ttu-id="08b7f-116">MAPI 登录例程</span><span class="sxs-lookup"><span data-stu-id="08b7f-116">MAPI Logon routine</span></span>

<span data-ttu-id="08b7f-117">在包装的 pst 存储区提供程序初始化之后, 您必须实现**[IMSProvider:: Logon](imsprovider-logon.md)** 函数以将 MAPI 登录到打包的 pst 存储。</span><span class="sxs-lookup"><span data-stu-id="08b7f-117">After the wrapped PST store provider is initialized, you must implement the **[IMSProvider::Logon](imsprovider-logon.md)** function to log on MAPI to the wrapped PST store.</span></span> <span data-ttu-id="08b7f-118">此函数验证用户凭据并获取提供程序的配置属性。</span><span class="sxs-lookup"><span data-stu-id="08b7f-118">This function validates user credentials and gets the configuration properties for the provider.</span></span> <span data-ttu-id="08b7f-119">您还必须实现该`SetOLFIInOST`函数以设置脱机文件信息 (**[OLFI](olfi.md)** )。</span><span class="sxs-lookup"><span data-stu-id="08b7f-119">You must also implement the  `SetOLFIInOST` function to set the Offline File Info (**[OLFI](olfi.md)** ).</span></span> <span data-ttu-id="08b7f-120">**OLFI**是长期 ID 结构的队列, 包装的 PST 存储提供程序使用这些结构为脱机模式中的新邮件或文件夹分配条目 id。</span><span class="sxs-lookup"><span data-stu-id="08b7f-120">**OLFI** is a queue of long-term ID structures that is used by the wrapped PST store provider to assign an Entry ID for a new message or folder in offline mode.</span></span> <span data-ttu-id="08b7f-121">最后, **IMSProvider:: Logon**函数返回 MAPI 后台处理程序和客户端应用程序可以在`ppMDB`参数中登录到的邮件存储对象。</span><span class="sxs-lookup"><span data-stu-id="08b7f-121">Finally, the **IMSProvider::Logon** function returns a message store object that the MAPI spooler and client applications can log on to in the  `ppMDB` parameter.</span></span> 
  
### <a name="cmsproviderlogon-example"></a><span data-ttu-id="08b7f-122">CMSProvider:: Logon () 示例</span><span class="sxs-lookup"><span data-stu-id="08b7f-122">CMSProvider::Logon() example</span></span>

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

## <a name="mapi-spooler-logon-routine"></a><span data-ttu-id="08b7f-123">MAPI 后台处理程序登录例程</span><span class="sxs-lookup"><span data-stu-id="08b7f-123">MAPI Spooler Logon routine</span></span>

<span data-ttu-id="08b7f-124">类似于**IMSProvider:: Logon**, 您必须实现**[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)** 函数以将 MAPI 后台处理程序记录到包装的 PST 存储中。</span><span class="sxs-lookup"><span data-stu-id="08b7f-124">Similar to **IMSProvider::Logon**, you must implement the **[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)** function to log the MAPI spooler on to the wrapped PST store.</span></span> <span data-ttu-id="08b7f-125">MAPI 后台处理程序和客户端应用程序可以登录到的邮件存储对象在`ppMDB`参数中返回。</span><span class="sxs-lookup"><span data-stu-id="08b7f-125">A message store object that the MAPI spooler and client applications can log on to is returned in the  `ppMDB` parameter.</span></span> 
  
### <a name="cmsproviderspoolerlogon-example"></a><span data-ttu-id="08b7f-126">CMSProvider:: SpoolerLogon () 示例</span><span class="sxs-lookup"><span data-stu-id="08b7f-126">CMSProvider::SpoolerLogon() example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="08b7f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08b7f-127">See also</span></span>

- [<span data-ttu-id="08b7f-128">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="08b7f-128">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md) 
- [<span data-ttu-id="08b7f-129">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="08b7f-129">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md) 
- [<span data-ttu-id="08b7f-130">初始化打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="08b7f-130">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="08b7f-131">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="08b7f-131">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="08b7f-132">关闭打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="08b7f-132">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)

