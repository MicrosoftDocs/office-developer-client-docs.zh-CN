---
title: 选择要加载的特定版本 MAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 85539a7f-74b6-4267-86ea-00da2c900c34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d353eba55e33b8ab48b3c47d2f31f1b5e0973b58
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344518"
---
# <a name="choose-a-specific-version-of-mapi-to-load"></a><span data-ttu-id="58106-103">选择要加载的特定版本 MAPI</span><span class="sxs-lookup"><span data-stu-id="58106-103">Choose a specific version of MAPI to load</span></span>

<span data-ttu-id="58106-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58106-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58106-105">当显式链接到 MAPI 的实现时，必须仔细选择要加载的实现。</span><span class="sxs-lookup"><span data-stu-id="58106-105">When linking explicitly to an implementation of MAPI, you must carefully select which implementation to load.</span></span> 
  
<span data-ttu-id="58106-106">有两种方法可显式链接到 MAPI 的实现。</span><span class="sxs-lookup"><span data-stu-id="58106-106">There are two methods to link explicitly to an implementation of MAPI.</span></span> 
  
1. <span data-ttu-id="58106-107">可以加载 MAPI 存根库，在注册表中指定要加载和调度 MAPI 调用的自定义 DLL。</span><span class="sxs-lookup"><span data-stu-id="58106-107">You can load the MAPI stub library, and specify in the registry a custom DLL to load and dispatch MAPI calls to.</span></span>
    
2. <span data-ttu-id="58106-108">您可以实现 MAPI 客户端查找算法来查找默认邮件客户端使用的 MAPI 版本并加载它。</span><span class="sxs-lookup"><span data-stu-id="58106-108">You can implement the MAPI client lookup algorithm to look up the version of MAPI used by the default mail client and load it.</span></span>
    
<span data-ttu-id="58106-109">由于可以更改Mapi32.dll[存根注册表 设置](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx)以指示应用程序使用 MAPI 的任何实现，因此我们建议你指示应用程序使用已测试的 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="58106-109">Because you can change the [Mapi32.dll Stub Registry Settings](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx) to direct your application to use any implementation of MAPI, we recommend that you direct your application to use an implementation of MAPI that you have tested with.</span></span> <span data-ttu-id="58106-110">下面介绍了两种显式链接方法。</span><span class="sxs-lookup"><span data-stu-id="58106-110">The following describes both methods of linking explicitly.</span></span> 
  
## <a name="reading-from-the-registry"></a><span data-ttu-id="58106-111">从注册表读取</span><span class="sxs-lookup"><span data-stu-id="58106-111">Reading from the registry</span></span>

### <a name="to-read-mapi-implementation-information-from-the-registry"></a><span data-ttu-id="58106-112">从注册表中读取 MAPI 实现信息</span><span class="sxs-lookup"><span data-stu-id="58106-112">To read MAPI implementation information from the registry</span></span>

1. <span data-ttu-id="58106-113">指示邮件客户端的自定义 DLL 的注册表项位于邮件客户端  `HKLM\Software\Clients\Mail` 的项下。</span><span class="sxs-lookup"><span data-stu-id="58106-113">The registry keys that indicate a custom DLL for a mail client are located under the  `HKLM\Software\Clients\Mail` key of the mail client.</span></span> 
    
   <span data-ttu-id="58106-114">下表介绍了这些键：</span><span class="sxs-lookup"><span data-stu-id="58106-114">The following table describes these keys:</span></span>
    
   |<span data-ttu-id="58106-115">**按键**</span><span class="sxs-lookup"><span data-stu-id="58106-115">**Key**</span></span>|<span data-ttu-id="58106-116">**描述**</span><span class="sxs-lookup"><span data-stu-id="58106-116">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="58106-117">MSIComponentID</span><span class="sxs-lookup"><span data-stu-id="58106-117">MSIComponentID</span></span>  <br/> |<span data-ttu-id="58106-118">一Windows Installer PublishComponent 类别 ID (GUID) ，用于标识导出简单 MAPI 或 MAPI 调用的 DLL。</span><span class="sxs-lookup"><span data-stu-id="58106-118">A Windows Installer PublishComponent category ID (GUID) that identifies the DLL that exports simple MAPI or MAPI calls.</span></span> <span data-ttu-id="58106-119">如果设置，则此键优先于 **DLLPath** 或 **DLLPathEx** 键。</span><span class="sxs-lookup"><span data-stu-id="58106-119">If set, this key takes precedence over the **DLLPath** or **DLLPathEx** key.</span></span>  <br/> |
   |<span data-ttu-id="58106-120">MSIApplicationLCID</span><span class="sxs-lookup"><span data-stu-id="58106-120">MSIApplicationLCID</span></span>  <br/> |<span data-ttu-id="58106-121">应用程序 (LCID) 区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="58106-121">Locale identifier (LCID) for your application.</span></span> <span data-ttu-id="58106-122">第一个字符串值标识来自 的子项，后续字符串值标识此注册表项下包含区域设置信息的  `HKLM\Software` 注册表值。</span><span class="sxs-lookup"><span data-stu-id="58106-122">The first string value identifies a sub-key from  `HKLM\Software` and subsequent string values identify registry values underneath this key that contain locale information.</span></span>  <br/> |
   |<span data-ttu-id="58106-123">MSIOfficeLCID</span><span class="sxs-lookup"><span data-stu-id="58106-123">MSIOfficeLCID</span></span>  <br/> |<span data-ttu-id="58106-124">Microsoft Office 的 CID。</span><span class="sxs-lookup"><span data-stu-id="58106-124">LCIDs for Microsoft Office.</span></span> <span data-ttu-id="58106-125">第一个字符串值标识来自 的子项，后续  `HKLM\Software` 字符串值标识此注册表项下的注册表值。</span><span class="sxs-lookup"><span data-stu-id="58106-125">The first string value identifies a sub-key from  `HKLM\Software` and subsequent string values identify registry values underneath this key.</span></span>  <br/> |
   
   <span data-ttu-id="58106-126">从这些密钥获取信息。</span><span class="sxs-lookup"><span data-stu-id="58106-126">Obtain the information from these keys.</span></span>
    
2. <span data-ttu-id="58106-127">将上一步获取的值传递到 [FGetComponentPath](fgetcomponentpath.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="58106-127">Pass the values that you obtained from the previous step to the [FGetComponentPath](fgetcomponentpath.md) function.</span></span> <span data-ttu-id="58106-128">**FGetComponentPath** 是由 MAPI 存根库导出的函数Mapistub.dll。</span><span class="sxs-lookup"><span data-stu-id="58106-128">**FGetComponentPath** is a function that is exported by the MAPI stub library Mapistub.dll.</span></span> <span data-ttu-id="58106-129">它返回 MAPI 的自定义版本的路径。</span><span class="sxs-lookup"><span data-stu-id="58106-129">It returns the path of the custom version of MAPI.</span></span> 


### <a name="to-load-the-implementation-of-mapi-marked-as-default"></a><span data-ttu-id="58106-130">加载标记为默认值的 MAPI 的实现</span><span class="sxs-lookup"><span data-stu-id="58106-130">To load the implementation of MAPI marked as default</span></span>

1. <span data-ttu-id="58106-131">读取  `HKLM\Software\Clients\Mail::(default)` 注册表值。</span><span class="sxs-lookup"><span data-stu-id="58106-131">Read the  `HKLM\Software\Clients\Mail::(default)` registry value.</span></span> 
    
2. <span data-ttu-id="58106-132">如前文所述，查找指示的客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="58106-132">Look up the information for the indicated client as described earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="58106-133">请注意，默认邮件客户端可能不会实现扩展 MAPI。</span><span class="sxs-lookup"><span data-stu-id="58106-133">Note that the default mail client might not implement Extended MAPI.</span></span> 
  
#### <a name="example"></a><span data-ttu-id="58106-134">示例</span><span class="sxs-lookup"><span data-stu-id="58106-134">Example</span></span>

<span data-ttu-id="58106-135">若要加载 MAPI（由 Outlook 实现，请查找 下的注册表项，然后将它们传递到 `HKLM\Software\Clients\Mail\Microsoft Outlook` **FGetComponentPath**。</span><span class="sxs-lookup"><span data-stu-id="58106-135">To load MAPI as implemented by Outlook, look up the registry keys under  `HKLM\Software\Clients\Mail\Microsoft Outlook` and pass them to **FGetComponentPath**.</span></span> <span data-ttu-id="58106-136">**FGetComponentPath** 将返回 mapI Outlook实现的路径。</span><span class="sxs-lookup"><span data-stu-id="58106-136">**FGetComponentPath** will return the path for Outlook's implementation of MAPI.</span></span> 
  
<span data-ttu-id="58106-137">如果未设置 **项 MSIComponentID、MSIApplicationLCID** 和 **MSIOfficeLCID，** 请检查 **DLLPathEx** 注册表值。 </span><span class="sxs-lookup"><span data-stu-id="58106-137">If the keys **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID** are not set, check the **DLLPathEx** registry value.</span></span> <span data-ttu-id="58106-138">如果设置了这些键， **则 FGetComponentPath** 会提供客户端实现 MAPI 的路径。</span><span class="sxs-lookup"><span data-stu-id="58106-138">If the keys are set, **FGetComponentPath** gives the path of the client's implementation of MAPI.</span></span> 
  
## <a name="implementing-the-mapi-client-lookup-algorithm"></a><span data-ttu-id="58106-139">实现 MAPI 客户端查找算法</span><span class="sxs-lookup"><span data-stu-id="58106-139">Implementing the MAPI Client Lookup algorithm</span></span>

<span data-ttu-id="58106-140">下表列出了 MFCMAPI 中用于查找 MAPI 自定义实现路径的四个函数：</span><span class="sxs-lookup"><span data-stu-id="58106-140">The following table lists the four functions from MFCMAPI that are used to look up the path for a custom implementation of MAPI:</span></span>
  
|<span data-ttu-id="58106-141">**函数**</span><span class="sxs-lookup"><span data-stu-id="58106-141">**Function**</span></span>|<span data-ttu-id="58106-142">**说明**</span><span class="sxs-lookup"><span data-stu-id="58106-142">**Description**</span></span>|
|:-----|:-----|
| `GetMAPIPath` <br/> |<span data-ttu-id="58106-143">获取 MAPI 库路径。</span><span class="sxs-lookup"><span data-stu-id="58106-143">Gets the MAPI library path.</span></span>  <br/> |
| `GetMailKey` <br/> |<span data-ttu-id="58106-144">获取 MAPI 邮件注册表项。</span><span class="sxs-lookup"><span data-stu-id="58106-144">Gets the MAPI mail registry key.</span></span>  <br/> |
| `GetMapiMsiIds` <br/> |<span data-ttu-id="58106-145">获取 Windows Installer 标识符。</span><span class="sxs-lookup"><span data-stu-id="58106-145">Gets the Windows Installer identifier.</span></span>  <br/> |
| `GetComponentPath` <br/> |<span data-ttu-id="58106-146">使用 [FGetComponentPath 获取组件路径](fgetcomponentpath.md)。</span><span class="sxs-lookup"><span data-stu-id="58106-146">Gets the component path using [FGetComponentPath](fgetcomponentpath.md).</span></span>  <br/> |
   
<span data-ttu-id="58106-147">由于 MFCMAPI 默认加载 MAPI 的默认实现，因此如果要使用不同的 MAPI 实现，则必须明确指示它这样做。</span><span class="sxs-lookup"><span data-stu-id="58106-147">Because MFCMAPI loads the default implementation of MAPI by default, if you want to use a different implementation of MAPI, you must explicitly direct it to do so.</span></span> <span data-ttu-id="58106-148">这是通过使用 **Session\Load MAPI** 例程执行的。</span><span class="sxs-lookup"><span data-stu-id="58106-148">This is performed by using the **Session\Load MAPI** routine.</span></span> 
  
### <a name="how-these-functions-work"></a><span data-ttu-id="58106-149">这些函数如何工作</span><span class="sxs-lookup"><span data-stu-id="58106-149">How these functions work</span></span>

1. <span data-ttu-id="58106-150">MFCMAPI  `GetMAPIPath` 调用 ，为客户端参数传递 NULL，以加载默认的 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="58106-150">MFCMAPI calls  `GetMAPIPath`, passing NULL for the client parameter, to load the default MAPI implementation.</span></span>
    
2.  <span data-ttu-id="58106-151">`GetMAPIPath`调用 `GetMapiMsiIds` 以读取 **MSIComponentID、MSIApplicationLCID** 和 **MSIOfficeLCID 的值**。 </span><span class="sxs-lookup"><span data-stu-id="58106-151">`GetMAPIPath` calls  `GetMapiMsiIds` to read the values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**.</span></span>
    
3.  <span data-ttu-id="58106-152">`GetMapiMsiIds` 调用  `GetMailKey` 打开默认邮件客户端的注册表项。</span><span class="sxs-lookup"><span data-stu-id="58106-152">`GetMapiMsiIds` calls  `GetMailKey` to open the registry key for the default mail client.</span></span> 
    
4.  <span data-ttu-id="58106-153">`GetMapiMsiIds` 使用 返回的注册表句柄查找  `GetMailKey` **MSIComponentID** **、MSIApplicationLCID** 和 **MSIOfficeLCID 的值**。</span><span class="sxs-lookup"><span data-stu-id="58106-153">`GetMapiMsiIds` uses the registry handle returned by  `GetMailKey` to look up values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**.</span></span>
    
5. <span data-ttu-id="58106-154">**MSIComponentID、MSIApplicationLCID** 和 **MSIOfficeLCID** 的值将返回到 `GetMAPIPath` 。</span><span class="sxs-lookup"><span data-stu-id="58106-154">The values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**, are returned to  `GetMAPIPath`.</span></span>  <span data-ttu-id="58106-155">`GetMAPIPath` 然后将它们传递给  `GetComponentPath` 。</span><span class="sxs-lookup"><span data-stu-id="58106-155">`GetMAPIPath` then passes them to  `GetComponentPath`.</span></span>
    
6.  <span data-ttu-id="58106-156">`GetComponentPath` 从系统目录加载 MAPI 存根库Mapi32.dll，并加载该存根库。</span><span class="sxs-lookup"><span data-stu-id="58106-156">`GetComponentPath` loads the MAPI stub library, Mapi32.dll, from the system directory.</span></span> 
    
7.  <span data-ttu-id="58106-157">`GetComponentPath` 然后，从数据库检索 **FGetComponentPath** 函数的地址Mapi32.dll假定Mapi32.dll **导出 FGetComponentPath**。</span><span class="sxs-lookup"><span data-stu-id="58106-157">`GetComponentPath` then retrieves the address of the **FGetComponentPath** function from Mapi32.dll, assuming that Mapi32.dll exports **FGetComponentPath**.</span></span>
    
8. <span data-ttu-id="58106-158">如果从服务器获取 **FGetComponentPath** Mapi32.dll失败，请从  `GetComponentPath` Mapistub.dll。</span><span class="sxs-lookup"><span data-stu-id="58106-158">If getting the address of **FGetComponentPath** from Mapi32.dll fails,  `GetComponentPath` retrieves the address from Mapistub.dll.</span></span> 
    
9.  <span data-ttu-id="58106-159">`GetComponentPath` 然后调用 **FGetComponentPath**，获取 MAPI 的默认版本的路径。</span><span class="sxs-lookup"><span data-stu-id="58106-159">`GetComponentPath` then calls **FGetComponentPath**, obtaining the path of the default version of MAPI.</span></span>
    
10.  <span data-ttu-id="58106-160">`GetMAPIPath` 然后将此路径返回到调用方，调用方随后加载 MAPI 并显式链接到它，如 [链接到 MAPI 函数 中所述](how-to-link-to-mapi-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="58106-160">`GetMAPIPath` then returns this path to the caller, which then loads MAPI and explicitly links to it as described in [Link to MAPI Functions](how-to-link-to-mapi-functions.md).</span></span>
    
> [!NOTE] 
> - <span data-ttu-id="58106-161">若要支持针对英语和非英语区域设置本地化的 MAPI 副本，请读取  `GetMAPIPath` **MSIApplicationLCID** 和 **MSIOfficeLCID** 子项的值。</span><span class="sxs-lookup"><span data-stu-id="58106-161">To support localized copies of MAPI for English and non-English locales,  `GetMAPIPath` reads the values for the **MSIApplicationLCID** and **MSIOfficeLCID** subkeys.</span></span>  <span data-ttu-id="58106-162">`GetMAPIPath` 然后调用 **FGetComponentPath**，首先将 **MSIApplicationLCID** 指定为 **szQualifier**，然后再次将 **MSIOfficeLCID** 指定为 **szQualifier**。</span><span class="sxs-lookup"><span data-stu-id="58106-162">`GetMAPIPath` then calls **FGetComponentPath**, first specifying **MSIApplicationLCID** as **szQualifier**, and again specifying **MSIOfficeLCID** as **szQualifier**.</span></span> <span data-ttu-id="58106-163">有关支持非英语语言的邮件客户端的注册表项详细信息，请参阅 Setting Up [the MSI Keys for Your MAPI DLL。](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="58106-163">For more information about registry keys for mail clients that support non-English languages, see [Setting Up the MSI Keys for Your MAPI DLL](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx).</span></span>   
> - <span data-ttu-id="58106-164">如果 MFCMAPI 没有收到使用 的 MAPI 的路径，它将从系统目录加载 MAPI 存根  `GetMAPIPath` 库。</span><span class="sxs-lookup"><span data-stu-id="58106-164">If MFCMAPI does not receive a path for MAPI using  `GetMAPIPath`, it loads the MAPI stub library from the system directory.</span></span>
> - <span data-ttu-id="58106-165">明确将 MAPI 调用映射到 [MAPI DLL](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx)中讨论的 **MSMapiApps** 注册表值仅适用于使用 MAPI 存根库的情况。</span><span class="sxs-lookup"><span data-stu-id="58106-165">The **MSMapiApps** registry value discussed in [Explicitly Mapping MAPI Calls to MAPI DLLs](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx) only applies when the MAPI Stub library is used.</span></span> <span data-ttu-id="58106-166">加载 MAPI 的特定实现或加载默认实现的应用程序不需要设置 **MSMapiApps** 注册表项。</span><span class="sxs-lookup"><span data-stu-id="58106-166">Applications that load a specific implementation of MAPI or load the default implementation do not have to set the **MSMapiApps** registry key.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="58106-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58106-167">See also</span></span>

- [<span data-ttu-id="58106-168">FGetComponentPath</span><span class="sxs-lookup"><span data-stu-id="58106-168">FGetComponentPath</span></span>](fgetcomponentpath.md)
- [<span data-ttu-id="58106-169">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="58106-169">MAPI Programming Overview</span></span>](mapi-programming-overview.md)
- [<span data-ttu-id="58106-170">链接到 MAPI 函数</span><span class="sxs-lookup"><span data-stu-id="58106-170">Link to MAPI Functions</span></span>](how-to-link-to-mapi-functions.md)
- [<span data-ttu-id="58106-171">Mapi32.dll存根注册表设置</span><span class="sxs-lookup"><span data-stu-id="58106-171">Mapi32.dll Stub Registry Settings</span></span>](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx)
- [<span data-ttu-id="58106-172">为 MAPI DLL 设置 MSI 密钥</span><span class="sxs-lookup"><span data-stu-id="58106-172">Setting Up the MSI Keys for Your MAPI DLL</span></span>](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)
- [<span data-ttu-id="58106-173">将 MAPI 调用显式映射到 MAPI DLL</span><span class="sxs-lookup"><span data-stu-id="58106-173">Explicitly Mapping MAPI Calls to MAPI DLLs</span></span>](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx)

