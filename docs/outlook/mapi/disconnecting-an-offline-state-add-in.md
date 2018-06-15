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
# <a name="disconnecting-an-offline-state-add-in"></a>断开连接的脱机状态外接程序

**适用于**： Outlook 
  
脱机状态外接程序断开连接时，您必须实现函数正确终止并清理外接程序。 有关详细信息设置和使用脱机状态外接程序来监视连接状态更改，请参阅[设置 Up 脱机状态外接程序](setting-up-an-offline-state-add-in.md)和[监视连接状态更改使用脱机状态外接程序](monitoring-connection-state-changes-using-an-offline-state-add-in.md)。
  
在此主题，这些断开连接，终止，并使用从示例脱机状态加载项的代码示例演示了清理功能。 示例脱机状态加载项是 COM 加载项程序，将**脱机状态**菜单添加到 Outlook 并使用脱机状态 API。 通过脱机状态菜单中，可以启用或禁用状态监控、 检查的当前状态，并更改的当前状态。 有关下载和安装加载项示例脱机状态的详细信息，请参阅[安装示例脱机状态外接程序](installing-the-sample-offline-state-add-in.md)。 有关脱机状态 API 的详细信息，请参阅[有关脱机状态 API](about-the-offline-state-api.md)。
  
## <a name="on-disconnection-routine"></a>在断开连接例程

脱机状态加载宏卸载时调用**IDTExtensibility2.OnDisconnection**方法。 您应实现清理此函数中的代码。 在以下示例中， **IDTExtensibility2.OnDisconnection**函数调用`HrTermAddin`函数。 
  
### <a name="cmyaddinondisconnection-example"></a>CMyAddin::OnDisconnection() 示例

```cpp
STDMETHODIMP CMyAddin::OnDisconnection(ext_DisconnectMode /*RemoveMode*/, SAFEARRAY * * /*custom*/) 
{ 
    Log(true,"OnDisconnection\n"); 
    HRESULT hRes = S_OK; 
    hRes = HrTermAddin(); 
     return hRes; 
}
```

## <a name="terminate-add-in-function"></a>终止外接程序函数

`HrTermAddin`函数调用`inDeInitMonitor`， `HrRemoveMenuItems`，和`UnloadLibraries`功能完成清理脱机状态加载项。 
  
### <a name="cmyaddinhrtermaddin-example"></a>CMyAddin::HrTermAddin() 示例

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

## <a name="deinitialize-monitor-routine"></a>Deinitialize 监视器例程

`inDeInitMonitor`函数调用[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)函数取消脱机对象的回调。 
  
### <a name="deinitmonitor-example"></a>DeInitMonitor() 示例

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

## <a name="remove-menu-items-routine"></a>删除菜单项例程

`HrRemoveMenuItems`函数调用`DispEventUnadvise`为下的**脱机状态**菜单中，每个菜单项，然后删除**脱机状态**菜单。 
  
### <a name="cmyaddinhrremovemenuitems-example"></a>CMyAddin::HrRemoveMenuItems() 示例

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

## <a name="unload-libraries-routine"></a>卸载库例程

加载宏卸载时从 Outlook 中，`UnloadLibraries`函数卸载加载项所需的动态链接库 (Dll)。 
  
### <a name="unloadlibraries-example"></a>UnloadLibraries() 示例

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

## <a name="see-also"></a>另请参阅

- [有关脱机状态 API](about-the-offline-state-api.md)
- [安装示例脱机状态外接程序](installing-the-sample-offline-state-add-in.md)
- [有关示例脱机状态外接程序](about-the-sample-offline-state-add-in.md)
- [设置的脱机状态外接程序](setting-up-an-offline-state-add-in.md)
- [监控的连接状态更改使用的脱机状态外接程序](monitoring-connection-state-changes-using-an-offline-state-add-in.md)

