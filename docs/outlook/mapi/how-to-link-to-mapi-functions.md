---
title: 链接到 MAPI 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: be72a893-a3bc-4dea-8234-47f3e1db4515
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5cb791d0d350a04864191a0a9d35a2f1c8b165d7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577714"
---
# <a name="link-to-mapi-functions"></a>链接到 MAPI 函数

**适用于**： Outlook 2013 |Outlook 2016 
  
有三种方法的链接： 隐式链接、 显式链接和使用 MAPI 存根库的新混合模型。
  
## <a name="implicit-linking"></a>隐式链接

过去，调用中的邮件应用程序始终 MAPI 函数涉及链接到 Mapi32.lib 库。 这包括 MAPI 呼叫路由至 Windows MAPI 存根库，Mapi32.dll，然后转接的呼叫在运行时的默认 MAPI 客户端实现。 此呼叫过程称为隐式链接。 下图的左侧显示 MAPI 函数呼叫过程中使用隐式链接的示例。 过程启动 MAPI 应用程序和涉及的 MAPI 库 (Mapi32.lib) 和 Windows MAPI 存根 (Mapi32.dll) 完成由 Outlook MAPI 客户端实现的 MAPI 存根 (Msmapi32.dll)。
  
**隐式和显式链接的比较。**

![隐式和显式链接的比较](media/09d9c49a-a52d-4407-9013-d0d14c8f63f6.gif "隐式和显式链接的比较")
  
## <a name="explicit-linking"></a>Explicit 链接

由于默认 MAPI 客户端支持使用 Windows Installer (MSI) 的按需安装，因此您可以开发邮件应用程序直接对 Outlook MAPI 存根而不是使用 MAPI 库和 Windows MAPI 存根。 上图中的右侧显示了 MAPI 函数调用过程，启动与 MAPI 应用程序的路径和 Outlook MAPI 存根 （步骤 2 中下一节） 的 DLL 名称查找和 Outlook MAPI 存根 （的函数调用一个的示例步骤 3 中下一节）。 下面的过程演示如何使用显式链接调用 MAPI 函数。 
  
> [!NOTE]
> 有关显式链接此信息可能多余到引入了以下节所述 MAPIStubLibrary.lib 需求。 隐式模型，如新库管理所有内容，并实现显式链接逻辑加载 Outlook 的 MAPI 直接。 
  
有关显式链接的详细信息，请参阅显式链接。
  
### <a name="to-call-mapi-api-elements-without-the-mapi-library-and-the-windows-mapi-stub"></a>若要调用不带 MAPI 库和 Windows MAPI 存根 MAPI API 元素

1. 在程序文件中，创建的每个 MAPI API 元素所使用的函数指针的全局列表。 
    
   下面的示例演示此步骤。
    
   ```cpp
    //Global MAPI function pointers
    LPMAPIINITIALIZE pfnMAPIInitialize = NULL;
    LPMAPIUNINITIALIZE pfnMAPIUninitialize = NULL;
   ```

2. 创建初始化 MAPI 函数来链接到默认 MAPI 客户端 (例如，Msmapi32.dll 的 Microsoft Outlook) 的 MAPI DLL 函数。 在此函数中，执行以下操作： 
    
    1. 从相应系统目录加载 mapi32.dll。 
        
       |||
       |:-----|:-----|
       |x64 或 x86 本身  <br/> |**%windir%\system32\mapi32.dll** <br/> |
       |x86 WoW 模式  <br/> |**%windir%\syswow64\mapi32.dll** <br/> |
    
    2. 调用[FGetComponentPath](fgetcomponentpath.md)函数可获取的路径和实现 MAPI 子系统的 DLL 名称。 有关详细信息，请参阅[选择特定版本的 MAPI 到负载](how-to-choose-a-specific-version-of-mapi-to-load.md)。
        
    3. 加载 DLL 通过调用 LoadLibrary 函数。 
        
    4. 通过调用 GetProcAddress 函数初始化 MAPI 函数指针数组。 
        
    下面的示例演示前面的步骤：
        
   ```cpp
    void InitializeMapiFunctions()
    {
    {
        // Get the DLL path and name of the actual MAPI implementation.
        FGetComponentPath(g_szMapiComponentGUID, NULL, szMAPIDLL, MAX_PATH);
        // Load the DLL.
        hMod = LoadLibrary(szMAPIDLL);
        // Initialize MAPI functions.
        pfnMAPIInitialize = GetProcAddress(hMod, "MAPIInitialize");
        pfnMAPIUninitialize = GetProcAddress(hMod, "MAPIUninitialize");
    }
   ```

3. 最后，调用函数您之前创建的步骤 2 中邮件应用程序中发出 MAPI API 元素的呼叫。 
    
   > [!CAUTION]
   > 关闭应用程序之前，必须先 MAPI 子系统取消初始化。 
  
   下面的示例演示此步骤： 
    
   ```cpp
    int main()
    {
        HRESULT hr;
        InitializeMapiFunctions();
        // Initialize the MAPI subsystem.
        hr = (*pfnMAPIInitialize)(NULL);
        if (hr!= S_OK)
        {
            // Handle the error case.
        }
        // Here is where you make calls to other MAPI interfaces.
        // Uninitialize the MAPI subsystem.
        (*pfnMAPIUninitialize)();
    return (0);
    }
   ```

## <a name="mapistublibrarylib"></a>MAPIStubLibrary.lib

Microsoft Outlook 2010 和 64 位 MAPI，现在扩展到 Microsoft Outlook 2013 一起工作的要求超过完全实现的传统 32 位 API。 新项目，MAPI 存根库，发布 CodePlex 网站上提供支持构建 32 位和 64 位的 MAPI 应用程序的 Mapi32.lib 顺便替换。 MAPIStubLibrary.lib 无需显式链接到 MAPI，并且具有构建它，您可以删除 Mapi32.lib 从链接器设置，替换 MAPIStubLibrary.lib;应不需要对代码进行任何进一步修改。 它也无需编写**LoadLibrary**和**GetProcAddress**，**句**代码来处理包含此库文件中，但不能在 Mapi32.lib，如果您使用显式链接将需要的较新导出。 
  
某些链接从此库 Mapi32.lib 中不提供的新功能包括：
  
- [GetDefCachedMode](getdefcachedmode.md)    
- [HrGetGALFromEmsmdbUID](hrgetgalfromemsmdbuid.md)   
- [HrOpenOfflineObj](hropenofflineobj.md)    
- [MAPICrashRecovery](mapicrashrecovery.md)   
- [OpenStreamOnFileW](openstreamonfilew.md)    
- [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)
    
引入 MAPI 存根库的另一种方法是直接在您的项目复制的源文件，MapiStubLibrary.cpp 和 StubUtils.cpp，并删除 Mapi32.lib 到任何链接和显式链接到 MAPI 任何代码。
  
若要访问 MAPI 存根库文件，并了解如何生成并将其集成到您的项目，以及有关此库问题如何时和为什么使用它，请参阅[MAPI 存根库](http://mapistublibrary.codeplex.com/documentation)CodePlex 网站上。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 编程概述](mapi-programming-overview.md)
- [安装 MAPI 子系统](installing-the-mapi-subsystem.md)
- [安装 MAPI 头文件](how-to-install-mapi-header-files.md)
- [选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)
- [确定要使用的链接方法](http://msdn.microsoft.com/en-us/library/253b8k2c.aspx)
- [链接到 DLL 的可执行文件](http://msdn.microsoft.com/en-us/library/9yd93633.aspx)
- [MAPI dll 设置 MSI 键](http://msdn.microsoft.com/en-us/library/ee909494%28v=VS.85%29.aspx)

