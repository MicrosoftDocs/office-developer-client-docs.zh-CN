---
title: 初始化包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 07633717-ba4c-b146-ad65-60b37ab98ab6
description: '上次修改时间: 2012 年10月5日'
ms.openlocfilehash: 31114e4082fbc5e4c57da95eb6b32339822b1645
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317239"
---
# <a name="initializing-a-wrapped-pst-store-provider"></a><span data-ttu-id="35ac1-103">初始化包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="35ac1-103">Initializing a wrapped PST store provider</span></span>

<span data-ttu-id="35ac1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="35ac1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="35ac1-105">若要实现包装的个人文件夹文件 (PST) 存储提供程序, 必须使用**[MSProviderInit](msproviderinit.md)** 函数作为入口点来初始化包装的 PST 存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="35ac1-105">To implement a wrapped Personal Folders file (PST) store provider, you must initialize the wrapped PST store provider by using the **[MSProviderInit](msproviderinit.md)** function as an entry point.</span></span> <span data-ttu-id="35ac1-106">初始化提供程序的 DLL 之后, **[MSGSERVICEENTRY](msgserviceentry.md)** 函数将配置打包的 PST 存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="35ac1-106">After the provider's DLL is initialized, the **[MSGSERVICEENTRY](msgserviceentry.md)** function configures the wrapped PST store provider.</span></span> 
  
<span data-ttu-id="35ac1-107">在本主题中, 通过使用示例包装的 PST 存储区提供程序中的代码示例来演示**MSProviderInit**函数和**MSGSERVICEENTRY**函数。</span><span class="sxs-lookup"><span data-stu-id="35ac1-107">In this topic, the **MSProviderInit** function and the **MSGSERVICEENTRY** function are demonstrated by using code examples from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="35ac1-108">此示例实现了一个用于与复制 API 结合使用的打包的 PST 提供程序。</span><span class="sxs-lookup"><span data-stu-id="35ac1-108">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="35ac1-109">有关下载和安装示例包装的 pst 存储区提供程序的详细信息, 请参阅[安装示例包装的 pst 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="35ac1-109">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="35ac1-110">有关复制 api 的详细信息, 请参阅[关于复制 api](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="35ac1-110">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
<span data-ttu-id="35ac1-111">初始化包装的 PST 存储区提供程序后, 必须实现功能, 以便 mapi 和 mapi 后台处理程序可以登录到邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="35ac1-111">After you have initialized a wrapped PST store provider, you must implement functions so that MAPI and the MAPI spooler can log onto the message store provider.</span></span> <span data-ttu-id="35ac1-112">有关详细信息, 请参阅[登录到打包的 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="35ac1-112">For more information, see [Logging On to a Wrapped PST Store Provider](logging-on-to-a-wrapped-pst-store-provider.md).</span></span>
  
## <a name="initialization-routine"></a><span data-ttu-id="35ac1-113">初始化例程</span><span class="sxs-lookup"><span data-stu-id="35ac1-113">Initialization routine</span></span>

<span data-ttu-id="35ac1-114">所有包装的 PST 存储区提供程序都必须将**[MSProviderInit](msproviderinit.md)** 函数实现为初始化提供程序 DLL 的入口点。</span><span class="sxs-lookup"><span data-stu-id="35ac1-114">All wrapped PST store providers must implement the **[MSProviderInit](msproviderinit.md)** function as an entry point to initialize the provider's DLL.</span></span> <span data-ttu-id="35ac1-115">**MSProviderInit**检查服务提供程序接口`ulMAPIVer`的版本号是否与当前版本号, `CURRENT_SPI_VERSION`是否兼容。</span><span class="sxs-lookup"><span data-stu-id="35ac1-115">**MSProviderInit** checks to see if the version number of the service provider interface,  `ulMAPIVer`, is compatible with the current version number,  `CURRENT_SPI_VERSION`.</span></span> <span data-ttu-id="35ac1-116">函数将 MAPI 内存管理例程保存到`g_lpAllocateBuffer`、 `g_lpAllocateMore`和`g_lpFreeBuffer`参数中。</span><span class="sxs-lookup"><span data-stu-id="35ac1-116">The function saves the MAPI memory management routines into the  `g_lpAllocateBuffer`,  `g_lpAllocateMore`, and  `g_lpFreeBuffer` parameters.</span></span> <span data-ttu-id="35ac1-117">应在整个包装的 PST 存储实现中使用这些内存管理例程, 以实现内存分配和释放。</span><span class="sxs-lookup"><span data-stu-id="35ac1-117">These memory management routines should be used throughout the wrapped PST store implementation for memory allocation and deallocation.</span></span> 
  
### <a name="msproviderinit-example"></a><span data-ttu-id="35ac1-118">MSProviderInit () 示例</span><span class="sxs-lookup"><span data-stu-id="35ac1-118">MSProviderInit() example</span></span>

```cpp
STDINITMETHODIMP MSProviderInit ( 
    HINSTANCE /*hInstance*/, 
    LPMALLOC lpMalloc, 
    LPALLOCATEBUFFER lpAllocateBuffer, 
    LPALLOCATEMORE lpAllocateMore, 
    LPFREEBUFFER lpFreeBuffer, 
    ULONG ulFlags, 
    ULONG ulMAPIVer, 
    ULONG FAR * lpulProviderVer, 
    LPMSPROVIDER FAR * lppMSProvider) 
{ 
    Log(true,"MSProviderInit function called\n"); 
    if (!lppMSProvider || !lpulProviderVer) return MAPI_E_INVALID_PARAMETER; 
    HRESULT hRes = S_OK; 
 
    *lppMSProvider = NULL; 
    *lpulProviderVer = CURRENT_SPI_VERSION; 
    if (ulMAPIVer < CURRENT_SPI_VERSION) 
    { 
        Log(true,"MSProviderInit: The version of the subsystem cannot handle this" 
            + "version of the provider\n"); 
        return MAPI_E_VERSION; 
    } 
 
    Log(true,"MSProviderInit: saving off memory management routines\n"); 
    g_lpAllocateBuffer = lpAllocateBuffer; 
    g_lpAllocateMore = lpAllocateMore; 
    g_lpFreeBuffer = lpFreeBuffer; 
    HMODULE hm = LoadLibrary("C:\\Program Files\\Common Files\\System" + 
        "\\MSMAPI\\1033\\MSPST32.dll" ); 
    if (!hm) hm = LoadLibrary("C:\\Program Files\\Microsoft Office\\Office12" + 
        "\\MSPST32.dll" ); 
    Log(true,"LoadLibrary returned 0x%08X\n", hm); 
 
    LPMSPROVIDERINIT pMsProviderInit = NULL; 
    if (hm) 
    { 
        pMsProviderInit = (LPMSPROVIDERINIT)GetProcAddress(hm, "MSProviderInit"); 
        Log(true,"GetProcAddress returned 0x%08X\n", pMsProviderInit); 
    } 
    else hRes = E_OUTOFMEMORY; 
    if (pMsProviderInit) 
    { 
        Log(true,"Calling pMsProviderInit\n"); 
        CMSProvider* pWrappedProvider = NULL; 
        LPMSPROVIDER pSyncProviderObj = NULL; 
        hRes = pMsProviderInit( 
            hm,// not hInstance: first param is handle of module in which the function lives 
            lpMalloc, 
            lpAllocateBuffer, 
            lpAllocateMore, 
            lpFreeBuffer, 
            ulFlags, 
            ulMAPIVer, 
            lpulProviderVer, 
            &pSyncProviderObj                         
            ); 
        Log(true,"pMsProviderInit returned 0x%08X\n", hRes); 
        if (SUCCEEDED(hRes)) 
        { 
            pWrappedProvider = new CMSProvider (pSyncProviderObj); 
            if (NULL == pWrappedProvider) 
            { 
                Log(true,"MSProviderInit: Failed to allocate new CMSProvider object\n"); 
                hRes = E_OUTOFMEMORY; 
            } 
            // Copy pointer to the allocated object back into the  
            //return IMSProvider object pointer 
            *lppMSProvider = pWrappedProvider; 
        } 
    } 
    else hRes = E_OUTOFMEMORY; 
    return hRes; 
}
```

### <a name="wrapped-pst-and-unicode-paths"></a><span data-ttu-id="35ac1-119">打包的 PST 和 Unicode 路径</span><span class="sxs-lookup"><span data-stu-id="35ac1-119">Wrapped PST and Unicode paths</span></span>

<span data-ttu-id="35ac1-120">若要 retrofit 在 microsoft Visual Studio 2008 中准备的原始示例, 以便使用 NST 的 unicode 路径以在启用 Unicode 的 Microsoft Outlook 2010 和 Outlook 2013 中使用, 则生成条目标识符的**CreateStoreEntryID**例程应使用一种格式的 ASCII 路径, 另一种格式用于 Unicode 路径。</span><span class="sxs-lookup"><span data-stu-id="35ac1-120">To retrofit the original sample prepared in Microsoft Visual Studio 2008 to use Unicode paths to the NST for use in Unicode-enabled Microsoft Outlook 2010 and Outlook 2013, the **CreateStoreEntryID** routine, which produces the entry identifier, should use one format for ASCII paths, and another for Unicode paths.</span></span> <span data-ttu-id="35ac1-121">这些表示为以下示例中的结构。</span><span class="sxs-lookup"><span data-stu-id="35ac1-121">These are represented as structures in the following example.</span></span> 
  
```cpp
typedef struct                              // short format
{
         BYTE             rgbFlags[4];     // MAPI-defined flags
         MAPIUID          uid;             // PST provider MUID
         BYTE             bReserved;       // Reserved (must be zero)
         CHAR             szPath[1];       // Full path to store (ASCII)
 } EIDMS;
// Unicode version of EIDMSW is an extension of EIDMS
// and szPath is always NULL
typedef struct                              // Long format to support Unicode path and name
{
         BYTE             rgbFlags[4];     // MAPI-defined flags
         MAPIUID          uid;             // PST provider MUID
         BYTE             bReserved;       // Reserved (must be zero)
         CHAR             szPath[1];       // ASCII path to store is always NULL
         WCHAR            wzPath[1];       // Full path to store (Unicode)
} EIDMSW;
```

> [!IMPORTANT]
> <span data-ttu-id="35ac1-122">这些结构中的差异是 Unicode 路径之前的两个 NULL 字节。</span><span class="sxs-lookup"><span data-stu-id="35ac1-122">The differences in these structures are two NULL bytes prior to a Unicode path.</span></span> <span data-ttu-id="35ac1-123">如果需要解释后面的 "服务入口例程" 中的条目标识符, 则可以通过一种方法来确定是否为 EIDMS 强制转换为 "szPath", 然后检查 [0] 是否为 NULL。</span><span class="sxs-lookup"><span data-stu-id="35ac1-123">If you need to interpret the entry identifier in the "Service Entry Routine" that follows, one way to determine whether that is the case or not would be to cast as EIDMS first, then check whether the szPath[0] is NULL.</span></span> <span data-ttu-id="35ac1-124">如果是, 则改为将其转换为 EIDMSW。</span><span class="sxs-lookup"><span data-stu-id="35ac1-124">If it is, cast it as EIDMSW instead.</span></span> 
  
## <a name="service-entry-routine"></a><span data-ttu-id="35ac1-125">服务入口例程</span><span class="sxs-lookup"><span data-stu-id="35ac1-125">Service Entry routine</span></span>

<span data-ttu-id="35ac1-126">**[MSGSERVICEENTRY](msgserviceentry.md)** 函数是在其中配置包装的 PST 存储区提供程序的邮件服务入口点。</span><span class="sxs-lookup"><span data-stu-id="35ac1-126">The **[MSGSERVICEENTRY](msgserviceentry.md)** function is the message service entry point where the wrapped PST store provider is configured.</span></span> <span data-ttu-id="35ac1-127">用于获取 MAPI `GetMemAllocRoutines()`内存管理例程的函数调用。</span><span class="sxs-lookup"><span data-stu-id="35ac1-127">The function calls  `GetMemAllocRoutines()` to get the MAPI memory management routines.</span></span> <span data-ttu-id="35ac1-128">函数使用`lpProviderAdmin`参数查找提供程序的配置文件部分, 并在配置文件中设置属性。</span><span class="sxs-lookup"><span data-stu-id="35ac1-128">The function uses the  `lpProviderAdmin` parameter to locate the profile section for the provider and sets the properties in the profile.</span></span> 
  
### <a name="serviceentry-example"></a><span data-ttu-id="35ac1-129">ServiceEntry () 示例</span><span class="sxs-lookup"><span data-stu-id="35ac1-129">ServiceEntry() example</span></span>

```cpp
HRESULT STDAPICALLTYPE ServiceEntry ( 
    HINSTANCE /*hInstance*/, 
    LPMALLOC lpMalloc, 
    LPMAPISUP lpMAPISup, 
    ULONG ulUIParam, 
    ULONG ulFlags, 
    ULONG ulContext, 
    ULONG cValues, 
    LPSPropValue lpProps, 
    LPPROVIDERADMIN lpProviderAdmin, 
    LPMAPIERROR FAR *lppMapiError) 
{ 
    if (!lpMAPISup || !lpProviderAdmin) return MAPI_E_INVALID_PARAMETER; 
    HRESULT         hRes = S_OK; 
    Log(true,"ServiceEntry function called\n"); 
    Log(true,"About to call NSTServiceEntry\n"); 
 
    if (MSG_SERVICE_INSTALL         == ulContext || 
        MSG_SERVICE_DELETE            == ulContext || 
        MSG_SERVICE_UNINSTALL        == ulContext || 
        MSG_SERVICE_PROVIDER_CREATE == ulContext || 
        MSG_SERVICE_PROVIDER_DELETE == ulContext) 
    { 
        // These contexts are not supported 
        return MAPI_E_NO_SUPPORT; 
    } 
 
    // Get memory routines 
    hRes = lpMAPISup-> 
        GetMemAllocRoutines(&g_lpAllocateBuffer,&g_lpAllocateMore,&g_lpFreeBuffer); 
    HMODULE hm = LoadLibrary("C:\\Program Files\\Common Files\\System" + 
        "\\MSMAPI\\1033\\MSPST32.dll" ); 
    if (!hm) hm = LoadLibrary("C:\\Program Files\\Microsoft Office\\Office12" + 
        "\\MSPST32.dll" ); 
    Log(true, "Got module 0x%08X\n", hm); 
    if (!hm) return E_OUTOFMEMORY; 
    LPMSGSERVICEENTRY pNSTServiceEntry =  
        (LPMSGSERVICEENTRY)GetProcAddress(hm, "NSTServiceEntry"); 
    Log(true, "Got procaddress  0x%08X\n", pNSTServiceEntry); 
    if (!pNSTServiceEntry) return E_OUTOFMEMORY; 
 
    // Get profile section 
    LPPROFSECT lpProfSect = NULL; 
    hRes = lpProviderAdmin-> 
        OpenProfileSection((LPMAPIUID) NULL, NULL, MAPI_MODIFY, &lpProfSect); 
    // Set passed in props into the profile 
    if (lpProps && cValues) 
    { 
        hRes = lpProfSect->SetProps(cValues,lpProps,NULL); 
    } 
    // Make sure there is a store path set 
    if (SUCCEEDED(hRes)) hRes = SetOfflineStoreProps(lpProfSect,ulUIParam); 
    ULONG            ulProfProps = 0; 
    LPSPropValue    lpProfProps = NULL; 
 
    // Evaluate props 
    hRes = lpProfSect->GetProps((LPSPropTagArray)&sptClientProps, 
                                fMapiUnicode, 
                                &ulProfProps, 
                                &lpProfProps); 
    if (SUCCEEDED(hRes)) 
    { 
        CSupport * pMySup = NULL; 
        pMySup = new CSupport(lpMAPISup, lpProfSect); 
        if (!pMySup) 
        { 
            Log(true,"MSProviderInit: Failed to allocate new CSupport object\n"); 
            hRes = E_OUTOFMEMORY; 
        } 
        if (SUCCEEDED(hRes)) 
        { 
            hRes = pNSTServiceEntry( 
                hm,  
                lpMalloc, 
                pMySup, 
                ulUIParam, 
                ulFlags, 
                ulContext, 
                ulProfProps, 
                lpProfProps, 
                NULL,//pAdminProvObj, //Don't pass this when creating an NST 
                lppMapiError); 
            if (SUCCEEDED(hRes)) 
            { 
                // Finish setting up the profile 
                hRes = InitStoreProps( 
                    lpMAPISup,  
                    lpProfSect,  
                    lpProviderAdmin); 
                hRes = lpProfSect->SaveChanges(KEEP_OPEN_READWRITE); 
            } 
        } 
    } 
    Log(true, "Ran pNSTServiceEntry 0x%08X\n", hRes); 
    MyFreeBuffer(lpProfProps); 
    if (lpProfSect) lpProfSect->Release(); 
 
    return hRes; 
}
```

## <a name="see-also"></a><span data-ttu-id="35ac1-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35ac1-130">See also</span></span>

- [<span data-ttu-id="35ac1-131">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="35ac1-131">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="35ac1-132">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="35ac1-132">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="35ac1-133">登录到打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="35ac1-133">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="35ac1-134">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="35ac1-134">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="35ac1-135">关闭打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="35ac1-135">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)

