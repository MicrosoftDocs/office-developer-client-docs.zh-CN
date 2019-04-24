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
  
有三种链接方式: 隐式链接、显式链接和使用 MAPI 存根库的新混合模型。
  
## <a name="implicit-linking"></a>隐式链接

以前, 在邮件应用程序中调用 MAPI 函数始终会链接到 Mapi32 库。 这包括将 MAPI 调用传递给 Windows MAPI 存根库, Mapi32, 然后在运行时将调用转发到默认的 MAPI 客户端实现。 此呼叫过程称为隐式链接。 下图的左侧显示了 MAPI 函数调用过程中使用的隐式链接的示例。 此过程由 mapi 应用程序启动, 并涉及 mapi 库 (Mapi32) 和 Windows mapi 存根 (Mapi32), 并由 mapi 存根 (Msmapi32) 的 Outlook MAPI 客户端实现完成。
  
**隐式链接和显式链接的比较。**

![隐式链接和显式链接的比较](media/09d9c49a-a52d-4407-9013-d0d14c8f63f6.gif "隐式链接和显式链接的比较")
  
## <a name="explicit-linking"></a>显式链接

由于默认 MAPI 客户端使用 Windows Installer (MSI) 支持按需安装, 因此您可以直接在 Outlook MAPI 存根 (而不是使用 mapi 库和 Windows MAPI 存根) 上开发邮件应用程序。 上图的右侧显示了 mapi 函数调用过程的示例, 从查找 outlook mapi 存根的路径和 DLL 名称 (下一节中的 "步骤 2") 的 mapi 应用程序开始, 并使函数调用 outlook mapi 存根 (下一节中的步骤 3)。 下面的过程演示如何使用显式链接来调用 MAPI 函数。 
  
> [!NOTE]
> 有关显式链接的此信息可能因引入以下部分中所述的 MAPIStubLibrary 而不符合您的需求。 与隐式模型一样, 新库可管理所有内容, 并实现直接加载 Outlook MAPI 的显式链接逻辑。 
  
有关显式链接的详细信息, 请参阅显式链接。
  
### <a name="to-call-mapi-api-elements-without-the-mapi-library-and-the-windows-mapi-stub"></a>在没有 mapi 库和 Windows MAPI 存根的情况下调用 mapi API 元素

1. 在您的程序文件中, 为要使用的每个 MAPI API 元素创建函数指针的全局列表。 
    
   下面的示例演示了这一步。
    
   ```cpp
    //Global MAPI function pointers
    LPMAPIINITIALIZE pfnMAPIInitialize = NULL;
    LPMAPIUNINITIALIZE pfnMAPIUninitialize = NULL;
   ```

2. 创建一个函数, 用于将 mapi 函数初始化为链接到默认 mapi 客户端的 mapi DLL (例如, Microsoft Outlook 的 Msmapi32)。 在此函数中, 执行以下操作: 
    
    1. 从相应的系统目录中加载 mapi32。 
        
       |||
       |:-----|:-----|
       |x64 或 x86 本机  <br/> |**%windir%\system32\mapi32.dll** <br/> |
       |WoW 模式下的 x86  <br/> |**%windir%\syswow64\mapi32.dll** <br/> |
    
    2. 调用[FGetComponentPath](fgetcomponentpath.md)函数, 以获取实现 MAPI 子系统的路径和 DLL 名称。 有关详细信息, 请参阅[选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)。
        
    3. 通过调用 LoadLibrary 函数加载 DLL。 
        
    4. 通过调用 GetProcAddress 函数初始化 MAPI 函数指针数组。 
        
    下面的示例展示了前面的步骤:
        
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

3. 最后, 在调用 MAPI API 元素之前, 请先调用您在邮件应用程序的步骤2中创建的函数。 
    
   > [!CAUTION]
   > 必须先取消对 MAPI 子系统的初始化, 然后再关闭您的应用程序。 
  
   下面的示例演示了这一步: 
    
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

## <a name="mapistublibrarylib"></a>MAPIStubLibrary

microsoft outlook 2010 和64位 MAPI 的出现现已扩展到 microsoft outlook 2013, 这需要的是传统的用于完整实施的32位 API。 在 CodePlex 网站上发布的新项目 (MAPI 存根库) 提供了支持同时生成32位和64位 MAPI 应用程序的 Mapi32 的替代项。 MAPIStubLibrary 无需显式链接到 MAPI 并生成它, 您可以从链接器设置中删除 Mapi32, 并将其替换为 MAPIStubLibrary;不需要进一步修改您的代码。 此外, 它还无需编写**LoadLibrary**、 **GetProcAddress**和**FreeLibrary**代码来处理此库文件中包含但不在 Mapi32 中的更新的导出, 如果您使用显式链接, 则需要这样做。 
  
从该库链接的某些新函数在 Mapi32 中不可用, 包括以下内容:
  
- [GetDefCachedMode](getdefcachedmode.md)    
- [HrGetGALFromEmsmdbUID](hrgetgalfromemsmdbuid.md)   
- [HrOpenOfflineObj](hropenofflineobj.md)    
- [MAPICrashRecovery](mapicrashrecovery.md)   
- [OpenStreamOnFileW](openstreamonfilew.md)    
- [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)
    
集成 MAPI 存根库的另一种方法是将源文件、MapiStubLibrary 和 StubUtils 直接复制到项目中, 并删除到 Mapi32 的任何链接以及任何显式链接到 MAPI 的代码。
  
若要访问 MAPI 存根库文件, 并获取有关如何生成并将其集成到项目中的信息, 以及有关此库的问题, 如何时和为什么要使用它, 请参阅 CodePlex 站点上的[MAPI 存根库](https://mapistublibrary.codeplex.com/documentation)。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 编程概述](mapi-programming-overview.md)
- [安装 MAPI 子系统](installing-the-mapi-subsystem.md)
- [安装 MAPI 头文件](how-to-install-mapi-header-files.md)
- [选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)
- [确定要使用的链接方法](https://msdn.microsoft.com/library/253b8k2c.aspx)
- [将可执行文件链接到 DLL](https://msdn.microsoft.com/library/9yd93633.aspx)
- [为 MAPI DLL 设置 MSI 密钥](https://msdn.microsoft.com/library/ee909494%28v=VS.85%29.aspx)

