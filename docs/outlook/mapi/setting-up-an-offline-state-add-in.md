---
title: 设置脱机状态加载项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2a326e93-fe8c-e3a5-1e92-30b75b6cb1d2
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: fa3cee9e6b25a9bcb951fbcbfa4435890341a872
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339289"
---
# <a name="setting-up-an-offline-state-add-in"></a><span data-ttu-id="df164-103">设置脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="df164-103">Setting up an offline state add-in</span></span>

<span data-ttu-id="df164-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="df164-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="df164-105">若要实现脱机状态外接程序, 必须实现连接、初始化和其他安装函数。</span><span class="sxs-lookup"><span data-stu-id="df164-105">To implement an offline state add-in, you must implement connection, initialization, and other setup functions.</span></span> <span data-ttu-id="df164-106">在本主题中, 通过使用示例脱机状态外接程序中的代码示例来演示这些连接、初始化和安装函数。</span><span class="sxs-lookup"><span data-stu-id="df164-106">In this topic, these connection, initialization, and setup functions are demonstrated by using code examples from the Sample Offline State Add-in.</span></span> <span data-ttu-id="df164-107">示例脱机状态加载项是一个 COM 加载项，它会将**脱机状态**菜单添加到 Outlook 并使用脱机状态 API。</span><span class="sxs-lookup"><span data-stu-id="df164-107">The Sample Offline State Add-in is a COM add-in that adds an **Offline State** menu to Outlook and uses the Offline State API.</span></span> <span data-ttu-id="df164-108">通过**脱机状态**菜单, 您可以启用或禁用状态监视、检查当前状态以及更改当前状态。</span><span class="sxs-lookup"><span data-stu-id="df164-108">Through the **Offline State** menu, you can enable or disable state monitoring, check the current state, and change the current state.</span></span> <span data-ttu-id="df164-109">有关下载和安装示例脱机状态加载项的详细信息，请参阅[安装示例脱机状态加载项](installing-the-sample-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="df164-109">For more information about downloading and installing the Sample Offline State Add-in, see [Installing the Sample Offline State Add-in](installing-the-sample-offline-state-add-in.md).</span></span> <span data-ttu-id="df164-110">有关脱机状态 API 的详细信息，请参阅[关于脱机状态 API](about-the-offline-state-api.md)。</span><span class="sxs-lookup"><span data-stu-id="df164-110">For more information about the Offline State API, see [About the Offline State API](about-the-offline-state-api.md).</span></span>
  
<span data-ttu-id="df164-111">设置脱机状态外接程序后, 必须实现用于监视和修改连接状态更改的函数。</span><span class="sxs-lookup"><span data-stu-id="df164-111">After you set up an offline state add-in, you must implement functions to monitor and modify connection state changes.</span></span> <span data-ttu-id="df164-112">有关详细信息, 请参阅[使用脱机状态加载项监视连接状态更改](monitoring-connection-state-changes-using-an-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="df164-112">For more information, see [Monitoring Connection State Changes Using an Offline State Add-in](monitoring-connection-state-changes-using-an-offline-state-add-in.md).</span></span>
  
## <a name="on-connection-routine"></a><span data-ttu-id="df164-113">在连接例程上</span><span class="sxs-lookup"><span data-stu-id="df164-113">On Connection routine</span></span>

<span data-ttu-id="df164-114">每次加载外接程序时, 都会调用**[OnConnection 方法 IDTExtensibility2](https://msdn.microsoft.com/library/extensibility.idtextensibility2.onconnection%28v=VS.80%29.aspx)** 。</span><span class="sxs-lookup"><span data-stu-id="df164-114">The **[IDTExtensibility2.OnConnection Method](https://msdn.microsoft.com/library/extensibility.idtextensibility2.onconnection%28v=VS.80%29.aspx)** is called every time an add-in is loaded.</span></span> <span data-ttu-id="df164-115">它是外接程序的入口点, 因此在启动外接程序时将调用`OnConnection`您在函数中放置的代码。</span><span class="sxs-lookup"><span data-stu-id="df164-115">It is the entry point for the add-in, so the code you put in the  `OnConnection` function will be called when the add-in starts.</span></span> <span data-ttu-id="df164-116">在下面的示例中, `OnConnection`函数调用`HrInitAddin`函数。</span><span class="sxs-lookup"><span data-stu-id="df164-116">In the following example, the  `OnConnection` function calls the  `HrInitAddin` function.</span></span> 
  
### <a name="cmyaddinonconnection-example"></a><span data-ttu-id="df164-117">CMyAddin:: OnConnection () 示例</span><span class="sxs-lookup"><span data-stu-id="df164-117">CMyAddin::OnConnection() example</span></span>

```cpp
STDMETHODIMP CMyAddin::OnConnection( 
    IDispatch * Application,  
    ext_ConnectMode ConnectMode,  
    IDispatch * /*AddInInst*/,  
    SAFEARRAY * * /*custom*/) 
{ 
    Log(true,"OnConnection\n"); 
    HRESULT hRes = S_OK; 
    m_spApp = Application; 
    m_ConnectMode = ConnectMode; 
    if (ConnectMode == ext_cm_AfterStartup) 
        hRes = HrInitAddin(); 
    return hRes; 
}
```

## <a name="initialize-add-in-routine"></a><span data-ttu-id="df164-118">初始化加载项例程</span><span class="sxs-lookup"><span data-stu-id="df164-118">Initialize Add-in routine</span></span>

<span data-ttu-id="df164-119">`HrInitAddin`函数`LoadLibraries`调用、 `HrCacheProfileName`和`HrAddMenuItems`函数来完成脱机状态加载项设置。</span><span class="sxs-lookup"><span data-stu-id="df164-119">The  `HrInitAddin` function calls the  `LoadLibraries`,  `HrCacheProfileName`, and  `HrAddMenuItems` functions to finish setting up the offline state add-in.</span></span> 
  
### <a name="cmyaddinhrinitaddin-example"></a><span data-ttu-id="df164-120">CMyAddin:: HrInitAddin () 示例</span><span class="sxs-lookup"><span data-stu-id="df164-120">CMyAddin::HrInitAddin() example</span></span>

```cpp
HRESULT CMyAddin::HrInitAddin() 
{ 
    HRESULT hRes = S_OK; 
    LoadLibraries(); 
    hRes = HrCacheProfileName(); 
    Log(true,_T("HrCacheProfileName returned 0x%08X\n"),hRes); 
    hRes = HrAddMenuItems(); 
    Log(true,_T("HrAddMenuItems returned 0x%08X\n"),hRes); 
    return hRes; 
}
```

## <a name="load-libraries-routine"></a><span data-ttu-id="df164-121">加载库例程</span><span class="sxs-lookup"><span data-stu-id="df164-121">Load Libraries routine</span></span>

<span data-ttu-id="df164-122">`LoadLibraries`函数将加载外接程序所需的动态链接库 (DLL) 文件。</span><span class="sxs-lookup"><span data-stu-id="df164-122">The  `LoadLibraries` function loads the dynamic-link library (DLL) files that the add-in requires.</span></span> 
  
### <a name="loadlibraries-example"></a><span data-ttu-id="df164-123">LoadLibraries () 示例</span><span class="sxs-lookup"><span data-stu-id="df164-123">LoadLibraries() example</span></span>

```cpp
void LoadLibraries() 
{ 
    Log(true,_T("LoadLibraries - loading exports from DLLs\n"));     
    HRESULT hRes = S_OK; 
    UINT uiRet = 0; 
    LONG lRet = 0; 
    BOOL bRet = true; 
    CHAR szSystemDir[MAX_PATH+1] = {0}; 
 
    // Get the system directory path 
    // (mapistub.dll and mapi32.dll reside here) 
    uiRet = GetSystemDirectoryA(szSystemDir, MAX_PATH); 
    if (uiRet > 0) 
    { 
        CHAR szDLLPath[MAX_PATH+1] = {0}; 
        hRes = StringCchPrintfA(szDLLPath, MAX_PATH+1, "%s\\%s",  
            szSystemDir, "mapistub.dll"); 
        if (SUCCEEDED(hRes)) 
        { 
            LPFGETCOMPONENTPATH pfnFGetComponentPath = NULL; 
            // Load mapistub.dll 
            hModMAPIStub = LoadLibraryA(szDLLPath); 
            if (hModMAPIStub) 
            {    
                // Get the address of FGetComponentPath from the mapistub 
                pfnFGetComponentPath = (LPFGETCOMPONENTPATH)GetProcAddress( 
                    hModMAPIStub, "FGetComponentPath"); 
            } 
            // If there is no address for FGetComponentPath yet 
            // try getting it from mapi32.dll 
            if (!pfnFGetComponentPath) 
            { 
                hRes = StringCchPrintfA(szDLLPath, MAX_PATH+1, "%s\\%s", 
                    szSystemDir, "mapi32.dll"); 
                if (SUCCEEDED(hRes)) 
                { 
                    // Load mapi32.dll 
                    hModMAPI = LoadLibraryA(szDLLPath); 
                    if (hModMAPI) 
                    { 
                        // Get the address of FGetComponentPath from mapi32 
                        pfnFGetComponentPath = (LPFGETCOMPONENTPATH)GetProcAddress( 
                            hModMAPI, "FGetComponentPath"); 
                    } 
                } 
            } 
            if (pfnFGetComponentPath) 
            { 
                LPSTR szAppLCID = NULL; 
                LPSTR szOfficeLCID = NULL; 
                HKEY hMicrosoftOutlook = NULL; 
                lRet = RegOpenKeyEx( 
                    HKEY_LOCAL_MACHINE, 
                    _T("Software\\Clients\\Mail\\Microsoft Outlook"), 
                    NULL, 
                    KEY_READ, 
                    &hMicrosoftOutlook); 
                if (ERROR_SUCCESS == lRet && hMicrosoftOutlook) 
                { 
                    HrGetRegMultiSZValueA(hMicrosoftOutlook, "MSIApplicationLCID", (LPVOID*) &szAppLCID); 
                    HrGetRegMultiSZValueA(hMicrosoftOutlook, "MSIOfficeLCID", (LPVOID*) &szOfficeLCID); 
                } 
                if (szAppLCID) 
                { 
                    bRet = pfnFGetComponentPath( 
                        "{FF1D0740-D227-11D1-A4B0-006008AF820E}", szAppLCID, szDLLPath, MAX_PATH, true); 
                } 
                if ((!bRet || szDLLPath[0] == _T('\0')) && szOfficeLCID) 
                { 
                    bRet = pfnFGetComponentPath( 
                        "{FF1D0740-D227-11D1-A4B0-006008AF820E}", szOfficeLCID, szDLLPath, MAX_PATH, true); 
                } 
                if (!bRet || szDLLPath[0] == _T('\0')) 
                { 
                    bRet = pfnFGetComponentPath( 
                        "{FF1D0740-D227-11D1-A4B0-006008AF820E}", NULL, szDLLPath, MAX_PATH, true); 
                } 
                delete[] szOfficeLCID; 
                delete[] szAppLCID; 
                if (hMicrosoftOutlook) RegCloseKey(hMicrosoftOutlook);       
            } 
            hModMSMAPI = LoadLibrary(szDLLPath); 
            if (hModMSMAPI) 
            { 
                pfnHrOpenOfflineObj = (HROPENOFFLINEOBJ*) GetProcAddress( 
                    hModMSMAPI, 
                    "HrOpenOfflineObj@20"); 
                pfnMAPIFreeBuffer = (LPMAPIFREEBUFFER) GetProcAddress( 
                    hModMSMAPI, 
                    "MAPIFreeBuffer"); 
            } 
        } 
    }    
}
```

## <a name="cache-profile-name-routine"></a><span data-ttu-id="df164-124">缓存配置文件名称例程</span><span class="sxs-lookup"><span data-stu-id="df164-124">Cache Profile Name routine</span></span>

<span data-ttu-id="df164-125">`HrCacheProfileName`函数调用**[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)** 函数打开当前会话的 "配置文件" 部分, 然后设置按钮处理程序的配置文件。</span><span class="sxs-lookup"><span data-stu-id="df164-125">The  `HrCacheProfileName` function calls the **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** function to open a profile section for the current session, and then sets the profile for the button handlers.</span></span> 
  
### <a name="cmyaddinhrcacheprofilename-example"></a><span data-ttu-id="df164-126">CMyAddin:: HrCacheProfileName () 示例</span><span class="sxs-lookup"><span data-stu-id="df164-126">CMyAddin::HrCacheProfileName() example</span></span>

```cpp
HRESULT CMyAddin::HrCacheProfileName() 
{ 
    HRESULT hRes = S_OK;     
    _NameSpacePtr spSession = m_spApp->GetNamespace("MAPI"); 
    IUnknown* lpMAPIObject = NULL; 
    LPMAPISESSION lpMAPISession = NULL; 
    // use the raw accessor 
    hRes = spSession->get_MAPIOBJECT(&lpMAPIObject); 
    if (SUCCEEDED(hRes) && lpMAPIObject) 
    { 
        hRes = lpMAPIObject->QueryInterface(IID_IMAPISession,(LPVOID*)&lpMAPISession); 
    } 
    if (SUCCEEDED(hRes) && lpMAPISession) 
    { 
        LPPROFSECT lpPSGlobal = NULL; 
        hRes = lpMAPISession->OpenProfileSection((LPMAPIUID)pbGlobalProfileSectionGuid, NULL, 0, &lpPSGlobal); 
 
        if (SUCCEEDED(hRes) && lpPSGlobal) 
        { 
            LPSPropValue lpProfileName = NULL; 
            // Asking for PR_PROFILE_NAME_W here - this might not work with earlier versions of Outlook 
            SPropTagArray staga = {1,PR_PROFILE_NAME_W}; 
            ULONG cVal = 0; 
            hRes = lpPSGlobal->GetProps(&staga,0,&cVal,&lpProfileName); 
            if (SUCCEEDED(hRes) && 1 == cVal && lpProfileName && PR_PROFILE_NAME_W == lpProfileName->ulPropTag) 
            { 
                m_InitButtonHandler.SetProfile(lpProfileName->Value.lpszW); 
                m_GetStateButtonHandler.SetProfile(lpProfileName->Value.lpszW); 
                m_SetStateButtonHandler.SetProfile(lpProfileName->Value.lpszW); 
            } 
            if (pfnMAPIFreeBuffer) pfnMAPIFreeBuffer(lpProfileName); 
        } 
        if (lpPSGlobal) lpPSGlobal->Release(); 
    } 
    if (lpMAPISession) lpMAPISession->Release(); 
    return hRes; 
}
```

## <a name="add-menu-items-routine"></a><span data-ttu-id="df164-127">"添加菜单项" 例程</span><span class="sxs-lookup"><span data-stu-id="df164-127">Add Menu Items routine</span></span>

<span data-ttu-id="df164-128">函数定义在 "**脱机状态**" 菜单下显示的菜单选项, 该加载项在 Outlook 中加载时创建, 然后是对每个菜单项的调用`DispEventAdvise` `HrAddMenuItems`</span><span class="sxs-lookup"><span data-stu-id="df164-128">The  `HrAddMenuItems` function defines the menu options that appear under the **Offline State** menu that is created when the add-in is loaded in Outlook, and then calls  `DispEventAdvise` for each menu item.</span></span> 
  
### <a name="cmyaddinhraddmenuitems-example"></a><span data-ttu-id="df164-129">CMyAddin:: HrAddMenuItems () 示例</span><span class="sxs-lookup"><span data-stu-id="df164-129">CMyAddin::HrAddMenuItems() example</span></span>

```cpp
HRESULT CMyAddin::HrAddMenuItems() 
{ 
    Log(true,"HrAddMenuItems\n"); 
    HRESULT    hRes = S_OK; 
    if (!m_fMenuItemsAdded) 
    { 
        try 
        { 
            _ExplorerPtr spExplorer = m_spApp->ActiveExplorer(); 
            _CommandBarsPtr spCmdBars = spExplorer->__CommandBars; 
            CommandBarPtr spMainBar = spCmdBars->ActiveMenuBar; 
            CommandBarControlsPtr spMainCtrls = spMainBar->Controls; 
 
            try { m_spMyMenu = spMainCtrls->GetItem("Offline State"); } catch (_com_error) {} 
            if (m_spMyMenu == NULL) 
            {             
                m_spMyMenu = spMainCtrls->Add((long)msoControlPopup,vtMissing,vtMissing,vtMissing, true); 
                m_spMyMenu->Caption = "Offline State"; 
            } 
 
            CommandBarControlsPtr spMyMenuCtrls = m_spMyMenu->Controls; 
            try { m_spInitButton = spMyMenuCtrls->GetItem("&Init Monitor"); } catch (_com_error) {} 
            if (m_spInitButton == NULL) 
            { 
                m_spInitButton = spMyMenuCtrls->Add((long)msoControlButton, vtMissing, vtMissing, vtMissing, true); 
                m_spInitButton->Caption = "&Init Monitor"; 
                m_spInitButton->FaceId = MY_INIT_BUTTON; 
            } 
            try { m_spDeinitButton = spMyMenuCtrls->GetItem("&Deinit Monitor"); } catch (_com_error) {} 
            if (m_spDeinitButton == NULL) 
            { 
                m_spDeinitButton = spMyMenuCtrls->Add((long)msoControlButton, vtMissing, vtMissing, vtMissing, true); 
                m_spDeinitButton->Caption = "&Deinit Monitor"; 
                m_spDeinitButton->FaceId = MY_DEINIT_BUTTON; 
            } 
            try { m_spGetStateButton = spMyMenuCtrls->GetItem("&GetCurrentState"); } catch (_com_error) {} 
            if (m_spGetStateButton == NULL) 
            { 
                m_spGetStateButton = spMyMenuCtrls->Add((long)msoControlButton, vtMissing, vtMissing, vtMissing, true); 
                m_spGetStateButton->Caption = "&GetCurrentState"; 
                m_spGetStateButton->FaceId = MY_GETSTATE_BUTTON; 
            } 
            try { m_spSetStateButton = spMyMenuCtrls->GetItem("&SetCurrentState"); } catch (_com_error) {} 
            if (m_spSetStateButton == NULL) 
            { 
                m_spSetStateButton = spMyMenuCtrls->Add((long)msoControlButton, vtMissing, vtMissing, vtMissing, true); 
                m_spSetStateButton->Caption = "&SetCurrentState"; 
                m_spSetStateButton->FaceId = MY_SETSTATE_BUTTON; 
            } 
            // Set up advise 
            _com_util::CheckError(m_InitButtonHandler.DispEventAdvise(m_spInitButton)); 
            _com_util::CheckError(m_DeinitButtonHandler.DispEventAdvise(m_spDeinitButton)); 
            _com_util::CheckError(m_GetStateButtonHandler.DispEventAdvise(m_spGetStateButton)); 
            _com_util::CheckError(m_SetStateButtonHandler.DispEventAdvise(m_spSetStateButton)); 
        } 
        catch (_com_error) 
        { 
            hRes = E_FAIL; 
        } 
        if (SUCCEEDED(hRes)) 
        { 
            m_fMenuItemsAdded = true; 
        } 
    } 
    return hRes;  
}
```

## <a name="see-also"></a><span data-ttu-id="df164-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df164-130">See also</span></span>

- [<span data-ttu-id="df164-131">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="df164-131">About the Offline State API</span></span>](about-the-offline-state-api.md) 
- [<span data-ttu-id="df164-132">安装示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="df164-132">Installing the Sample Offline State Add-in</span></span>](installing-the-sample-offline-state-add-in.md)
- [<span data-ttu-id="df164-133">关于示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="df164-133">About the Sample Offline State Add-in</span></span>](about-the-sample-offline-state-add-in.md)
- [<span data-ttu-id="df164-134">使用脱机状态加载项监视连接状态更改</span><span class="sxs-lookup"><span data-stu-id="df164-134">Monitoring Connection State Changes Using an Offline State Add-in</span></span>](monitoring-connection-state-changes-using-an-offline-state-add-in.md)
- [<span data-ttu-id="df164-135">断开与脱机状态外接程序的连接</span><span class="sxs-lookup"><span data-stu-id="df164-135">Disconnecting an Offline State Add-in</span></span>](disconnecting-an-offline-state-add-in.md)

