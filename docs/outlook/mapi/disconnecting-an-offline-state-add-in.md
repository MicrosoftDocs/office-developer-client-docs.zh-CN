---
title: 断开连接的脱机状态外接程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6922cb38-a9e3-e4a9-d4a3-e11b81fc77e2
description: 上次修改时间： 2015 年 12 月 7 日
ms.openlocfilehash: 82f529f58a62f412ed8b25d1ceaf508463491612
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19774788"
---
# <a name="disconnecting-an-offline-state-add-in"></a><span data-ttu-id="82f10-103">断开连接的脱机状态外接程序</span><span class="sxs-lookup"><span data-stu-id="82f10-103">Disconnecting an Offline State Add-in</span></span>

<span data-ttu-id="82f10-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="82f10-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="82f10-105">脱机状态外接程序断开连接时，您必须实现函数正确终止并清理外接程序。</span><span class="sxs-lookup"><span data-stu-id="82f10-105">When the offline state add-in is disconnected, you must implement functions to properly terminate and clean up the add-in.</span></span> <span data-ttu-id="82f10-106">有关详细信息设置和使用脱机状态外接程序来监视连接状态更改，请参阅[设置 Up 脱机状态外接程序](setting-up-an-offline-state-add-in.md)和[监视连接状态更改使用脱机状态外接程序](monitoring-connection-state-changes-using-an-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="82f10-106">For more information on setting up and using the offline state add-in to monitor connection state changes, see [Setting Up an Offline State Add-in](setting-up-an-offline-state-add-in.md) and [Monitoring Connection State Changes Using an Offline State Add-in](monitoring-connection-state-changes-using-an-offline-state-add-in.md).</span></span>
  
<span data-ttu-id="82f10-107">在此主题，这些断开连接，终止，并使用从示例脱机状态加载项的代码示例演示了清理功能。</span><span class="sxs-lookup"><span data-stu-id="82f10-107">In this topic, these disconnection, terminate, and clean-up functions are demonstrated by using code examples from the Sample Offline State Add-in.</span></span> <span data-ttu-id="82f10-108">示例脱机状态加载项是 COM 加载项程序，将**脱机状态**菜单添加到 Outlook 并使用脱机状态 API。</span><span class="sxs-lookup"><span data-stu-id="82f10-108">The Sample Offline State Add-in is a COM add-in that adds an **Offline State** menu to Outlook and uses the Offline State API.</span></span> <span data-ttu-id="82f10-109">通过脱机状态菜单中，可以启用或禁用状态监控、 检查的当前状态，并更改的当前状态。</span><span class="sxs-lookup"><span data-stu-id="82f10-109">Through the Offline State menu, you can enable or disable state monitoring, check the current state, and change the current state.</span></span> <span data-ttu-id="82f10-110">有关下载和安装加载项示例脱机状态的详细信息，请参阅[安装示例脱机状态外接程序](installing-the-sample-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="82f10-110">For more information about downloading and installing the Sample Offline State Add-in, see [Installing the Sample Offline State Add-in](installing-the-sample-offline-state-add-in.md).</span></span> <span data-ttu-id="82f10-111">有关脱机状态 API 的详细信息，请参阅[有关脱机状态 API](about-the-offline-state-api.md)。</span><span class="sxs-lookup"><span data-stu-id="82f10-111">For more information about the Offline State API, see [About the Offline State API](about-the-offline-state-api.md).</span></span>
  
## <a name="on-disconnection-routine"></a><span data-ttu-id="82f10-112">在断开连接例程</span><span class="sxs-lookup"><span data-stu-id="82f10-112">On Disconnection Routine</span></span>

<span data-ttu-id="82f10-113">脱机状态加载宏卸载时调用**IDTExtensibility2.OnDisconnection**方法。</span><span class="sxs-lookup"><span data-stu-id="82f10-113">The **IDTExtensibility2.OnDisconnection** method is called when the Offline State Add-in is unloaded.</span></span> <span data-ttu-id="82f10-114">您应实现清理此函数中的代码。</span><span class="sxs-lookup"><span data-stu-id="82f10-114">You should implement clean up code in this function.</span></span> <span data-ttu-id="82f10-115">在以下示例中， **IDTExtensibility2.OnDisconnection**函数调用`HrTermAddin`函数。</span><span class="sxs-lookup"><span data-stu-id="82f10-115">In the following example, the **IDTExtensibility2.OnDisconnection** function calls the  `HrTermAddin` function.</span></span> 
  
### <a name="cmyaddinondisconnection-example"></a><span data-ttu-id="82f10-116">CMyAddin::OnDisconnection() 示例</span><span class="sxs-lookup"><span data-stu-id="82f10-116">CMyAddin::OnDisconnection() example</span></span>

```cpp
STDMETHODIMP CMyAddin::OnDisconnection(ext_DisconnectMode /*RemoveMode*/, SAFEARRAY * * /*custom*/) 
{ 
    Log(true,"OnDisconnection\n"); 
    HRESULT hRes = S_OK; 
    hRes = HrTermAddin(); 
     return hRes; 
}
```

## <a name="terminate-add-in-function"></a><span data-ttu-id="82f10-117">终止外接程序函数</span><span class="sxs-lookup"><span data-stu-id="82f10-117">Terminate Add-in Function</span></span>

<span data-ttu-id="82f10-118">`HrTermAddin`函数调用`inDeInitMonitor`， `HrRemoveMenuItems`，和`UnloadLibraries`功能完成清理脱机状态加载项。</span><span class="sxs-lookup"><span data-stu-id="82f10-118">The  `HrTermAddin` function calls the  `inDeInitMonitor`,  `HrRemoveMenuItems`, and  `UnloadLibraries` functions to finish cleaning up the Offline State Add-in.</span></span> 
  
### <a name="cmyaddinhrtermaddin-example"></a><span data-ttu-id="82f10-119">CMyAddin::HrTermAddin() 示例</span><span class="sxs-lookup"><span data-stu-id="82f10-119">CMyAddin::HrTermAddin() example</span></span>

```cpp
HRESULT CMyAddin::HrTermAddin() 
{ 
    HRESULT hRes = S_OK; 
    DeInitMonitor(); 
    hRes =  HrRemoveMenuItems(); 
    UnloadLibraries(); 
    return hRes; 
}
```

## <a name="deinitialize-monitor-routine"></a><span data-ttu-id="82f10-120">Deinitialize 监视器例程</span><span class="sxs-lookup"><span data-stu-id="82f10-120">Deinitialize Monitor Routine</span></span>

<span data-ttu-id="82f10-121">`inDeInitMonitor`函数调用[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)函数取消脱机对象的回调。</span><span class="sxs-lookup"><span data-stu-id="82f10-121">The  `inDeInitMonitor` function calls the [IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md) function to cancel the callbacks for the offline object.</span></span> 
  
### <a name="deinitmonitor-example"></a><span data-ttu-id="82f10-122">DeInitMonitor() 示例</span><span class="sxs-lookup"><span data-stu-id="82f10-122">DeInitMonitor() example</span></span>

```cpp
void DeInitMonitor() 
{ 
Log(true,_T("Deinitializing Outlook Offline State Monitor\n")); 
HRESULT hRes = S_OK; 
if (g_lpOfflineMgr) 
{ 
hRes = g_lpOfflineMgr->Unadvise(MAPIOFFLINE_UNADVISE_DEFAULT, g_ulAdviseToken); 
g_lpOfflineMgr->Release(); 
g_lpOfflineMgr = NULL; 
g_ulAdviseToken = NULL; 
} 
}
```

## <a name="remove-menu-items-routine"></a><span data-ttu-id="82f10-123">删除菜单项例程</span><span class="sxs-lookup"><span data-stu-id="82f10-123">Remove Menu Items Routine</span></span>

<span data-ttu-id="82f10-124">`HrRemoveMenuItems`函数调用`DispEventUnadvise`为下的**脱机状态**菜单中，每个菜单项，然后删除**脱机状态**菜单。</span><span class="sxs-lookup"><span data-stu-id="82f10-124">The  `HrRemoveMenuItems` function calls  `DispEventUnadvise` for each menu item under the **Offline State** menu, and then deletes the **Offline State** menu.</span></span> 
  
### <a name="cmyaddinhrremovemenuitems-example"></a><span data-ttu-id="82f10-125">CMyAddin::HrRemoveMenuItems() 示例</span><span class="sxs-lookup"><span data-stu-id="82f10-125">CMyAddin::HrRemoveMenuItems() example</span></span>

```cpp
HRESULT CMyAddin::HrRemoveMenuItems() 
{     
    Log(true,"HrRemoveMenuItems\n"); 
    HRESULT hRes = S_OK; 
    if (m_fMenuItemsAdded) 
    { 
        try 
        { 
            if (m_spInitButton) 
            { 
                m_InitButtonHandler.DispEventUnadvise(m_spInitButton); 
            } 
            if (m_spDeinitButton) 
            { 
                m_DeinitButtonHandler.DispEventUnadvise(m_spDeinitButton); 
            } 
            if (m_spGetStateButton) 
            { 
                m_GetStateButtonHandler.DispEventUnadvise(m_spGetStateButton); 
            } 
            if (m_spSetStateButton) 
            { 
                m_SetStateButtonHandler.DispEventUnadvise(m_spSetStateButton); 
            } 
 
            m_spMyMenu->Delete(); 
        } 
        catch(_com_error) 
        { 
            hRes = E_FAIL; 
        } 
        if (SUCCEEDED(hRes)) 
        { 
            m_fMenuItemsAdded = false; 
        } 
    } 
    return hRes; 
}
```

## <a name="unload-libraries-routine"></a><span data-ttu-id="82f10-126">卸载库例程</span><span class="sxs-lookup"><span data-stu-id="82f10-126">Unload Libraries Routine</span></span>

<span data-ttu-id="82f10-127">加载宏卸载时从 Outlook 中，`UnloadLibraries`函数卸载加载项所需的动态链接库 (Dll)。</span><span class="sxs-lookup"><span data-stu-id="82f10-127">When the add-in is unloaded from Outlook, the  `UnloadLibraries` function unloads the dynamic-link libraries (DLLs) that the add-in required.</span></span> 
  
### <a name="unloadlibraries-example"></a><span data-ttu-id="82f10-128">UnloadLibraries() 示例</span><span class="sxs-lookup"><span data-stu-id="82f10-128">UnloadLibraries() example</span></span>

```cpp
void UnloadLibraries() 
{ 
    Log(true,_T("UnloadLibraries - freeing modules\n")); 
    pfnHrOpenOfflineObj = NULL; 
    pfnMAPIFreeBuffer = NULL; 
    if (hModMSMAPI) FreeLibrary(hModMSMAPI); 
    hModMSMAPI = NULL; 
    if (hModMAPI) FreeLibrary(hModMAPI); 
    hModMAPI = NULL; 
    if (hModMAPIStub) FreeLibrary(hModMAPIStub); 
    hModMAPIStub = NULL; 
}
```

## <a name="see-also"></a><span data-ttu-id="82f10-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82f10-129">See also</span></span>

- [<span data-ttu-id="82f10-130">有关脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="82f10-130">About the Offline State API</span></span>](about-the-offline-state-api.md)
- [<span data-ttu-id="82f10-131">安装示例脱机状态外接程序</span><span class="sxs-lookup"><span data-stu-id="82f10-131">Installing the Sample Offline State Add-in</span></span>](installing-the-sample-offline-state-add-in.md)
- [<span data-ttu-id="82f10-132">有关示例脱机状态外接程序</span><span class="sxs-lookup"><span data-stu-id="82f10-132">About the Sample Offline State Add-in</span></span>](about-the-sample-offline-state-add-in.md)
- [<span data-ttu-id="82f10-133">设置的脱机状态外接程序</span><span class="sxs-lookup"><span data-stu-id="82f10-133">Setting Up an Offline State Add-in</span></span>](setting-up-an-offline-state-add-in.md)
- [<span data-ttu-id="82f10-134">监控的连接状态更改使用的脱机状态外接程序</span><span class="sxs-lookup"><span data-stu-id="82f10-134">Monitoring Connection State Changes Using an Offline State Add-in</span></span>](monitoring-connection-state-changes-using-an-offline-state-add-in.md)

