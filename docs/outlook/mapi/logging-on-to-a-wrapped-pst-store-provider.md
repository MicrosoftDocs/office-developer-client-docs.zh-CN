---
title: 登录到换行的 PST 存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 364bc5fd-2199-0bb2-142b-9b3b686b2268
description: 上次修改时间： 2012 年 7 月 2 日
ms.openlocfilehash: 2dfa3820d8d2ab57f278e90bef5d5a40164da6fc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776139"
---
# <a name="logging-on-to-a-wrapped-pst-store-provider"></a>登录到换行的 PST 存储提供程序

**适用于**： Outlook 
  
您可以日志上 MAPI 到换行的 PST 存储提供程序之前，您必须初始化并配置的换行的个人文件夹文件 (PST) 存储提供程序。 有关详细信息，请参阅[初始化自动换行 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)。
  
已初始化并配置换行的 PST 存储提供程序后，您必须实现两个登录例程。 **[IMSProvider::Logon](imsprovider-logon.md)** 函数登录到的换行的 PST 存储提供程序的 MAPI。 **[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)** 函数登录到的换行的 PST 存储提供程序 MAPI 后台处理程序。 
  
本主题中使用从示例自动换行 PST 存储提供程序的代码示例演示了**IMSProvider::Logon**函数和**IMSProvider::SpoolerLogon**函数。 本示例实现的换行的太平洋标准时间提供程序旨在与复制 API 结合使用。 有关下载并安装示例自动换行 PST 存储提供程序的详细信息，请参阅[安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 API 的详细信息，请参阅[有关复制 API](about-the-replication-api.md)。
  
MAPI 和 MAPI 后台处理程序都将记录后换行 PST 到存储提供程序，系统已准备好使用。 有关详细信息，请参阅[使用自动换行 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)。
  
## <a name="mapi-logon-routine"></a>MAPI 登录例程

初始化的换行的 PST 存储提供程序后，您必须实现要登录到换行的 PST 存储 MAPI 的**[IMSProvider::Logon](imsprovider-logon.md)** 函数。 此函数验证用户凭据，并获取提供程序的配置属性。 您还必须实现`SetOLFIInOST`函数设置脱机文件信息 (**[OLFI](olfi.md)** )。 **OLFI**是长期 ID 结构的换行 PST 存储提供程序用于分配新的邮件或文件夹在脱机模式下的条目 ID 的队列。 最后，该**IMSProvider::Logon**函数返回的 MAPI 后台处理程序和客户端应用程序中可以登录到的消息存储对象`ppMDB`参数。 
  
### <a name="cmsproviderlogon-example"></a>CMSProvider::Logon() 示例

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

## <a name="mapi-spooler-logon-routine"></a>MAPI 后台处理程序登录例程

类似于**IMSProvider::Logon**，您必须实现**[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)** 函数以登录到的换行的 PST 存储 MAPI 后台处理程序。 MAPI 后台处理程序和客户端应用程序可以登录到的消息存储对象返回在`ppMDB`参数。 
  
### <a name="cmsproviderspoolerlogon-example"></a>CMSProvider::SpoolerLogon() 示例

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

## <a name="see-also"></a>另请参阅

- [有关示例包装 PST 存储提供程序](about-the-sample-wrapped-pst-store-provider.md) 
- [安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md) 
- [初始化换行的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
- [使用包装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)
- [关机的情况下被环绕的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)

