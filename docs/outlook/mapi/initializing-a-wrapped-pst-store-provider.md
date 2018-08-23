---
title: 初始化换行的 PST 存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 07633717-ba4c-b146-ad65-60b37ab98ab6
description: 上次修改时间： 2012 年 10 月 5 日
ms.openlocfilehash: c39f66917ecc080785b3a3e91506d3994427ca62
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569076"
---
# <a name="initializing-a-wrapped-pst-store-provider"></a><span data-ttu-id="20c23-103">初始化换行的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="20c23-103">Initializing a wrapped PST store provider</span></span>

<span data-ttu-id="20c23-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20c23-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20c23-105">若要实现包装的个人文件夹文件 (PST) 存储提供程序，必须使用作为入口点**[MSProviderInit](msproviderinit.md)** 函数初始化的换行的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="20c23-105">To implement a wrapped Personal Folders file (PST) store provider, you must initialize the wrapped PST store provider by using the **[MSProviderInit](msproviderinit.md)** function as an entry point.</span></span> <span data-ttu-id="20c23-106">初始化提供程序的 DLL 之后， **[MSGSERVICEENTRY](msgserviceentry.md)** 函数将配置的换行的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="20c23-106">After the provider's DLL is initialized, the **[MSGSERVICEENTRY](msgserviceentry.md)** function configures the wrapped PST store provider.</span></span> 
  
<span data-ttu-id="20c23-107">本主题中使用从示例自动换行 PST 存储提供程序的代码示例演示了**MSProviderInit**函数和**MSGSERVICEENTRY**函数。</span><span class="sxs-lookup"><span data-stu-id="20c23-107">In this topic, the **MSProviderInit** function and the **MSGSERVICEENTRY** function are demonstrated by using code examples from the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="20c23-108">本示例实现的换行的太平洋标准时间提供程序旨在与复制 API 结合使用。</span><span class="sxs-lookup"><span data-stu-id="20c23-108">The sample implements a wrapped PST provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="20c23-109">有关下载并安装示例自动换行 PST 存储提供程序的详细信息，请参阅[安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="20c23-109">For more information about downloading and installing the Sample Wrapped PST Store Provider, see [Installing the Sample Wrapped PST Store Provider](installing-the-sample-wrapped-pst-store-provider.md).</span></span> <span data-ttu-id="20c23-110">有关复制 API 的详细信息，请参阅[有关复制 API](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="20c23-110">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
<span data-ttu-id="20c23-111">初始化换行的 PST 存储提供程序后，您必须实现函数，以便可以登录的消息存储提供程序的 MAPI 和 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="20c23-111">After you have initialized a wrapped PST store provider, you must implement functions so that MAPI and the MAPI spooler can log onto the message store provider.</span></span> <span data-ttu-id="20c23-112">有关详细信息，请参阅[日志记录在到自动换行 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="20c23-112">For more information, see [Logging On to a Wrapped PST Store Provider](logging-on-to-a-wrapped-pst-store-provider.md).</span></span>
  
## <a name="initialization-routine"></a><span data-ttu-id="20c23-113">初始化例程</span><span class="sxs-lookup"><span data-stu-id="20c23-113">Initialization routine</span></span>

<span data-ttu-id="20c23-114">所有换行的 PST 存储提供程序必须实现**[MSProviderInit](msproviderinit.md)** 函数作为初始化提供程序的 DLL 入口点。</span><span class="sxs-lookup"><span data-stu-id="20c23-114">All wrapped PST store providers must implement the **[MSProviderInit](msproviderinit.md)** function as an entry point to initialize the provider's DLL.</span></span> <span data-ttu-id="20c23-115">**MSProviderInit**检查是否为服务提供程序接口的版本号`ulMAPIVer`，与当前版本号，兼容`CURRENT_SPI_VERSION`。</span><span class="sxs-lookup"><span data-stu-id="20c23-115">**MSProviderInit** checks to see if the version number of the service provider interface,  `ulMAPIVer`, is compatible with the current version number,  `CURRENT_SPI_VERSION`.</span></span> <span data-ttu-id="20c23-116">该函数将保存的 MAPI 内存管理例程到`g_lpAllocateBuffer`， `g_lpAllocateMore`，和`g_lpFreeBuffer`参数。</span><span class="sxs-lookup"><span data-stu-id="20c23-116">The function saves the MAPI memory management routines into the  `g_lpAllocateBuffer`,  `g_lpAllocateMore`, and  `g_lpFreeBuffer` parameters.</span></span> <span data-ttu-id="20c23-117">这些内存管理例程应用于整个换行 PST 存储实现内存分配和释放。</span><span class="sxs-lookup"><span data-stu-id="20c23-117">These memory management routines should be used throughout the wrapped PST store implementation for memory allocation and deallocation.</span></span> 
  
### <a name="msproviderinit-example"></a><span data-ttu-id="20c23-118">MSProviderInit() 示例</span><span class="sxs-lookup"><span data-stu-id="20c23-118">MSProviderInit() example</span></span>

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

### <a name="wrapped-pst-and-unicode-paths"></a><span data-ttu-id="20c23-119">换行的 PST 和 Unicode 路径</span><span class="sxs-lookup"><span data-stu-id="20c23-119">Wrapped PST and Unicode paths</span></span>

<span data-ttu-id="20c23-120">英语原始的示例在 Microsoft Visual Studio 2008 中准备使用 Unicode 路径 NST 在启用 Unicode 的 Microsoft Outlook 2010 和 Outlook 2013 中使用， **CreateStoreEntryID**例程，它将生成的条目标识符，应使用ASCII 路径和另一个用于 Unicode 路径的一种格式。</span><span class="sxs-lookup"><span data-stu-id="20c23-120">To retrofit the original sample prepared in Microsoft Visual Studio 2008 to use Unicode paths to the NST for use in Unicode-enabled Microsoft Outlook 2010 and Outlook 2013, the **CreateStoreEntryID** routine, which produces the entry identifier, should use one format for ASCII paths, and another for Unicode paths.</span></span> <span data-ttu-id="20c23-121">这些都表示为下面的示例中的结构。</span><span class="sxs-lookup"><span data-stu-id="20c23-121">These are represented as structures in the following example.</span></span> 
  
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
> <span data-ttu-id="20c23-122">在这些结构中的差异是之前的 Unicode 路径的两个 NULL 字节。</span><span class="sxs-lookup"><span data-stu-id="20c23-122">The differences in these structures are two NULL bytes prior to a Unicode path.</span></span> <span data-ttu-id="20c23-123">如果您需要解释中"服务条目例行"后面的项标识符，请将是一种方法来确定的是否是这种情况来强制转换为 EIDMS 首先，然后检查 szPath [0] 是否为 NULL。</span><span class="sxs-lookup"><span data-stu-id="20c23-123">If you need to interpret the entry identifier in the "Service Entry Routine" that follows, one way to determine whether that is the case or not would be to cast as EIDMS first, then check whether the szPath[0] is NULL.</span></span> <span data-ttu-id="20c23-124">如果是，将其转换 EIDMSW。</span><span class="sxs-lookup"><span data-stu-id="20c23-124">If it is, cast it as EIDMSW instead.</span></span> 
  
## <a name="service-entry-routine"></a><span data-ttu-id="20c23-125">服务项例程</span><span class="sxs-lookup"><span data-stu-id="20c23-125">Service Entry routine</span></span>

<span data-ttu-id="20c23-126">**[MSGSERVICEENTRY](msgserviceentry.md)** 函数是包装的 PST 存储提供程序的配置位置的消息服务入口点。</span><span class="sxs-lookup"><span data-stu-id="20c23-126">The **[MSGSERVICEENTRY](msgserviceentry.md)** function is the message service entry point where the wrapped PST store provider is configured.</span></span> <span data-ttu-id="20c23-127">函数调用`GetMemAllocRoutines()`以获取 MAPI 内存管理例程。</span><span class="sxs-lookup"><span data-stu-id="20c23-127">The function calls  `GetMemAllocRoutines()` to get the MAPI memory management routines.</span></span> <span data-ttu-id="20c23-128">该函数使用`lpProviderAdmin`参数来配置文件中找到的提供程序和设置的属性的配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="20c23-128">The function uses the  `lpProviderAdmin` parameter to locate the profile section for the provider and sets the properties in the profile.</span></span> 
  
### <a name="serviceentry-example"></a><span data-ttu-id="20c23-129">ServiceEntry() 示例</span><span class="sxs-lookup"><span data-stu-id="20c23-129">ServiceEntry() example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="20c23-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20c23-130">See also</span></span>

- [<span data-ttu-id="20c23-131">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="20c23-131">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="20c23-132">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="20c23-132">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
- [<span data-ttu-id="20c23-133">登录包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="20c23-133">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="20c23-134">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="20c23-134">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
- [<span data-ttu-id="20c23-135">关闭包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="20c23-135">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)

