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
# <a name="link-to-mapi-functions"></a><span data-ttu-id="7fdb0-103">链接到 MAPI 函数</span><span class="sxs-lookup"><span data-stu-id="7fdb0-103">Link to MAPI functions</span></span>

<span data-ttu-id="7fdb0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7fdb0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7fdb0-105">有三种链接方式: 隐式链接、显式链接和使用 MAPI 存根库的新混合模型。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-105">There are three methods of linking: implicit linking, explicit linking, and a new hybrid model using the MAPI Stub Library.</span></span>
  
## <a name="implicit-linking"></a><span data-ttu-id="7fdb0-106">隐式链接</span><span class="sxs-lookup"><span data-stu-id="7fdb0-106">Implicit linking</span></span>

<span data-ttu-id="7fdb0-107">以前, 在邮件应用程序中调用 MAPI 函数始终会链接到 Mapi32 库。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-107">Historically, calling MAPI functions in a messaging application always involved linking to the Mapi32.lib library.</span></span> <span data-ttu-id="7fdb0-108">这包括将 MAPI 调用传递给 Windows MAPI 存根库, Mapi32, 然后在运行时将调用转发到默认的 MAPI 客户端实现。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-108">This included routing MAPI calls to the Windows MAPI stub library, Mapi32.dll, which then forwarded the calls to the default MAPI client implementation at run time.</span></span> <span data-ttu-id="7fdb0-109">此呼叫过程称为隐式链接。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-109">This call process is known as implicit linking.</span></span> <span data-ttu-id="7fdb0-110">下图的左侧显示了 MAPI 函数调用过程中使用的隐式链接的示例。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-110">The left side of the following figure shows an example of implicit linking used in a MAPI function call process.</span></span> <span data-ttu-id="7fdb0-111">此过程由 mapi 应用程序启动, 并涉及 mapi 库 (Mapi32) 和 Windows mapi 存根 (Mapi32), 并由 mapi 存根 (Msmapi32) 的 Outlook MAPI 客户端实现完成。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-111">The process is initiated by a MAPI application and involves the MAPI library (Mapi32.lib) and the Windows MAPI stub (Mapi32.dll) and is completed by the Outlook MAPI client implementation of the MAPI stub (Msmapi32.dll).</span></span>
  
<span data-ttu-id="7fdb0-112">**隐式链接和显式链接的比较。**</span><span class="sxs-lookup"><span data-stu-id="7fdb0-112">**Comparison of implicit and explicit linking.**</span></span>

<span data-ttu-id="7fdb0-113">![隐式链接和显式链接的比较](media/09d9c49a-a52d-4407-9013-d0d14c8f63f6.gif "隐式链接和显式链接的比较")</span><span class="sxs-lookup"><span data-stu-id="7fdb0-113">![Comparison of implicit and explicit linking](media/09d9c49a-a52d-4407-9013-d0d14c8f63f6.gif "Comparison of implicit and explicit linking")</span></span>
  
## <a name="explicit-linking"></a><span data-ttu-id="7fdb0-114">显式链接</span><span class="sxs-lookup"><span data-stu-id="7fdb0-114">Explicit linking</span></span>

<span data-ttu-id="7fdb0-115">由于默认 MAPI 客户端使用 Windows Installer (MSI) 支持按需安装, 因此您可以直接在 Outlook MAPI 存根 (而不是使用 mapi 库和 Windows MAPI 存根) 上开发邮件应用程序。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-115">Because the default MAPI client supports on-demand installation using the Windows Installer (MSI), you can develop messaging applications directly on the Outlook MAPI stub instead of using the MAPI library and Windows MAPI stub.</span></span> <span data-ttu-id="7fdb0-116">上图的右侧显示了 mapi 函数调用过程的示例, 从查找 outlook mapi 存根的路径和 DLL 名称 (下一节中的 "步骤 2") 的 mapi 应用程序开始, 并使函数调用 outlook mapi 存根 (下一节中的步骤 3)。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-116">The right side of the previous figure shows an example of a MAPI function call process, starting with a MAPI application looking for the path and DLL name for the Outlook MAPI stub (step 2 in the following section), and making function calls into the Outlook MAPI stub (step 3 in the following section).</span></span> <span data-ttu-id="7fdb0-117">下面的过程演示如何使用显式链接来调用 MAPI 函数。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-117">The following procedure shows how to call MAPI functions by using explicit linking.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7fdb0-118">有关显式链接的此信息可能因引入以下部分中所述的 MAPIStubLibrary 而不符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-118">This information about explicit linking may be superfluous to your needs with the introduction of the MAPIStubLibrary.lib discussed in the following section.</span></span> <span data-ttu-id="7fdb0-119">与隐式模型一样, 新库可管理所有内容, 并实现直接加载 Outlook MAPI 的显式链接逻辑。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-119">Like the implicit model, the new library manages everything and implements the explicit linking logic that loads Outlook's MAPI directly.</span></span> 
  
<span data-ttu-id="7fdb0-120">有关显式链接的详细信息, 请参阅显式链接。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-120">For more information about explicit linking, see Linking Explicitly.</span></span>
  
### <a name="to-call-mapi-api-elements-without-the-mapi-library-and-the-windows-mapi-stub"></a><span data-ttu-id="7fdb0-121">在没有 mapi 库和 Windows MAPI 存根的情况下调用 mapi API 元素</span><span class="sxs-lookup"><span data-stu-id="7fdb0-121">To call MAPI API elements without the MAPI library and the Windows MAPI stub</span></span>

1. <span data-ttu-id="7fdb0-122">在您的程序文件中, 为要使用的每个 MAPI API 元素创建函数指针的全局列表。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-122">In your program file, create a global list of function pointers for each MAPI API element that you are using.</span></span> 
    
   <span data-ttu-id="7fdb0-123">下面的示例演示了这一步。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-123">The following example shows this step.</span></span>
    
   ```cpp
    //Global MAPI function pointers
    LPMAPIINITIALIZE pfnMAPIInitialize = NULL;
    LPMAPIUNINITIALIZE pfnMAPIUninitialize = NULL;
   ```

2. <span data-ttu-id="7fdb0-124">创建一个函数, 用于将 mapi 函数初始化为链接到默认 mapi 客户端的 mapi DLL (例如, Microsoft Outlook 的 Msmapi32)。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-124">Create a function that initializes MAPI functions to link to the MAPI DLL of the default MAPI client (for example, Msmapi32.dll of Microsoft Outlook).</span></span> <span data-ttu-id="7fdb0-125">在此函数中, 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="7fdb0-125">In this function, do the following:</span></span> 
    
    1. <span data-ttu-id="7fdb0-126">从相应的系统目录中加载 mapi32。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-126">Load mapi32.dll from the appropriate system directory.</span></span> 
        
       |||
       |:-----|:-----|
       |<span data-ttu-id="7fdb0-127">x64 或 x86 本机</span><span class="sxs-lookup"><span data-stu-id="7fdb0-127">x64 or x86 natively</span></span>  <br/> |<span data-ttu-id="7fdb0-128">**%windir%\system32\mapi32.dll**</span><span class="sxs-lookup"><span data-stu-id="7fdb0-128">**%windir%\system32\mapi32.dll**</span></span> <br/> |
       |<span data-ttu-id="7fdb0-129">WoW 模式下的 x86</span><span class="sxs-lookup"><span data-stu-id="7fdb0-129">x86 on WoW mode</span></span>  <br/> |<span data-ttu-id="7fdb0-130">**%windir%\syswow64\mapi32.dll**</span><span class="sxs-lookup"><span data-stu-id="7fdb0-130">**%windir%\syswow64\mapi32.dll**</span></span> <br/> |
    
    2. <span data-ttu-id="7fdb0-131">调用[FGetComponentPath](fgetcomponentpath.md)函数, 以获取实现 MAPI 子系统的路径和 DLL 名称。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-131">Call the [FGetComponentPath](fgetcomponentpath.md) function to get the path and DLL name that implements the MAPI subsystem.</span></span> <span data-ttu-id="7fdb0-132">有关详细信息, 请参阅[选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-132">For more information, see [Choose a Specific Version of MAPI to Load](how-to-choose-a-specific-version-of-mapi-to-load.md).</span></span>
        
    3. <span data-ttu-id="7fdb0-133">通过调用 LoadLibrary 函数加载 DLL。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-133">Load the DLL by calling the LoadLibrary function.</span></span> 
        
    4. <span data-ttu-id="7fdb0-134">通过调用 GetProcAddress 函数初始化 MAPI 函数指针数组。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-134">Initialize the MAPI function pointer array by calling the GetProcAddress function.</span></span> 
        
    <span data-ttu-id="7fdb0-135">下面的示例展示了前面的步骤:</span><span class="sxs-lookup"><span data-stu-id="7fdb0-135">The following example shows the previous steps:</span></span>
        
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

3. <span data-ttu-id="7fdb0-136">最后, 在调用 MAPI API 元素之前, 请先调用您在邮件应用程序的步骤2中创建的函数。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-136">Finally, call the function that you created in step 2 in your messaging application before you make calls to MAPI API elements.</span></span> 
    
   > [!CAUTION]
   > <span data-ttu-id="7fdb0-137">必须先取消对 MAPI 子系统的初始化, 然后再关闭您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-137">You must uninitialize the MAPI subsystem before closing your application.</span></span> 
  
   <span data-ttu-id="7fdb0-138">下面的示例演示了这一步:</span><span class="sxs-lookup"><span data-stu-id="7fdb0-138">The following example shows this step:</span></span> 
    
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

## <a name="mapistublibrarylib"></a><span data-ttu-id="7fdb0-139">MAPIStubLibrary</span><span class="sxs-lookup"><span data-stu-id="7fdb0-139">MAPIStubLibrary.lib</span></span>

<span data-ttu-id="7fdb0-140">microsoft outlook 2010 和64位 MAPI 的出现现已扩展到 microsoft outlook 2013, 这需要的是传统的用于完整实施的32位 API。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-140">The advent of Microsoft Outlook 2010 and 64-bit MAPI, now extending to the Microsoft Outlook 2013, requires more than the traditional 32-bit API for full implementation.</span></span> <span data-ttu-id="7fdb0-141">在 CodePlex 网站上发布的新项目 (MAPI 存根库) 提供了支持同时生成32位和64位 MAPI 应用程序的 Mapi32 的替代项。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-141">A new project, the MAPI Stub Library, posted on the CodePlex website provides a drop-in replacement for Mapi32.lib that supports building both 32-bit and 64-bit MAPI applications.</span></span> <span data-ttu-id="7fdb0-142">MAPIStubLibrary 无需显式链接到 MAPI 并生成它, 您可以从链接器设置中删除 Mapi32, 并将其替换为 MAPIStubLibrary;不需要进一步修改您的代码。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-142">MAPIStubLibrary.lib eliminates the need to explicitly link to MAPI, and having built it, you can remove Mapi32.lib from your linker settings, replacing it with MAPIStubLibrary.lib; no further modifications to your code should be needed.</span></span> <span data-ttu-id="7fdb0-143">此外, 它还无需编写**LoadLibrary**、 **GetProcAddress**和**FreeLibrary**代码来处理此库文件中包含但不在 Mapi32 中的更新的导出, 如果您使用显式链接, 则需要这样做。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-143">It also eliminates the need to write **LoadLibrary**, **GetProcAddress**, and **FreeLibrary** code to handle newer exports included in this library file but not in Mapi32.lib, which would be needed if you used explicit linking.</span></span> 
  
<span data-ttu-id="7fdb0-144">从该库链接的某些新函数在 Mapi32 中不可用, 包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="7fdb0-144">Some of the new functions linked from this library that are not available in Mapi32.lib include the following:</span></span>
  
- [<span data-ttu-id="7fdb0-145">GetDefCachedMode</span><span class="sxs-lookup"><span data-stu-id="7fdb0-145">GetDefCachedMode</span></span>](getdefcachedmode.md)    
- [<span data-ttu-id="7fdb0-146">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="7fdb0-146">HrGetGALFromEmsmdbUID</span></span>](hrgetgalfromemsmdbuid.md)   
- [<span data-ttu-id="7fdb0-147">HrOpenOfflineObj</span><span class="sxs-lookup"><span data-stu-id="7fdb0-147">HrOpenOfflineObj</span></span>](hropenofflineobj.md)    
- [<span data-ttu-id="7fdb0-148">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="7fdb0-148">MAPICrashRecovery</span></span>](mapicrashrecovery.md)   
- [<span data-ttu-id="7fdb0-149">OpenStreamOnFileW</span><span class="sxs-lookup"><span data-stu-id="7fdb0-149">OpenStreamOnFileW</span></span>](openstreamonfilew.md)    
- [<span data-ttu-id="7fdb0-150">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="7fdb0-150">WrapCompressedRTFStreamEx</span></span>](wrapcompressedrtfstreamex.md)
    
<span data-ttu-id="7fdb0-151">集成 MAPI 存根库的另一种方法是将源文件、MapiStubLibrary 和 StubUtils 直接复制到项目中, 并删除到 Mapi32 的任何链接以及任何显式链接到 MAPI 的代码。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-151">An alternate method of incorporating the MAPI Stub Library is to copy the source files, MapiStubLibrary.cpp and StubUtils.cpp, directly into your project and remove any linkage to Mapi32.lib and any code that explicitly links to MAPI.</span></span>
  
<span data-ttu-id="7fdb0-152">若要访问 MAPI 存根库文件, 并获取有关如何生成并将其集成到项目中的信息, 以及有关此库的问题, 如何时和为什么要使用它, 请参阅 CodePlex 站点上的[MAPI 存根库](https://mapistublibrary.codeplex.com/documentation)。</span><span class="sxs-lookup"><span data-stu-id="7fdb0-152">To access the MAPI Stub Library files and for information about how to build and integrate it into your project, as well as questions about this library such as when and why to use it, see the [MAPI Stub Library](https://mapistublibrary.codeplex.com/documentation) on the CodePlex site.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7fdb0-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fdb0-153">See also</span></span>

- [<span data-ttu-id="7fdb0-154">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="7fdb0-154">MAPI Programming Overview</span></span>](mapi-programming-overview.md)
- [<span data-ttu-id="7fdb0-155">安装 MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="7fdb0-155">Installing the MAPI Subsystem</span></span>](installing-the-mapi-subsystem.md)
- [<span data-ttu-id="7fdb0-156">安装 MAPI 头文件</span><span class="sxs-lookup"><span data-stu-id="7fdb0-156">Install MAPI Header Files</span></span>](how-to-install-mapi-header-files.md)
- [<span data-ttu-id="7fdb0-157">选择要加载的 MAPI 的特定版本</span><span class="sxs-lookup"><span data-stu-id="7fdb0-157">Choose a Specific Version of MAPI to Load</span></span>](how-to-choose-a-specific-version-of-mapi-to-load.md)
- [<span data-ttu-id="7fdb0-158">确定要使用的链接方法</span><span class="sxs-lookup"><span data-stu-id="7fdb0-158">Determining Which Linking Method to Use</span></span>](https://msdn.microsoft.com/library/253b8k2c.aspx)
- [<span data-ttu-id="7fdb0-159">将可执行文件链接到 DLL</span><span class="sxs-lookup"><span data-stu-id="7fdb0-159">Linking an Executable to a DLL</span></span>](https://msdn.microsoft.com/library/9yd93633.aspx)
- [<span data-ttu-id="7fdb0-160">为 MAPI DLL 设置 MSI 密钥</span><span class="sxs-lookup"><span data-stu-id="7fdb0-160">Setting Up the MSI Keys for Your MAPI DLL</span></span>](https://msdn.microsoft.com/library/ee909494%28v=VS.85%29.aspx)

