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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400143"
---
# <a name="link-to-mapi-functions"></a><span data-ttu-id="57ea5-103">链接到 MAPI 函数</span><span class="sxs-lookup"><span data-stu-id="57ea5-103">Link to MAPI functions</span></span>

<span data-ttu-id="57ea5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57ea5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57ea5-105">有三种方法的链接： 隐式链接、 显式链接和使用 MAPI 存根库的新混合模型。</span><span class="sxs-lookup"><span data-stu-id="57ea5-105">There are three methods of linking: implicit linking, explicit linking, and a new hybrid model using the MAPI Stub Library.</span></span>
  
## <a name="implicit-linking"></a><span data-ttu-id="57ea5-106">隐式链接</span><span class="sxs-lookup"><span data-stu-id="57ea5-106">Implicit linking</span></span>

<span data-ttu-id="57ea5-107">过去，调用中的邮件应用程序始终 MAPI 函数涉及链接到 Mapi32.lib 库。</span><span class="sxs-lookup"><span data-stu-id="57ea5-107">Historically, calling MAPI functions in a messaging application always involved linking to the Mapi32.lib library.</span></span> <span data-ttu-id="57ea5-108">这包括 MAPI 呼叫路由至 Windows MAPI 存根库，Mapi32.dll，然后转接的呼叫在运行时的默认 MAPI 客户端实现。</span><span class="sxs-lookup"><span data-stu-id="57ea5-108">This included routing MAPI calls to the Windows MAPI stub library, Mapi32.dll, which then forwarded the calls to the default MAPI client implementation at run time.</span></span> <span data-ttu-id="57ea5-109">此呼叫过程称为隐式链接。</span><span class="sxs-lookup"><span data-stu-id="57ea5-109">This call process is known as implicit linking.</span></span> <span data-ttu-id="57ea5-110">下图的左侧显示 MAPI 函数呼叫过程中使用隐式链接的示例。</span><span class="sxs-lookup"><span data-stu-id="57ea5-110">The left side of the following figure shows an example of implicit linking used in a MAPI function call process.</span></span> <span data-ttu-id="57ea5-111">过程启动 MAPI 应用程序和涉及的 MAPI 库 (Mapi32.lib) 和 Windows MAPI 存根 (Mapi32.dll) 完成由 Outlook MAPI 客户端实现的 MAPI 存根 (Msmapi32.dll)。</span><span class="sxs-lookup"><span data-stu-id="57ea5-111">The process is initiated by a MAPI application and involves the MAPI library (Mapi32.lib) and the Windows MAPI stub (Mapi32.dll) and is completed by the Outlook MAPI client implementation of the MAPI stub (Msmapi32.dll).</span></span>
  
<span data-ttu-id="57ea5-112">**隐式和显式链接的比较。**</span><span class="sxs-lookup"><span data-stu-id="57ea5-112">**Comparison of implicit and explicit linking.**</span></span>

<span data-ttu-id="57ea5-113">![隐式和显式链接的比较](media/09d9c49a-a52d-4407-9013-d0d14c8f63f6.gif "隐式和显式链接的比较")</span><span class="sxs-lookup"><span data-stu-id="57ea5-113">![Comparison of implicit and explicit linking](media/09d9c49a-a52d-4407-9013-d0d14c8f63f6.gif "Comparison of implicit and explicit linking")</span></span>
  
## <a name="explicit-linking"></a><span data-ttu-id="57ea5-114">Explicit 链接</span><span class="sxs-lookup"><span data-stu-id="57ea5-114">Explicit linking</span></span>

<span data-ttu-id="57ea5-115">由于默认 MAPI 客户端支持使用 Windows Installer (MSI) 的按需安装，因此您可以开发邮件应用程序直接对 Outlook MAPI 存根而不是使用 MAPI 库和 Windows MAPI 存根。</span><span class="sxs-lookup"><span data-stu-id="57ea5-115">Because the default MAPI client supports on-demand installation using the Windows Installer (MSI), you can develop messaging applications directly on the Outlook MAPI stub instead of using the MAPI library and Windows MAPI stub.</span></span> <span data-ttu-id="57ea5-116">上图中的右侧显示了 MAPI 函数调用过程，启动与 MAPI 应用程序的路径和 Outlook MAPI 存根 （步骤 2 中下一节） 的 DLL 名称查找和 Outlook MAPI 存根 （的函数调用一个的示例步骤 3 中下一节）。</span><span class="sxs-lookup"><span data-stu-id="57ea5-116">The right side of the previous figure shows an example of a MAPI function call process, starting with a MAPI application looking for the path and DLL name for the Outlook MAPI stub (step 2 in the following section), and making function calls into the Outlook MAPI stub (step 3 in the following section).</span></span> <span data-ttu-id="57ea5-117">下面的过程演示如何使用显式链接调用 MAPI 函数。</span><span class="sxs-lookup"><span data-stu-id="57ea5-117">The following procedure shows how to call MAPI functions by using explicit linking.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="57ea5-118">有关显式链接此信息可能多余到引入了以下节所述 MAPIStubLibrary.lib 需求。</span><span class="sxs-lookup"><span data-stu-id="57ea5-118">This information about explicit linking may be superfluous to your needs with the introduction of the MAPIStubLibrary.lib discussed in the following section.</span></span> <span data-ttu-id="57ea5-119">隐式模型，如新库管理所有内容，并实现显式链接逻辑加载 Outlook 的 MAPI 直接。</span><span class="sxs-lookup"><span data-stu-id="57ea5-119">Like the implicit model, the new library manages everything and implements the explicit linking logic that loads Outlook's MAPI directly.</span></span> 
  
<span data-ttu-id="57ea5-120">有关显式链接的详细信息，请参阅显式链接。</span><span class="sxs-lookup"><span data-stu-id="57ea5-120">For more information about explicit linking, see Linking Explicitly.</span></span>
  
### <a name="to-call-mapi-api-elements-without-the-mapi-library-and-the-windows-mapi-stub"></a><span data-ttu-id="57ea5-121">若要调用不带 MAPI 库和 Windows MAPI 存根 MAPI API 元素</span><span class="sxs-lookup"><span data-stu-id="57ea5-121">To call MAPI API elements without the MAPI library and the Windows MAPI stub</span></span>

1. <span data-ttu-id="57ea5-122">在程序文件中，创建的每个 MAPI API 元素所使用的函数指针的全局列表。</span><span class="sxs-lookup"><span data-stu-id="57ea5-122">In your program file, create a global list of function pointers for each MAPI API element that you are using.</span></span> 
    
   <span data-ttu-id="57ea5-123">下面的示例演示此步骤。</span><span class="sxs-lookup"><span data-stu-id="57ea5-123">The following example shows this step.</span></span>
    
   ```cpp
    //Global MAPI function pointers
    LPMAPIINITIALIZE pfnMAPIInitialize = NULL;
    LPMAPIUNINITIALIZE pfnMAPIUninitialize = NULL;
   ```

2. <span data-ttu-id="57ea5-124">创建初始化 MAPI 函数来链接到默认 MAPI 客户端 (例如，Msmapi32.dll 的 Microsoft Outlook) 的 MAPI DLL 函数。</span><span class="sxs-lookup"><span data-stu-id="57ea5-124">Create a function that initializes MAPI functions to link to the MAPI DLL of the default MAPI client (for example, Msmapi32.dll of Microsoft Outlook).</span></span> <span data-ttu-id="57ea5-125">在此函数中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="57ea5-125">In this function, do the following:</span></span> 
    
    1. <span data-ttu-id="57ea5-126">从相应系统目录加载 mapi32.dll。</span><span class="sxs-lookup"><span data-stu-id="57ea5-126">Load mapi32.dll from the appropriate system directory.</span></span> 
        
       |||
       |:-----|:-----|
       |<span data-ttu-id="57ea5-127">x64 或 x86 本身</span><span class="sxs-lookup"><span data-stu-id="57ea5-127">x64 or x86 natively</span></span>  <br/> |<span data-ttu-id="57ea5-128">**%windir%\system32\mapi32.dll**</span><span class="sxs-lookup"><span data-stu-id="57ea5-128">**%windir%\system32\mapi32.dll**</span></span> <br/> |
       |<span data-ttu-id="57ea5-129">x86 WoW 模式</span><span class="sxs-lookup"><span data-stu-id="57ea5-129">x86 on WoW mode</span></span>  <br/> |<span data-ttu-id="57ea5-130">**%windir%\syswow64\mapi32.dll**</span><span class="sxs-lookup"><span data-stu-id="57ea5-130">**%windir%\syswow64\mapi32.dll**</span></span> <br/> |
    
    2. <span data-ttu-id="57ea5-131">调用[FGetComponentPath](fgetcomponentpath.md)函数可获取的路径和实现 MAPI 子系统的 DLL 名称。</span><span class="sxs-lookup"><span data-stu-id="57ea5-131">Call the [FGetComponentPath](fgetcomponentpath.md) function to get the path and DLL name that implements the MAPI subsystem.</span></span> <span data-ttu-id="57ea5-132">有关详细信息，请参阅[选择特定版本的 MAPI 到负载](how-to-choose-a-specific-version-of-mapi-to-load.md)。</span><span class="sxs-lookup"><span data-stu-id="57ea5-132">For more information, see [Choose a Specific Version of MAPI to Load](how-to-choose-a-specific-version-of-mapi-to-load.md).</span></span>
        
    3. <span data-ttu-id="57ea5-133">加载 DLL 通过调用 LoadLibrary 函数。</span><span class="sxs-lookup"><span data-stu-id="57ea5-133">Load the DLL by calling the LoadLibrary function.</span></span> 
        
    4. <span data-ttu-id="57ea5-134">通过调用 GetProcAddress 函数初始化 MAPI 函数指针数组。</span><span class="sxs-lookup"><span data-stu-id="57ea5-134">Initialize the MAPI function pointer array by calling the GetProcAddress function.</span></span> 
        
    <span data-ttu-id="57ea5-135">下面的示例演示前面的步骤：</span><span class="sxs-lookup"><span data-stu-id="57ea5-135">The following example shows the previous steps:</span></span>
        
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

3. <span data-ttu-id="57ea5-136">最后，调用函数您之前创建的步骤 2 中邮件应用程序中发出 MAPI API 元素的呼叫。</span><span class="sxs-lookup"><span data-stu-id="57ea5-136">Finally, call the function that you created in step 2 in your messaging application before you make calls to MAPI API elements.</span></span> 
    
   > [!CAUTION]
   > <span data-ttu-id="57ea5-137">关闭应用程序之前，必须先 MAPI 子系统取消初始化。</span><span class="sxs-lookup"><span data-stu-id="57ea5-137">You must uninitialize the MAPI subsystem before closing your application.</span></span> 
  
   <span data-ttu-id="57ea5-138">下面的示例演示此步骤：</span><span class="sxs-lookup"><span data-stu-id="57ea5-138">The following example shows this step:</span></span> 
    
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

## <a name="mapistublibrarylib"></a><span data-ttu-id="57ea5-139">MAPIStubLibrary.lib</span><span class="sxs-lookup"><span data-stu-id="57ea5-139">MAPIStubLibrary.lib</span></span>

<span data-ttu-id="57ea5-140">Microsoft Outlook 2010 和 64 位 MAPI，现在扩展到 Microsoft Outlook 2013 一起工作的要求超过完全实现的传统 32 位 API。</span><span class="sxs-lookup"><span data-stu-id="57ea5-140">The advent of Microsoft Outlook 2010 and 64-bit MAPI, now extending to the Microsoft Outlook 2013, requires more than the traditional 32-bit API for full implementation.</span></span> <span data-ttu-id="57ea5-141">新项目，MAPI 存根库，发布 CodePlex 网站上提供支持构建 32 位和 64 位的 MAPI 应用程序的 Mapi32.lib 顺便替换。</span><span class="sxs-lookup"><span data-stu-id="57ea5-141">A new project, the MAPI Stub Library, posted on the CodePlex website provides a drop-in replacement for Mapi32.lib that supports building both 32-bit and 64-bit MAPI applications.</span></span> <span data-ttu-id="57ea5-142">MAPIStubLibrary.lib 无需显式链接到 MAPI，并且具有构建它，您可以删除 Mapi32.lib 从链接器设置，替换 MAPIStubLibrary.lib;应不需要对代码进行任何进一步修改。</span><span class="sxs-lookup"><span data-stu-id="57ea5-142">MAPIStubLibrary.lib eliminates the need to explicitly link to MAPI, and having built it, you can remove Mapi32.lib from your linker settings, replacing it with MAPIStubLibrary.lib; no further modifications to your code should be needed.</span></span> <span data-ttu-id="57ea5-143">它也无需编写**LoadLibrary**和**GetProcAddress**，**句**代码来处理包含此库文件中，但不能在 Mapi32.lib，如果您使用显式链接将需要的较新导出。</span><span class="sxs-lookup"><span data-stu-id="57ea5-143">It also eliminates the need to write **LoadLibrary**, **GetProcAddress**, and **FreeLibrary** code to handle newer exports included in this library file but not in Mapi32.lib, which would be needed if you used explicit linking.</span></span> 
  
<span data-ttu-id="57ea5-144">某些链接从此库 Mapi32.lib 中不提供的新功能包括：</span><span class="sxs-lookup"><span data-stu-id="57ea5-144">Some of the new functions linked from this library that are not available in Mapi32.lib include the following:</span></span>
  
- [<span data-ttu-id="57ea5-145">GetDefCachedMode</span><span class="sxs-lookup"><span data-stu-id="57ea5-145">GetDefCachedMode</span></span>](getdefcachedmode.md)    
- [<span data-ttu-id="57ea5-146">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="57ea5-146">HrGetGALFromEmsmdbUID</span></span>](hrgetgalfromemsmdbuid.md)   
- [<span data-ttu-id="57ea5-147">HrOpenOfflineObj</span><span class="sxs-lookup"><span data-stu-id="57ea5-147">HrOpenOfflineObj</span></span>](hropenofflineobj.md)    
- [<span data-ttu-id="57ea5-148">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="57ea5-148">MAPICrashRecovery</span></span>](mapicrashrecovery.md)   
- [<span data-ttu-id="57ea5-149">OpenStreamOnFileW</span><span class="sxs-lookup"><span data-stu-id="57ea5-149">OpenStreamOnFileW</span></span>](openstreamonfilew.md)    
- [<span data-ttu-id="57ea5-150">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="57ea5-150">WrapCompressedRTFStreamEx</span></span>](wrapcompressedrtfstreamex.md)
    
<span data-ttu-id="57ea5-151">引入 MAPI 存根库的另一种方法是直接在您的项目复制的源文件，MapiStubLibrary.cpp 和 StubUtils.cpp，并删除 Mapi32.lib 到任何链接和显式链接到 MAPI 任何代码。</span><span class="sxs-lookup"><span data-stu-id="57ea5-151">An alternate method of incorporating the MAPI Stub Library is to copy the source files, MapiStubLibrary.cpp and StubUtils.cpp, directly into your project and remove any linkage to Mapi32.lib and any code that explicitly links to MAPI.</span></span>
  
<span data-ttu-id="57ea5-152">若要访问 MAPI 存根库文件，并了解如何生成并将其集成到您的项目，以及有关此库问题如何时和为什么使用它，请参阅[MAPI 存根库](https://mapistublibrary.codeplex.com/documentation)CodePlex 网站上。</span><span class="sxs-lookup"><span data-stu-id="57ea5-152">To access the MAPI Stub Library files and for information about how to build and integrate it into your project, as well as questions about this library such as when and why to use it, see the [MAPI Stub Library](https://mapistublibrary.codeplex.com/documentation) on the CodePlex site.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="57ea5-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57ea5-153">See also</span></span>

- [<span data-ttu-id="57ea5-154">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="57ea5-154">MAPI Programming Overview</span></span>](mapi-programming-overview.md)
- [<span data-ttu-id="57ea5-155">安装 MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="57ea5-155">Installing the MAPI Subsystem</span></span>](installing-the-mapi-subsystem.md)
- [<span data-ttu-id="57ea5-156">安装 MAPI 头文件</span><span class="sxs-lookup"><span data-stu-id="57ea5-156">Install MAPI Header Files</span></span>](how-to-install-mapi-header-files.md)
- [<span data-ttu-id="57ea5-157">选择要加载的 MAPI 的特定版本</span><span class="sxs-lookup"><span data-stu-id="57ea5-157">Choose a Specific Version of MAPI to Load</span></span>](how-to-choose-a-specific-version-of-mapi-to-load.md)
- [<span data-ttu-id="57ea5-158">确定要使用的链接方法</span><span class="sxs-lookup"><span data-stu-id="57ea5-158">Determining Which Linking Method to Use</span></span>](https://msdn.microsoft.com/library/253b8k2c.aspx)
- [<span data-ttu-id="57ea5-159">链接到 DLL 的可执行文件</span><span class="sxs-lookup"><span data-stu-id="57ea5-159">Linking an Executable to a DLL</span></span>](https://msdn.microsoft.com/library/9yd93633.aspx)
- [<span data-ttu-id="57ea5-160">MAPI dll 设置 MSI 键</span><span class="sxs-lookup"><span data-stu-id="57ea5-160">Setting Up the MSI Keys for Your MAPI DLL</span></span>](https://msdn.microsoft.com/library/ee909494%28v=VS.85%29.aspx)

