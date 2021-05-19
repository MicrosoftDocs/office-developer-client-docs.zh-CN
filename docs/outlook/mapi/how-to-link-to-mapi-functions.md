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
ms.openlocfilehash: 71108da8bb9914bb7ed0ad0b3adacc24e1d69e63
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346879"
---
# <a name="link-to-mapi-functions"></a>链接到 MAPI 函数

**适用于**：Outlook 2013 | Outlook 2016 
  
链接有三种方法：隐式链接、显式链接和使用 MAPI 存根库的新混合模型。
  
## <a name="implicit-linking"></a>隐式链接

过去，在邮件应用程序中调用 MAPI 函数始终涉及链接到 Mapi32.lib 库。 这包括将 MAPI 调用Windows MAPI 存根库 Mapi32.dll，然后该库会运行时将调用转发到默认的 MAPI 客户端实现。 此调用过程称为隐式链接。 下图的左侧显示了 MAPI 函数调用过程中使用的隐式链接示例。 此过程由 MAPI 应用程序启动，涉及 MAPI 库 (Mapi32.lib) 和 Windows MAPI 存根 (Mapi32.dll) ，并且由 MAPI 存根 (Msmapi32.dll) 的 Outlook MAPI 客户端实现完成。
  
**隐式链接和显式链接的比较。**

![隐式链接和显式链接的比较](media/09d9c49a-a52d-4407-9013-d0d14c8f63f6.gif "隐式链接和显式链接的比较")
  
## <a name="explicit-linking"></a>显式链接

由于默认 MAPI 客户端支持使用 Windows Installer (MSI) 按需安装，因此可以直接在 Outlook MAPI 存根上开发邮件应用程序，而不是使用 MAPI 库和 Windows MAPI 存根。 上图右侧显示了 MAPI 函数调用过程的示例，从查找 Outlook MAP (I 存根的路径和 DLL 名称的 MAPI 应用程序开始) 部分中的步骤 2，然后对 Outlook MAPI 存根 (步骤 3 进行函数调用) 。 以下过程演示如何使用显式链接调用 MAPI 函数。 
  
> [!NOTE]
> 通过引入 MAPIStubLibrary.lib（将在下一节中进行讨论）来说明显式链接的信息可能多余。 与隐式模型一样，新库管理所有内容，并实现直接加载 Outlook MAPI 的显式链接逻辑。 
  
有关显式链接详细信息，请参阅链接显式。
  
### <a name="to-call-mapi-api-elements-without-the-mapi-library-and-the-windows-mapi-stub"></a>在没有 MAPI 库和 MAPI 存根的情况下Windows MAPI API 元素

1. 在程序文件中，为使用的每个 MAPI API 元素创建函数指针的全局列表。 
    
   以下示例演示此步骤。
    
   ```cpp
    //Global MAPI function pointers
    LPMAPIINITIALIZE pfnMAPIInitialize = NULL;
    LPMAPIUNINITIALIZE pfnMAPIUninitialize = NULL;
   ```

2. 创建一个函数，用于初始化 MAPI 函数以链接到默认 MAPI 客户端的 MAPI DLL (例如，Msmapi32.dll Microsoft Outlook) 。 在此函数中，执行以下操作： 
    
    1. 从mapi32.dll目录加载数据。 
        
       |||
       |:-----|:-----|
       |x64 或 x86 本地  <br/> |**%windir%\system32\mapi32.dll** <br/> |
       |WoW 模式下的 x86  <br/> |**%windir%\syswow64\mapi32.dll** <br/> |
    
    2. 调用 [FGetComponentPath](fgetcomponentpath.md) 函数，获取实现 MAPI 子系统的路径和 DLL 名称。 有关详细信息，请参阅 Choose [a Specific Version of MAPI to Load](how-to-choose-a-specific-version-of-mapi-to-load.md)。
        
    3. 通过调用 LoadLibrary 函数加载 DLL。 
        
    4. 通过调用 GetProcAddress 函数初始化 MAPI 函数指针数组。 
        
    以下示例显示前面的步骤：
        
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

3. 最后，调用在消息应用程序的步骤 2 中创建的函数，然后再调用 MAPI API 元素。 
    
   > [!CAUTION]
   > 在关闭应用程序之前，必须取消初始化 MAPI 子系统。 
  
   以下示例演示此步骤： 
    
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

Microsoft Outlook 2010 64 位 MAPI（现在扩展到 Microsoft Outlook 2013）需要比传统的 32 位 API 更多的完整实现。 CodePlex 网站上发布的新项目 MAPI 存根库提供了 Mapi32.lib 的下拉列表替换，它支持构建 32 位和 64 位 MAPI 应用程序。 MAPIStubLibrary.lib 无需显式链接到 MAPI，生成 MAPI 后，可以从链接器设置中删除 Mapi32.lib，将其替换为 MAPIStubLibrary.lib;无需对代码进行进一步修改。 它还无需编写 LoadLibrary、GetProcAddress 和 **FreeLibrary** 代码来处理此库文件（而非 Mapi32.lib）中包含的较新的导出，如果使用显式链接，则需要此代码。   
  
从此库链接的 Mapi32.lib 中不可用的一些新函数包括：
  
- [GetDefCachedMode](getdefcachedmode.md)    
- [HrGetGALFromEmsmdbUID](hrgetgalfromemsmdbuid.md)   
- [HrOpenOfflineObj](hropenofflineobj.md)    
- [MAPICrashRecovery](mapicrashrecovery.md)   
- [OpenStreamOnFileW](openstreamonfilew.md)    
- [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)
    
合并 MAPI 存根库的替代方法是，将源文件 MapiStubLibrary.cpp 和 StubUtils.cpp 直接复制到项目中，并删除与 Mapi32.lib 的任何链接以及显式链接到 MAPI 的任何代码。
  
若要访问 MAPI 存根库文件，以及如何构建并将其集成到项目中的信息，以及有关此库的问题（如何时以及为何使用它）的信息，请参阅 CodePlex 站点上的 [MAPI 存](https://mapistublibrary.codeplex.com/documentation) 根库。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 编程概述](mapi-programming-overview.md)
- [安装 MAPI 子系统](installing-the-mapi-subsystem.md)
- [安装 MAPI 头文件](how-to-install-mapi-header-files.md)
- [选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)
- [确定要使用哪种链接方法](https://msdn.microsoft.com/library/253b8k2c.aspx)
- [将可执行文件链接到 DLL](https://msdn.microsoft.com/library/9yd93633.aspx)
- [为 MAPI DLL 设置 MSI 密钥](https://msdn.microsoft.com/library/ee909494%28v=VS.85%29.aspx)

