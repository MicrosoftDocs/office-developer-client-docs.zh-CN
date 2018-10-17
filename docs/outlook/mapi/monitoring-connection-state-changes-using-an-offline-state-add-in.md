---
title: 监控使用脱机状态加载项的连接状态更改
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: c482ddce-f2b6-222b-aa30-824b1c6f3b14
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d8385b2379f2fde8689ae2c7fc5d177af696f22e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579877"
---
# <a name="monitoring-connection-state-changes-using-an-offline-state-add-in"></a><span data-ttu-id="562fb-103">监控使用脱机状态加载项的连接状态更改</span><span class="sxs-lookup"><span data-stu-id="562fb-103">Monitoring connection state changes using an offline state add-in</span></span>

<span data-ttu-id="562fb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="562fb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="562fb-105">您可以使用脱机状态外接程序来监视连接状态更改之前，您必须实现函数来设置和初始化外接程序。</span><span class="sxs-lookup"><span data-stu-id="562fb-105">Before you can use an offline state add-in to monitor connection state changes, you must implement functions to set up and initialize the add-in.</span></span> <span data-ttu-id="562fb-106">有关详细信息，请参阅[设置 Up 脱机状态外接程序](setting-up-an-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="562fb-106">For more information, see [Setting Up an Offline State Add-in](setting-up-an-offline-state-add-in.md).</span></span>
  
<span data-ttu-id="562fb-107">设置脱机状态外接程序后，您必须使用**[HrOpenOfflineObj](hropenofflineobj.md)** 函数获取脱机对象。</span><span class="sxs-lookup"><span data-stu-id="562fb-107">After you set up the offline state add-in, you must use the **[HrOpenOfflineObj](hropenofflineobj.md)** function to obtain an offline object.</span></span> <span data-ttu-id="562fb-108">使用此脱机对象，您可以初始化状态监视器，然后获取和设置的当前状态。</span><span class="sxs-lookup"><span data-stu-id="562fb-108">Using this offline object, you can initialize your state monitor, and then get and set the current state.</span></span> 
  
<span data-ttu-id="562fb-109">本主题中，使用从示例脱机状态加载项的代码示例演示了这些状态监控函数。</span><span class="sxs-lookup"><span data-stu-id="562fb-109">In this topic, these state monitoring functions are demonstrated by using code examples from the Sample Offline State Add-in.</span></span> <span data-ttu-id="562fb-110">示例脱机状态加载项是 COM 加载项程序，将**脱机状态**菜单添加到 Outlook 并利用脱机状态 API。</span><span class="sxs-lookup"><span data-stu-id="562fb-110">The Sample Offline State Add-in is a COM add-in that adds an **Offline State** menu to Outlook and utilizes the Offline State API.</span></span> <span data-ttu-id="562fb-111">通过**脱机状态**菜单中，可以启用或禁用状态监控、 检查的当前状态，并更改的当前状态。</span><span class="sxs-lookup"><span data-stu-id="562fb-111">Through the **Offline State** menu, you can enable or disable state monitoring, check the current state, and change the current state.</span></span> <span data-ttu-id="562fb-112">有关下载和安装加载项示例脱机状态的详细信息，请参阅[安装示例脱机状态外接程序](installing-the-sample-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="562fb-112">For more information about downloading and installing the Sample Offline State Add-in, see [Installing the Sample Offline State Add-in](installing-the-sample-offline-state-add-in.md).</span></span> <span data-ttu-id="562fb-113">有关脱机状态 API 的详细信息，请参阅[有关脱机状态 API](about-the-offline-state-api.md)。</span><span class="sxs-lookup"><span data-stu-id="562fb-113">For more information about the Offline State API, see [About the Offline State API](about-the-offline-state-api.md).</span></span>
  
<span data-ttu-id="562fb-114">脱机状态外接程序断开连接时，您必须实现函数正确终止并清理外接程序。</span><span class="sxs-lookup"><span data-stu-id="562fb-114">When the offline state add-in is disconnected, you must implement functions to properly terminate and clean up the add-in.</span></span> <span data-ttu-id="562fb-115">有关详细信息，请参阅[脱机状态外接程序断开连接](disconnecting-an-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="562fb-115">For more information, see [Disconnecting an Offline State Add-in](disconnecting-an-offline-state-add-in.md).</span></span>
  
## <a name="open-offline-object-routine"></a><span data-ttu-id="562fb-116">打开脱机对象例程</span><span class="sxs-lookup"><span data-stu-id="562fb-116">Open Offline Object routine</span></span>

<span data-ttu-id="562fb-117">为客户端连接状态更改时收到通知，必须调用**[HrOpenOfflineObj](hropenofflineobj.md)** 函数。</span><span class="sxs-lookup"><span data-stu-id="562fb-117">For the client to be notified when a connection state change occurs, you must call the **[HrOpenOfflineObj](hropenofflineobj.md)** function.</span></span> <span data-ttu-id="562fb-118">此函数打开脱机支持**[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)** 的对象。</span><span class="sxs-lookup"><span data-stu-id="562fb-118">This function opens an offline object that supports **[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**.</span></span> <span data-ttu-id="562fb-119">ConnectionState.h 标头文件中定义的**HrOpenOfflineObj**函数。</span><span class="sxs-lookup"><span data-stu-id="562fb-119">The **HrOpenOfflineObj** function is defined in the ConnectionState.h header file.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="562fb-120">**HrOpenOfflineObj**函数声明 ImportProcs.h 头文件中，如下所示： `extern HROPENOFFLINEOBJ* pfnHrOpenOfflineObj;`。</span><span class="sxs-lookup"><span data-stu-id="562fb-120">The **HrOpenOfflineObj** function is declared in the ImportProcs.h header file as follows:  `extern HROPENOFFLINEOBJ* pfnHrOpenOfflineObj;`.</span></span> 
  
### <a name="hropenofflineobj-example"></a><span data-ttu-id="562fb-121">HrOpenOfflineObj 示例</span><span class="sxs-lookup"><span data-stu-id="562fb-121">HrOpenOfflineObj example</span></span>

```cpp
typedef HRESULT (STDMETHODCALLTYPE HROPENOFFLINEOBJ)( 
    ULONG ulFlags, 
    LPCWSTR pwszProfileName, 
    const GUID* pGUID, 
    const GUID* pInstance, 
    IMAPIOfflineMgr** ppOffline 
);
```

## <a name="initialize-monitor-routine"></a><span data-ttu-id="562fb-122">初始化监视器例程</span><span class="sxs-lookup"><span data-stu-id="562fb-122">Initialize Monitor routine</span></span>

<span data-ttu-id="562fb-123">`InitMonitor`函数调用**HrOpenOfflineObj**函数。</span><span class="sxs-lookup"><span data-stu-id="562fb-123">The  `InitMonitor` function calls the **HrOpenOfflineObj** function.</span></span> <span data-ttu-id="562fb-124">`InitMonitor`函数调用**CMyOfflineNotify** ，从而 Outlook 可以将回调通知发送到客户端，并注册通过**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 变量回调`AdviseInfo`。</span><span class="sxs-lookup"><span data-stu-id="562fb-124">The  `InitMonitor` function calls **CMyOfflineNotify** so that Outlook can send callback notifications to the client, and registers the callback through the **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** variable  `AdviseInfo`.</span></span>
  
### <a name="initmonitor-example"></a><span data-ttu-id="562fb-125">InitMonitor() 示例</span><span class="sxs-lookup"><span data-stu-id="562fb-125">InitMonitor() example</span></span>

```cpp
void InitMonitor(LPCWSTR szProfile) 
{ 
    if (!szProfile) return; 
    Log(true,_T("Initializing Outlook Offline State Monitor\n")); 
    HRESULT hRes = S_OK; 
 
    if (g_lpOfflineMgr) 
    { 
        Log(true,_T("Already initialized\n")); 
        return; 
    } 
     
    if (pfnHrOpenOfflineObj) 
    { 
        if (g_lpOfflineMgr) DeInitMonitor(); 
        Log(true,_T("Calling HrOpenOfflineObj for \"%ws\"\n"),szProfile); 
        hRes = pfnHrOpenOfflineObj( 
            NULL, 
            szProfile, 
            &GUID_GlobalState, 
            NULL, 
            &g_lpOfflineMgr); 
        if (FAILED(hRes))  
        { 
            Log(true,_T("HrOpenOfflineObj failed: 0x%08X\n"),hRes); 
        } 
        if (g_lpOfflineMgr) 
        { 
            IMAPIOffline* lpOffline = NULL; 
            hRes = g_lpOfflineMgr->QueryInterface(IID_IMAPIOffline,(LPVOID*)&lpOffline); 
             
            if (lpOffline) 
            { 
                ULONG ulCap = NULL; 
                hRes = lpOffline->GetCapabilities(&ulCap); 
                 
                if (ulCap & MAPIOFFLINE_CAPABILITY_OFFLINE) Log(true,_T("MAPIOFFLINE_CAPABILITY_OFFLINE supported\n")); 
                if (ulCap & MAPIOFFLINE_CAPABILITY_ONLINE) Log(true,_T("MAPIOFFLINE_CAPABILITY_ONLINE supported\n")); 
                 
                if (ulCap & (MAPIOFFLINE_CAPABILITY_OFFLINE | MAPIOFFLINE_CAPABILITY_ONLINE)) 
                { 
                    CMyOfflineNotify* lpImplNotify = new CMyOfflineNotify(); 
                     
                    if (lpImplNotify) 
                    { 
                        MAPIOFFLINE_ADVISEINFO AdviseInfo = {0}; 
                        AdviseInfo.ulSize = sizeof(MAPIOFFLINE_ADVISEINFO); 
                        AdviseInfo.ulClientToken = 0;// something you want to get handed back when you get the notification 
                        AdviseInfo.CallbackType = MAPIOFFLINE_CALLBACK_TYPE_NOTIFY; 
                        AdviseInfo.pCallback = lpImplNotify; 
                        AdviseInfo.ulAdviseTypes = MAPIOFFLINE_ADVISE_TYPE_STATECHANGE; 
                        AdviseInfo.ulStateMask = MAPIOFFLINE_STATE_ALL; 
                         
                        hRes = g_lpOfflineMgr->Advise(MAPIOFFLINE_ADVISE_DEFAULT, &AdviseInfo, &g_ulAdviseToken); 
                        Log(true,"ulAdviseToken = 0x%08X\n",g_ulAdviseToken); 
                    } 
                } 
                lpOffline->Release(); 
            }                 
        } 
    } 
}
```

## <a name="get-current-state-routine"></a><span data-ttu-id="562fb-126">获取当前状态例程</span><span class="sxs-lookup"><span data-stu-id="562fb-126">Get Current State routine</span></span>

<span data-ttu-id="562fb-127">`GetCurrentState`函数调用**HrOpenOfflineObj**函数，然后使用脱机对象获取当前连接状态。</span><span class="sxs-lookup"><span data-stu-id="562fb-127">The  `GetCurrentState` function calls the **HrOpenOfflineObj** function, and then uses the offline object to get the current connection state.</span></span> <span data-ttu-id="562fb-128">返回的当前状态`ulCurState`变量，在使用`CButtonEventHandler::Click`函数以向用户显示的当前状态。</span><span class="sxs-lookup"><span data-stu-id="562fb-128">The current state is returned in the  `ulCurState` variable, which is used in the  `CButtonEventHandler::Click` function to display the current state to the user.</span></span> 
  
### <a name="getcurrentstate-example"></a><span data-ttu-id="562fb-129">GetCurrentState() 示例</span><span class="sxs-lookup"><span data-stu-id="562fb-129">GetCurrentState() example</span></span>

```cpp
ULONG (LPCWSTR szProfile) 
{ 
    if (!szProfile) return 0; 
    Log(true,_T("Getting Current Offline State\n")); 
    HRESULT hRes = S_OK; 
    ULONG ulCurState = NULL; 
 
    if (pfnHrOpenOfflineObj) 
    { 
        if (g_lpOfflineMgr) DeInitMonitor(); 
        Log(true,_T("Calling HrOpenOfflineObj for \"%ws\"\n"),szProfile); 
        hRes = pfnHrOpenOfflineObj( 
            NULL, 
            szProfile, 
            &GUID_GlobalState, 
            NULL, 
            &g_lpOfflineMgr); 
        if (FAILED(hRes))  
        { 
            Log(true,_T("HrOpenOfflineObj failed: 0x%08X\n"),hRes); 
        } 
        if (g_lpOfflineMgr) 
        { 
            IMAPIOffline* lpOffline = NULL; 
            hRes = g_lpOfflineMgr->QueryInterface(IID_IMAPIOffline,(LPVOID*)&lpOffline); 
             
            if (lpOffline) 
            { 
                hRes = lpOffline->GetCurrentState(&ulCurState); 
                Log(true,_T("GetCurrentState returned 0x%08X\n"),hRes); 
 
                switch(ulCurState) 
                { 
                case MAPIOFFLINE_STATE_ONLINE: 
                    Log(true,_T("Current state is MAPIOFFLINE_STATE_ONLINE\n")); 
                    break; 
                case MAPIOFFLINE_STATE_OFFLINE: 
                    Log(true,_T("Current state is MAPIOFFLINE_STATE_OFFLINE\n")); 
                    break; 
                default: 
                    Log(true,_T("Current state is 0x%0X\n"),ulCurState); 
                } 
                lpOffline->Release(); 
            } 
        } 
    } 
    return ulCurState; 
}
```

## <a name="set-current-state-routine"></a><span data-ttu-id="562fb-130">设置当前状态例程</span><span class="sxs-lookup"><span data-stu-id="562fb-130">Set Current State routine</span></span>

<span data-ttu-id="562fb-131">`SetCurrentState`函数调用**HrOpenOfflineObj**函数，然后使用脱机对象设置当前连接状态。</span><span class="sxs-lookup"><span data-stu-id="562fb-131">The  `SetCurrentState` function calls the **HrOpenOfflineObj** function, and then uses the offline object to set the current connection state.</span></span> <span data-ttu-id="562fb-132">`CButtonEventHandler::Click`函数调用`SetCurrentState`函数和新状态中传递通过`ulState`变量。</span><span class="sxs-lookup"><span data-stu-id="562fb-132">The  `CButtonEventHandler::Click` function calls the  `SetCurrentState` function and the new state is passed in through the  `ulState` variable.</span></span> 
  
### <a name="setcurrentstate-example"></a><span data-ttu-id="562fb-133">SetCurrentState() 示例</span><span class="sxs-lookup"><span data-stu-id="562fb-133">SetCurrentState() example</span></span>

```cpp
HRESULT SetCurrentState(LPCWSTR szProfile, ULONG ulFlags, ULONG ulState) 
{ 
    if (!szProfile) return 0; 
    Log(true,_T("Setting Current Offline State\n")); 
    HRESULT hRes = S_OK; 
 
    if (pfnHrOpenOfflineObj) 
    { 
        if (g_lpOfflineMgr) DeInitMonitor(); 
        Log(true,_T("Calling HrOpenOfflineObj for \"%ws\"\n"),szProfile); 
        hRes = pfnHrOpenOfflineObj( 
            NULL, 
            szProfile, 
            &GUID_GlobalState, 
            NULL, 
            &g_lpOfflineMgr); 
        if (FAILED(hRes))  
        { 
            Log(true,_T("HrOpenOfflineObj failed: 0x%08X\n"),hRes); 
        } 
        if (g_lpOfflineMgr) 
        { 
            IMAPIOffline* lpOffline = NULL; 
            hRes = g_lpOfflineMgr->QueryInterface(IID_IMAPIOffline,(LPVOID*)&lpOffline); 
             
            if (lpOffline) 
            { 
                switch(ulFlags) 
                { 
                case MAPIOFFLINE_FLAG_BLOCK: 
                    Log(true,_T("Flag used: MAPIOFFLINE_FLAG_BLOCK\n")); 
                    break; 
                case MAPIOFFLINE_FLAG_DEFAULT: 
                    Log(true,_T("Flag used: MAPIOFFLINE_FLAG_DEFAULT\n")); 
                    break; 
                default: 
                    Log(true,_T("Flag used: 0x%0X\n"),ulFlags); 
                } 
                switch(ulState) 
                { 
                case MAPIOFFLINE_STATE_ONLINE: 
                    Log(true,_T("New state will be MAPIOFFLINE_STATE_ONLINE\n")); 
                    break; 
                case MAPIOFFLINE_STATE_OFFLINE: 
                    Log(true,_T("New state will be MAPIOFFLINE_STATE_OFFLINE\n")); 
                    break; 
                default: 
                    Log(true,_T("New state will be 0x%0X\n"),ulState); 
                } 
                hRes = lpOffline->SetCurrentState(ulFlags, MAPIOFFLINE_STATE_OFFLINE_MASK,ulState,NULL); 
                Log(true,_T("SetCurrentState returned 0x%08X\n"),hRes); 
                 
                lpOffline->Release(); 
            } 
        } 
    } 
    return hRes; 
}
```

## <a name="notification-routine"></a><span data-ttu-id="562fb-134">通知例程</span><span class="sxs-lookup"><span data-stu-id="562fb-134">Notification routine</span></span>

<span data-ttu-id="562fb-135">Outlook 使用**[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** 函数的连接状态发生更改时，向客户端发送通知。</span><span class="sxs-lookup"><span data-stu-id="562fb-135">The **[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** function is used by Outlook to send notifications to a client when there are changes in the connection state.</span></span> 
  
### <a name="cmyofflinenotifynotify-example"></a><span data-ttu-id="562fb-136">CMyOfflineNotify::Notify() 示例</span><span class="sxs-lookup"><span data-stu-id="562fb-136">CMyOfflineNotify::Notify() example</span></span>

```cpp
void CMyOfflineNotify::Notify(const MAPIOFFLINE_NOTIFY *pNotifyInfo) 
{ 
    Log(true,_T("CMyOfflineNotify::Notify\n")); 
    if    (pNotifyInfo == NULL) 
    {     
        Log(true,_T("pNotifyInfo is NULL\n")); 
    } 
    else 
    { 
        Log(true,_T("pNotifyInfo->ulSize == 0x%0X\n"),pNotifyInfo->ulSize); 
        switch(pNotifyInfo->NotifyType) 
        { 
            case    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE: 
                Log(true,_T("pNotifyInfo->NotifyType == MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE\n")); 
                break; 
            case    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START: 
                Log(true,_T("pNotifyInfo->NotifyType == MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START\n")); 
                break; 
            case    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE: 
                Log(true,_T("pNotifyInfo->NotifyType == MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE\n")); 
                break; 
            default: 
                Log(true,_T("pNotifyInfo->NotifyType == 0x%08X\n"),pNotifyInfo->NotifyType); 
        } 
        Log(true,_T("pNotifyInfo->ulClientToken == 0x%0X\n"),pNotifyInfo->ulClientToken); 
        switch(pNotifyInfo->Info.StateChange.ulMask) 
        { 
            case    MAPIOFFLINE_STATE_OFFLINE_MASK: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulMask == MAPIOFFLINE_STATE_OFFLINE_MASK\n")); 
                break; 
            default: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulMask == 0x%0X\n"),pNotifyInfo->Info.StateChange.ulMask); 
        } 
        switch(pNotifyInfo->Info.StateChange.ulStateOld) 
        { 
            case    MAPIOFFLINE_STATE_ONLINE: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateOld == MAPIOFFLINE_STATE_ONLINE\n")); 
                break; 
            case    MAPIOFFLINE_STATE_OFFLINE: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateOld == MAPIOFFLINE_STATE_OFFLINE\n")); 
                break; 
            default: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateOld == 0x%0X\n"),pNotifyInfo->Info.StateChange.ulStateOld); 
        } 
        switch(pNotifyInfo->Info.StateChange.ulStateNew) 
        { 
            case    MAPIOFFLINE_STATE_ONLINE: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateNew == MAPIOFFLINE_STATE_ONLINE\n")); 
                break; 
            case    MAPIOFFLINE_STATE_OFFLINE: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateNew == MAPIOFFLINE_STATE_OFFLINE\n")); 
                break; 
            default: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateNew == 0x%0X\n"),pNotifyInfo->Info.StateChange.ulStateNew); 
        } 
    } 
    return; 
}
```

## <a name="see-also"></a><span data-ttu-id="562fb-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="562fb-137">See also</span></span>

- [<span data-ttu-id="562fb-138">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="562fb-138">About the Offline State API</span></span>](about-the-offline-state-api.md)
- [<span data-ttu-id="562fb-139">安装示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="562fb-139">Installing the Sample Offline State Add-in</span></span>](installing-the-sample-offline-state-add-in.md)
- [<span data-ttu-id="562fb-140">关于示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="562fb-140">About the Sample Offline State Add-in</span></span>](about-the-sample-offline-state-add-in.md)
- [<span data-ttu-id="562fb-141">设置脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="562fb-141">Setting Up an Offline State Add-in</span></span>](setting-up-an-offline-state-add-in.md)
- [<span data-ttu-id="562fb-142">断开脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="562fb-142">Disconnecting an Offline State Add-in</span></span>](disconnecting-an-offline-state-add-in.md)
