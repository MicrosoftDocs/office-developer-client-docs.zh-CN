---
title: 获取默认邮件客户端的特定 MAPI 版本的路径
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5ee7fb05-cfb3-6b68-5a9a-1d6375f2e879
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1992e34a684a6b5894963eae0c299b21c064578c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346457"
---
# <a name="get-the-path-of-a-specific-version-of-mapi-for-the-default-mail-client"></a><span data-ttu-id="1cfef-103">获取默认邮件客户端的特定 MAPI 版本的路径</span><span class="sxs-lookup"><span data-stu-id="1cfef-103">Get the path of a specific version of MAPI for the default mail client</span></span>

<span data-ttu-id="1cfef-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1cfef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1cfef-105">本主题包含 c + + 中的代码示例, 说明如何获取计算机上默认邮件客户端使用的特定 MAPI 版本的路径。</span><span class="sxs-lookup"><span data-stu-id="1cfef-105">This topic includes a code sample in C++ that shows how to obtain the path of a specific version of MAPI that is used by the default mail client on a computer.</span></span> <span data-ttu-id="1cfef-106">mapi 邮件客户端具有一个选项, 可用于在注册表中指定 mapi 存根库应将 mapi 调用加载并将其发送到的自定义 DLL。</span><span class="sxs-lookup"><span data-stu-id="1cfef-106">MAPI mail clients have an option to specify in the registry a custom DLL that the MAPI stub library should load and dispatch MAPI calls to.</span></span> <span data-ttu-id="1cfef-107">为默认邮件客户端的此自定义 DLL 设置的注册表项是**MSIComponentID**, 在默认邮件客户端的**HKLM\Software\Clients\Mail**项下。</span><span class="sxs-lookup"><span data-stu-id="1cfef-107">The registry key to set for this custom DLL for a default mail client is **MSIComponentID**, under the **HKLM\Software\Clients\Mail** key of the default mail client.</span></span> <span data-ttu-id="1cfef-108">由 mapi 存根库 mapistub 导出的[FGetComponentPath](fgetcomponentpath.md)函数可以返回由**MSIComponentID**注册表项指定的自定义版本的 mapi 的路径。</span><span class="sxs-lookup"><span data-stu-id="1cfef-108">The [FGetComponentPath](fgetcomponentpath.md) function, exported by the MAPI stub library, mapistub.dll, can return the path to the custom version of MAPI specified by the **MSIComponentID** registry key.</span></span> 
  
<span data-ttu-id="1cfef-109">此代码示例包括两个函数`HrGetRegMultiSZValueA` : `GetMAPISVCPath`和。</span><span class="sxs-lookup"><span data-stu-id="1cfef-109">This code sample includes two functions:  `HrGetRegMultiSZValueA` and  `GetMAPISVCPath`.</span></span> <span data-ttu-id="1cfef-110">`GetMAPISVCPath`函数使用[FGetComponentPath](fgetcomponentpath.md)获取自定义版本的 MAPI 的路径。</span><span class="sxs-lookup"><span data-stu-id="1cfef-110">The  `GetMAPISVCPath` function uses [FGetComponentPath](fgetcomponentpath.md) to obtain the path to the custom version of MAPI.</span></span> <span data-ttu-id="1cfef-111">它假定默认邮件客户端为 Microsoft Office Outlook 2007, 并传递到**FGetComponentPath**的值`{FF1D0740-D227-11D1-A4B0-006008AF820E}`, 即 Outlook 2007 设置为**MSIComponentID**注册表项的 MAPI 的组件 ID。</span><span class="sxs-lookup"><span data-stu-id="1cfef-111">It assumes that the default mail client is Microsoft Office Outlook 2007, and passes to **FGetComponentPath** the value,  `{FF1D0740-D227-11D1-A4B0-006008AF820E}`, that Outlook 2007 sets as the component ID of MAPI for the **MSIComponentID** registry key.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1cfef-112">实际上, 您不应假定值是 MAPI 的`{FF1D0740-D227-11D1-A4B0-006008AF820E}`组件 ID, 而是直接将其传递给**FGetComponentPath**。</span><span class="sxs-lookup"><span data-stu-id="1cfef-112">In practice, you should not assume the value,  `{FF1D0740-D227-11D1-A4B0-006008AF820E}`, is always the component ID of MAPI and directly pass it to **FGetComponentPath**.</span></span> <span data-ttu-id="1cfef-113">若要可靠地了解计算机上使用的 MAPI Outlook 的版本, 您必须从注册表中读取**MSIComponentID**的值, 并将其传递给**FGetComponentPath**。</span><span class="sxs-lookup"><span data-stu-id="1cfef-113">To reliably find out which version of MAPI Outlook uses on a computer, you must read from the registry the value of **MSIComponentID** and pass it to **FGetComponentPath**.</span></span> 
  
<span data-ttu-id="1cfef-114">下面的步骤介绍了`GetMAPISVCPath`如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1cfef-114">The following steps describe how  `GetMAPISVCPath` does this.</span></span> 
  
1. <span data-ttu-id="1cfef-115">从系统目录中加载 MAPI 存根库 mapistub。</span><span class="sxs-lookup"><span data-stu-id="1cfef-115">Loads the MAPI stub library, mapistub.dll, from the system directory.</span></span>
    
2. <span data-ttu-id="1cfef-116">假定 mapistub 导出**FGetComponentPath**函数, 它会尝试从 mapistub 获取此函数的地址。</span><span class="sxs-lookup"><span data-stu-id="1cfef-116">Assumes that mapistub.dll exports the **FGetComponentPath** function, it tries to get the address of this function from mapistub.dll.</span></span> 
    
3. <span data-ttu-id="1cfef-117">如果从 mapistub 获取地址失败, 它将尝试从 mapi32 获取地址。</span><span class="sxs-lookup"><span data-stu-id="1cfef-117">If getting the address from mapistub.dll fails, it tries to get the address from mapi32.dll.</span></span>
    
4. <span data-ttu-id="1cfef-118">如果获取**FGetComponentPath**的地址成功, 它将打开注册表并使用`HrGetRegMultiSZValueA`函数读取**HKLM\Software\Clients\Mail\Microsoft Outlook**下的注册表值。</span><span class="sxs-lookup"><span data-stu-id="1cfef-118">If getting the address of **FGetComponentPath** succeeds, it opens the registry and uses the  `HrGetRegMultiSZValueA` function to read the registry values under **HKLM\Software\Clients\Mail\Microsoft Outlook**.</span></span> 
    
5. <span data-ttu-id="1cfef-119">调用**FGetComponentPath**, 并指定值`{FF1D0740-D227-11D1-A4B0-006008AF820E}`, 以获取 Outlook 2007 使用的 MAPI 版本的路径。</span><span class="sxs-lookup"><span data-stu-id="1cfef-119">Calls **FGetComponentPath**, specifying the value,  `{FF1D0740-D227-11D1-A4B0-006008AF820E}`, to obtain the path to the version of MAPI that Outlook 2007 uses.</span></span>
    
<span data-ttu-id="1cfef-120">请注意, 若要支持针对英语和非英语区域设置的 MAPI 的本地化副本, 该代码示例将读取**MSIApplicationLCID**和**MSIOfficeLCID**子项的值并调用**FGetComponentPath**, 首先指定**MSIApplicationLCID**作为*szQualifier* , 然后再次将**MSIOfficeLCID**指定为*szQualifier* 。</span><span class="sxs-lookup"><span data-stu-id="1cfef-120">Note that to support localized copies of MAPI for English and non-English locales, the code sample reads the values for the **MSIApplicationLCID** and **MSIOfficeLCID** subkeys and calls **FGetComponentPath**, first specifying **MSIApplicationLCID** as  *szQualifier*  , and then again specifying **MSIOfficeLCID** as  *szQualifier*  .</span></span> <span data-ttu-id="1cfef-121">有关支持非英语语言的邮件客户端的注册表项的详细信息, 请参阅[设置 MAPI DLL 的 MSI 密钥](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1cfef-121">For more information about registry keys for mail clients that support non-English languages, see [Setting Up the MSI Keys for Your MAPI DLL](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx).</span></span>
  
```cpp
// HrGetRegMultiSZValueA 
// Get a REG_MULTI_SZ registry value - allocating memory using new to hold it. 
void HrGetRegMultiSZValueA( 
    IN HKEY hKey, // the key. 
    IN LPCSTR lpszValue, // value name in key. 
    OUT LPVOID* lppData) // where to put the data. 
{ 
    *lppData = NULL; 
    DWORD dwKeyType = NULL;       
    DWORD cb = NULL; 
    LONG lRet = 0; 
    
    // Get its size 
    lRet = RegQueryValueExA( 
        hKey, 
        lpszValue, 
        NULL, 
        &amp;dwKeyType, 
        NULL, 
        &amp;cb); 
 
    if (ERROR_SUCCESS == lRet &amp;&amp; cb &amp;&amp; REG_MULTI_SZ == dwKeyType) 
    { 
        *lppData = new BYTE[cb]; 
       
        if (*lppData) 
        { 
            // Get the current value 
            lRet = RegQueryValueExA( 
                hKey,  
                lpszValue,  
                NULL,  
                &amp;dwKeyType,  
                (unsigned char*)*lppData,  
                &amp;cb); 
          
            if (ERROR_SUCCESS != lRet) 
            { 
                delete[] *lppData; 
                *lppData = NULL; 
            } 
        } 
    } 
} 
 
typedef BOOL (STDAPICALLTYPE FGETCOMPONENTPATH) ( 
    LPSTR szComponent, 
    LPSTR szQualifier, 
    LPSTR szDllPath, 
    DWORD cchBufferSize, 
    BOOL fInstall); 
typedef FGETCOMPONENTPATH FAR * LPFGETCOMPONENTPATH;  
 
/////////////////////////////////////////////////////////////////////////////// 
// Function name   : GetMAPISVCPath 
// Description       : This will get the correct path to the MAPISVC.INF file. 
// Return type      : void  
// Argument         : LPSTR szMAPIDir - Buffer to hold the path to the MAPISVC file. 
//                    ULONG cchMAPIDir - size of the buffer 
void GetMAPISVCPath(LPSTR szMAPIDir, ULONG cchMAPIDir) 
{ 
    HRESULT hRes = S_OK; 
    UINT uiRet = 0; 
    LONG lRet = 0; 
    BOOL bRet = true; 
    
    szMAPIDir[0] = &apos;\0&apos;; // Terminate string at position 0, safer if fail below 
    
    CHAR szSystemDir[MAX_PATH+1] = {0}; 
    
    // Get the system directory path 
    // (mapistub.dll and mapi32.dll reside here) 
    uiRet = GetSystemDirectoryA(szSystemDir, MAX_PATH); 
    if (uiRet &gt; 0) 
    { 
        CHAR szDLLPath[MAX_PATH+1] = {0}; 
       
        hRes = StringCchPrintfA(szDLLPath, MAX_PATH+1, &quot;%s\\%s&quot;,  
            szSystemDir, &quot;mapistub.dll&quot;); 
        if (SUCCEEDED(hRes)) 
        { 
            LPFGETCOMPONENTPATH pfnFGetComponentPath = NULL; 
          
            HMODULE hmodStub = 0; 
            HMODULE hmodMapi32 = 0; 
          
            // Load mapistub.dll 
            hmodStub = LoadLibraryA(szDLLPath); 
            if (hmodStub) 
            {    
                // Get the address of FGetComponentPath from the mapistub 
                pfnFGetComponentPath = (LPFGETCOMPONENTPATH)GetProcAddress( 
                    hmodStub, &quot;FGetComponentPath&quot;); 
            } 
          
            // If failed to get the address of FGetComponentPath, 
            // try mapi32.dll 
            if (!pfnFGetComponentPath) 
            { 
                hRes = StringCchPrintfA(szDLLPath, MAX_PATH+1, &quot;%s\\%s&quot;, 
                    szSystemDir, &quot;mapi32.dll&quot;); 
                if (SUCCEEDED(hRes)) 
                { 
                    // Load mapi32.dll 
                    hmodMapi32 = LoadLibraryA(szDLLPath); 
                    if (hmodMapi32) 
                    { 
                        // Get the address of FGetComponentPath from mapi32 
                        pfnFGetComponentPath = (LPFGETCOMPONENTPATH)GetProcAddress( 
                            hmodMapi32, &quot;FGetComponentPath&quot;); 
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
                    _T(&quot;Software\\Clients\\Mail\\Microsoft Outlook&quot;), 
                    NULL, 
                    KEY_READ, 
                    &amp;hMicrosoftOutlook); 
             
                if (ERROR_SUCCESS == lRet &amp;&amp; hMicrosoftOutlook) 
                { 
                    HrGetRegMultiSZValueA(hMicrosoftOutlook, &quot;MSIApplicationLCID&quot;, (LPVOID*) &amp;szAppLCID); 
                    HrGetRegMultiSZValueA(hMicrosoftOutlook, &quot;MSIOfficeLCID&quot;, (LPVOID*) &amp;szOfficeLCID); 
                } 
             
                // Only passing a fixed value as the component ID for MAPI in this example 
                // In practice, must read from the registry the value of MSIComponentID 
                if (szAppLCID) 
                { 
                    bRet = pfnFGetComponentPath( 
                        &quot;{FF1D0740-D227-11D1-A4B0-006008AF820E}&quot;, szAppLCID, szMAPIDir, cchMAPIDir, true); 
                } 
                if ((!bRet || szMAPIDir[0] == _T(&apos;\0&apos;)) &amp;&amp; szOfficeLCID) 
                { 
                    bRet = pfnFGetComponentPath( 
                    &quot;{FF1D0740-D227-11D1-A4B0-006008AF820E}&quot;, szOfficeLCID, szMAPIDir, cchMAPIDir, true); 
                } 
                if (!bRet || szMAPIDir[0] == _T(&apos;\0&apos;)) 
                { 
                    bRet = pfnFGetComponentPath( 
                        &quot;{FF1D0740-D227-11D1-A4B0-006008AF820E}&quot;, NULL, szMAPIDir, cchMAPIDir, true); 
                } 
             
                // Got the path to msmapi32.dll - need to strip it 
                if (bRet &amp;&amp; szMAPIDir[0] != _T(&apos;\0&apos;)) 
                { 
                    LPSTR lpszSlash = NULL; 
                    LPSTR lpszCur = szMAPIDir; 
                
                    for (lpszSlash = lpszCur; *lpszCur; lpszCur = lpszCur++) 
                    { 
                        if (*lpszCur == _T(&apos;\\&apos;)) lpszSlash = lpszCur; 
                    } 
                   *lpszSlash = _T(&apos;\0&apos;); 
                } 
 
                delete[] szOfficeLCID; 
                delete[] szAppLCID; 
                if (hMicrosoftOutlook) RegCloseKey(hMicrosoftOutlook);       
            } 
             
            // If FGetComponentPath returns FALSE or if 
            // it returned nothing, or if failed to find an 
            // address of FGetComponentPath, then 
            // just default to the system directory 
            if (!bRet || szMAPIDir[0] == &apos;\0&apos;) 
            { 
                hRes = StringCchPrintfA( 
                    szMAPIDir, cchMAPIDir,&quot;%s&quot;, szSystemDir); 
            } 
          
            if (szMAPIDir[0] != _T(&apos;\0&apos;)) 
            { 
                hRes = StringCchPrintfA( 
                    szMAPIDir, cchMAPIDir, &quot;%s\\%s&quot;, szMAPIDir, &quot;MAPISVC.INF&quot;); 
            } 
          
            if (hmodMapi32) FreeLibrary(hmodMapi32); 
            if (hmodStub) FreeLibrary(hmodStub); 
        } 
    }    
}

```


