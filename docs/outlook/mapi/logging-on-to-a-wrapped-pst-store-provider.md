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
# <a name="logging-on-to-a-wrapped-pst-store-provider"></a>登录包装的 PST 存储区提供程序

**适用于**：Outlook 2013 | Outlook 2016 
  
必须先初始化和配置包装的个人文件夹文件 (PST) 存储提供程序, 然后才能将 MAPI 登录到打包的 PST 存储提供程序。 有关详细信息, 请参阅[初始化打包的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)。
  
初始化和配置打包的 PST 存储区提供程序后, 必须实现两个登录例程。 **[IMSProvider:: Logon](imsprovider-logon.md)** 函数在 MAPI 上登录到打包的 PST 存储提供程序。 **[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)** 函数将 MAPI 后台处理程序登录到打包的 PST 存储提供程序。 
  
在本主题中, 通过使用示例包装的 PST 存储区提供程序中的代码示例来演示**IMSProvider:: Logon**函数和**IMSProvider:: SpoolerLogon**函数。 此示例实现了一个用于与复制 API 结合使用的打包的 PST 提供程序。 有关下载和安装示例包装的 pst 存储区提供程序的详细信息, 请参阅[安装示例包装的 pst 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)。 有关复制 api 的详细信息, 请参阅[关于复制 api](about-the-replication-api.md)。
  
mapi 和 mapi 后台处理程序登录到包装的 PST 存储提供程序后, 即可使用它。 有关详细信息, 请参阅[使用打包的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)。
  
## <a name="mapi-logon-routine"></a>MAPI 登录例程

在包装的 pst 存储区提供程序初始化之后, 您必须实现**[IMSProvider:: Logon](imsprovider-logon.md)** 函数以将 MAPI 登录到打包的 pst 存储。 此函数验证用户凭据并获取提供程序的配置属性。 您还必须实现该`SetOLFIInOST`函数以设置脱机文件信息 (**[OLFI](olfi.md)** )。 **OLFI**是长期 ID 结构的队列, 包装的 PST 存储提供程序使用这些结构为脱机模式中的新邮件或文件夹分配条目 id。 最后, **IMSProvider:: Logon**函数返回 MAPI 后台处理程序和客户端应用程序可以在`ppMDB`参数中登录到的邮件存储对象。 
  
### <a name="cmsproviderlogon-example"></a>CMSProvider:: Logon () 示例

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

类似于**IMSProvider:: Logon**, 您必须实现**[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)** 函数以将 MAPI 后台处理程序记录到包装的 PST 存储中。 MAPI 后台处理程序和客户端应用程序可以登录到的邮件存储对象在`ppMDB`参数中返回。 
  
### <a name="cmsproviderspoolerlogon-example"></a>CMSProvider:: SpoolerLogon () 示例

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

- [关于示例包装的 PST 存储区提供程序](about-the-sample-wrapped-pst-store-provider.md) 
- [安装示例包装的 PST 存储区提供程序](installing-the-sample-wrapped-pst-store-provider.md) 
- [初始化打包的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)
- [使用包装的 PST 存储区提供程序](using-a-wrapped-pst-store-provider.md)
- [关闭打包的 PST 存储区提供程序](shutting-down-a-wrapped-pst-store-provider.md)

