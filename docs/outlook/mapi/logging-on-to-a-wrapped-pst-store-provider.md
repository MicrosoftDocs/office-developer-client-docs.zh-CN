---
title: 登录包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 364bc5fd-2199-0bb2-142b-9b3b686b2268
description: 上次修改时间：2012 年 7 月 2 日
ms.openlocfilehash: 96f472d67f144a451046ff61a3ed6c6ff2ff9acf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408984"
---
# <a name="logging-on-to-a-wrapped-pst-store-provider"></a>登录包装的 PST 存储区提供程序

**适用于**：Outlook 2013 | Outlook 2016 
  
在可以登录到包装的 PST 存储提供程序的 MAPI 之前，您必须初始化和配置包装的个人文件夹文件 (PST) 存储提供程序。 有关详细信息，请参阅初始化 [封装的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)。
  
初始化并配置包装的 PST 存储提供程序后，必须实现两个登录例程。 **[IMSProvider：：Logon](imsprovider-logon.md)** 函数将 MAPI 记录到包装的 PST 存储提供程序。 **[IMSProvider：：SpoolerLogon](imsprovider-spoolerlogon.md)** 函数将 MAPI 后台处理程序记录到包装的 PST 存储提供程序。 
  
在本主题中，使用示例包装 PST 存储提供程序中的代码示例演示 **IMSProvider：：Logon** 函数和 **IMSProvider：：SpoolerLogon** 函数。 该示例实现一个包装的 PST 提供程序，旨在与复制 API 结合使用。 有关下载和安装包装的示例 PST 存储提供程序详细信息，请参阅安装包装的 PST 存储 [提供程序示例](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 API 的信息，请参阅[关于复制 API。](about-the-replication-api.md)
  
MAPI 和 MAPI 后台处理程序登录到包装的 PST 存储提供程序后，即可使用。 有关详细信息，请参阅 [使用封装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)。
  
## <a name="mapi-logon-routine"></a>MAPI 登录例程

初始化包装的 PST 存储提供程序后，您必须实现 **[IMSProvider：：Logon](imsprovider-logon.md)** 函数以登录到包装的 PST 存储的 MAPI。 此函数验证用户凭据并获取提供程序的配置属性。 还必须实现 函数  `SetOLFIInOST` ，以设置 **[OLFI](olfi.md)** (脱机) 。 **OLFI** 是一个长期 ID 结构的队列，包装的 PST 存储提供程序使用该队列在脱机模式下分配新邮件或文件夹的条目 ID。 最后 **，IMSProvider：：Logon** 函数返回 MAPI 后台处理程序和客户端应用程序可以在 参数中登录的消息存储  `ppMDB` 对象。 
  
### <a name="cmsproviderlogon-example"></a>CMSProvider：：Logon () 示例

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

与 **IMSProvider：：Logon** 类似，您必须实现 **[IMSProvider：：SpoolerLogon](imsprovider-spoolerlogon.md)** 函数以将 MAPI 后台处理程序记录到包装的 PST 存储。 参数中返回 MAPI 后台处理程序和客户端应用程序可登录的邮件存储  `ppMDB` 对象。 
  
### <a name="cmsproviderspoolerlogon-example"></a>CMSProvider：：SpoolerLogon () 示例

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

- [关于包装的 PST 存储提供程序示例](about-the-sample-wrapped-pst-store-provider.md) 
- [安装包装的 PST 存储提供程序示例](installing-the-sample-wrapped-pst-store-provider.md) 
- [初始化包装的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
- [使用包装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)
- [关闭包装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)

