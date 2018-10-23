---
title: 断开脱机状态加载项
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6922cb38-a9e3-e4a9-d4a3-e11b81fc77e2
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: ce25c6777c8a71da0fe11e0bbf34eefafe2ca50d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564134"
---
# <a name="disconnecting-an-offline-state-add-in"></a>断开脱机状态加载项

**适用于**：Outlook 2013 | Outlook 2016 
  
当脱机状态加载项已断开连接时，必须实现函数来正确终止和清理加载项。 有关设置和使用脱机状态加载项监视连接状态更改的详细信息，请参阅[设置脱机状态加载项](setting-up-an-offline-state-add-in.md)和[使用脱机状态加载项监视连接状态更改](monitoring-connection-state-changes-using-an-offline-state-add-in.md)。
  
在此主题中，通过使用示例脱机状态加载项的代码示例来演示这些断开连接、终止和清理函数。 示例脱机状态加载项是一个 COM 加载项，它会将**脱机状态**菜单添加到 Outlook 并使用脱机状态 API。 通过“脱机状态”菜单，可以启用或禁用状态监视、检查当前状态和更改当前状态。 有关下载和安装示例脱机状态加载项的详细信息，请参阅[安装示例脱机状态加载项](installing-the-sample-offline-state-add-in.md)。 有关脱机状态 API 的详细信息，请参阅[关于脱机状态 API](about-the-offline-state-api.md)。
  
## <a name="on-disconnection-routine"></a>断开连接例程

卸载脱机状态加载项时调用 **IDTExtensibility2.OnDisconnection** 方法。 您应该在此函数中实现清理代码。 在以下示例中，**IDTExtensibility2.OnDisconnection** 函数调用 `HrTermAddin` 函数。 
  
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

## <a name="terminate-add-in-function"></a>终止加载项函数

`HrTermAddin` 函数调用 `inDeInitMonitor`、`HrRemoveMenuItems` 和 `UnloadLibraries` 函数以完成清理脱机状态加载项。 
  
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

## <a name="deinitialize-monitor-routine"></a>取消初始化监视例程

`inDeInitMonitor` 函数调用 [IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md) 函数以取消脱机对象的回调。 
  
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

`HrRemoveMenuItems` 函数调用**脱机状态**菜单下的每个菜单项的 `DispEventUnadvise`，然后删除**脱机状态**菜单。 
  
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

从 Outlook 卸载加载项时，`UnloadLibraries` 函数卸载该加载项必需的动态链接库 (DLL)。 
  
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

- [关于脱机状态 API](about-the-offline-state-api.md)
- [安装示例脱机状态加载项](installing-the-sample-offline-state-add-in.md)
- [关于示例脱机状态加载项](about-the-sample-offline-state-add-in.md)
- [设置脱机状态加载项](setting-up-an-offline-state-add-in.md)
- [使用脱机状态加载项监视连接状态更改](monitoring-connection-state-changes-using-an-offline-state-add-in.md)

