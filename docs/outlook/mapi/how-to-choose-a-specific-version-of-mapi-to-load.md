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
# <a name="choose-a-specific-version-of-mapi-to-load"></a><span data-ttu-id="3b2f5-103">选择要加载的特定版本 MAPI</span><span class="sxs-lookup"><span data-stu-id="3b2f5-103">Choose a specific version of MAPI to load</span></span>

<span data-ttu-id="3b2f5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b2f5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b2f5-105">当显式链接到 MAPI 的实现时, 您必须仔细选择要加载的实现。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-105">When linking explicitly to an implementation of MAPI, you must carefully select which implementation to load.</span></span> 
  
<span data-ttu-id="3b2f5-106">有两种方法可显式链接到 MAPI 的实现。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-106">There are two methods to link explicitly to an implementation of MAPI.</span></span> 
  
1. <span data-ttu-id="3b2f5-107">您可以加载 mapi 存根库, 并在注册表中指定一个用于加载和调度 MAPI 调用的自定义 DLL。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-107">You can load the MAPI stub library, and specify in the registry a custom DLL to load and dispatch MAPI calls to.</span></span>
    
2. <span data-ttu-id="3b2f5-108">您可以实现 MAPI 客户端查找算法, 以查找默认邮件客户端使用的 mapi 版本并加载它。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-108">You can implement the MAPI client lookup algorithm to look up the version of MAPI used by the default mail client and load it.</span></span>
    
<span data-ttu-id="3b2f5-109">由于您可以更改[Mapi32 存根 (Stub) 注册表设置](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx), 以使应用程序使用任何 mapi 实现, 因此我们建议您将应用程序定向到使用已通过测试的 mapi 实现。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-109">Because you can change the [Mapi32.dll Stub Registry Settings](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx) to direct your application to use any implementation of MAPI, we recommend that you direct your application to use an implementation of MAPI that you have tested with.</span></span> <span data-ttu-id="3b2f5-110">下面介绍了这两种方法的显式链接。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-110">The following describes both methods of linking explicitly.</span></span> 
  
## <a name="reading-from-the-registry"></a><span data-ttu-id="3b2f5-111">读取注册表</span><span class="sxs-lookup"><span data-stu-id="3b2f5-111">Reading from the registry</span></span>

### <a name="to-read-mapi-implementation-information-from-the-registry"></a><span data-ttu-id="3b2f5-112">从注册表中读取 MAPI 实现信息</span><span class="sxs-lookup"><span data-stu-id="3b2f5-112">To read MAPI implementation information from the registry</span></span>

1. <span data-ttu-id="3b2f5-113">指示邮件客户端的自定义 DLL 的注册表项位于邮件客户端的`HKLM\Software\Clients\Mail`键下。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-113">The registry keys that indicate a custom DLL for a mail client are located under the  `HKLM\Software\Clients\Mail` key of the mail client.</span></span> 
    
   <span data-ttu-id="3b2f5-114">下表对这些项进行了描述:</span><span class="sxs-lookup"><span data-stu-id="3b2f5-114">The following table describes these keys:</span></span>
    
   |<span data-ttu-id="3b2f5-115">**按键**</span><span class="sxs-lookup"><span data-stu-id="3b2f5-115">**Key**</span></span>|<span data-ttu-id="3b2f5-116">**描述**</span><span class="sxs-lookup"><span data-stu-id="3b2f5-116">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3b2f5-117">MSIComponentID</span><span class="sxs-lookup"><span data-stu-id="3b2f5-117">MSIComponentID</span></span>  <br/> |<span data-ttu-id="3b2f5-118">Windows Installer PublishComponent 类别 ID (GUID), 用于标识导出简单 MAPI 或 mapi 调用的 DLL。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-118">A Windows Installer PublishComponent category ID (GUID) that identifies the DLL that exports simple MAPI or MAPI calls.</span></span> <span data-ttu-id="3b2f5-119">如果设置, 则此项优先于**DLLPath**或**DLLPathEx**项。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-119">If set, this key takes precedence over the **DLLPath** or **DLLPathEx** key.</span></span>  <br/> |
   |<span data-ttu-id="3b2f5-120">MSIApplicationLCID</span><span class="sxs-lookup"><span data-stu-id="3b2f5-120">MSIApplicationLCID</span></span>  <br/> |<span data-ttu-id="3b2f5-121">应用程序的区域设置标识符 (LCID)。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-121">Locale identifier (LCID) for your application.</span></span> <span data-ttu-id="3b2f5-122">第一个字符串值标识 from `HKLM\Software`关键字 and 后续字符串值标识此项下包含区域设置信息的注册表值。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-122">The first string value identifies a sub-key from  `HKLM\Software` and subsequent string values identify registry values underneath this key that contain locale information.</span></span>  <br/> |
   |<span data-ttu-id="3b2f5-123">MSIOfficeLCID</span><span class="sxs-lookup"><span data-stu-id="3b2f5-123">MSIOfficeLCID</span></span>  <br/> |<span data-ttu-id="3b2f5-124">Microsoft Office 的 lcid。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-124">LCIDs for Microsoft Office.</span></span> <span data-ttu-id="3b2f5-125">第一个字符串值标识 from `HKLM\Software`关键字, 后面的字符串值标识此项下的注册表值。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-125">The first string value identifies a sub-key from  `HKLM\Software` and subsequent string values identify registry values underneath this key.</span></span>  <br/> |
   
   <span data-ttu-id="3b2f5-126">获取这些项中的信息。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-126">Obtain the information from these keys.</span></span>
    
2. <span data-ttu-id="3b2f5-127">将您从上一步获取的值传递给[FGetComponentPath](fgetcomponentpath.md)函数。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-127">Pass the values that you obtained from the previous step to the [FGetComponentPath](fgetcomponentpath.md) function.</span></span> <span data-ttu-id="3b2f5-128">**FGetComponentPath**是由 MAPI 存根库 Mapistub 导出的函数。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-128">**FGetComponentPath** is a function that is exported by the MAPI stub library Mapistub.dll.</span></span> <span data-ttu-id="3b2f5-129">它返回 MAPI 自定义版本的路径。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-129">It returns the path of the custom version of MAPI.</span></span> 


### <a name="to-load-the-implementation-of-mapi-marked-as-default"></a><span data-ttu-id="3b2f5-130">加载标记为默认值的 MAPI 的实现</span><span class="sxs-lookup"><span data-stu-id="3b2f5-130">To load the implementation of MAPI marked as default</span></span>

1. <span data-ttu-id="3b2f5-131">读取`HKLM\Software\Clients\Mail::(default)`注册表值。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-131">Read the  `HKLM\Software\Clients\Mail::(default)` registry value.</span></span> 
    
2. <span data-ttu-id="3b2f5-132">如上文所述, 查找指示的客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-132">Look up the information for the indicated client as described earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b2f5-133">请注意, 默认邮件客户端可能不会实现扩展 MAPI。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-133">Note that the default mail client might not implement Extended MAPI.</span></span> 
  
#### <a name="example"></a><span data-ttu-id="3b2f5-134">示例</span><span class="sxs-lookup"><span data-stu-id="3b2f5-134">Example</span></span>

<span data-ttu-id="3b2f5-135">若要加载 Outlook 实现的 MAPI, 请在下面`HKLM\Software\Clients\Mail\Microsoft Outlook`查找注册表项, 并将其传递给**FGetComponentPath**。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-135">To load MAPI as implemented by Outlook, look up the registry keys under  `HKLM\Software\Clients\Mail\Microsoft Outlook` and pass them to **FGetComponentPath**.</span></span> <span data-ttu-id="3b2f5-136">**FGetComponentPath**将返回 Outlook 的 MAPI 实现的路径。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-136">**FGetComponentPath** will return the path for Outlook's implementation of MAPI.</span></span> 
  
<span data-ttu-id="3b2f5-137">如果未设置 keys **MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID** , 请检查**DLLPathEx**注册表值。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-137">If the keys **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID** are not set, check the **DLLPathEx** registry value.</span></span> <span data-ttu-id="3b2f5-138">如果设置了这些项, **FGetComponentPath**将提供客户端的 MAPI 实现的路径。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-138">If the keys are set, **FGetComponentPath** gives the path of the client's implementation of MAPI.</span></span> 
  
## <a name="implementing-the-mapi-client-lookup-algorithm"></a><span data-ttu-id="3b2f5-139">实现 MAPI 客户端查找算法</span><span class="sxs-lookup"><span data-stu-id="3b2f5-139">Implementing the MAPI Client Lookup algorithm</span></span>

<span data-ttu-id="3b2f5-140">下表列出了 MFCMAPI 中的四个函数, 这些函数用于查找 MAPI 的自定义实现的路径:</span><span class="sxs-lookup"><span data-stu-id="3b2f5-140">The following table lists the four functions from MFCMAPI that are used to look up the path for a custom implementation of MAPI:</span></span>
  
|<span data-ttu-id="3b2f5-141">**函数**</span><span class="sxs-lookup"><span data-stu-id="3b2f5-141">**Function**</span></span>|<span data-ttu-id="3b2f5-142">**说明**</span><span class="sxs-lookup"><span data-stu-id="3b2f5-142">**Description**</span></span>|
|:-----|:-----|
| `GetMAPIPath` <br/> |<span data-ttu-id="3b2f5-143">获取 MAPI 库路径。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-143">Gets the MAPI library path.</span></span>  <br/> |
| `GetMailKey` <br/> |<span data-ttu-id="3b2f5-144">获取 MAPI 邮件注册表项。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-144">Gets the MAPI mail registry key.</span></span>  <br/> |
| `GetMapiMsiIds` <br/> |<span data-ttu-id="3b2f5-145">获取 Windows Installer 标识符。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-145">Gets the Windows Installer identifier.</span></span>  <br/> |
| `GetComponentPath` <br/> |<span data-ttu-id="3b2f5-146">使用[FGetComponentPath](fgetcomponentpath.md)获取组件路径。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-146">Gets the component path using [FGetComponentPath](fgetcomponentpath.md).</span></span>  <br/> |
   
<span data-ttu-id="3b2f5-147">由于默认情况下, MFCMAPI 会加载默认的 mapi 实现, 因此, 如果要使用不同的 mapi 实现, 则必须显式指导它执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-147">Because MFCMAPI loads the default implementation of MAPI by default, if you want to use a different implementation of MAPI, you must explicitly direct it to do so.</span></span> <span data-ttu-id="3b2f5-148">这是通过使用**Session\Load MAPI**例程来执行的。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-148">This is performed by using the **Session\Load MAPI** routine.</span></span> 
  
### <a name="how-these-functions-work"></a><span data-ttu-id="3b2f5-149">这些函数的工作原理</span><span class="sxs-lookup"><span data-stu-id="3b2f5-149">How these functions work</span></span>

1. <span data-ttu-id="3b2f5-150">MFCMAPI 调用`GetMAPIPath`, 为客户端参数传递 NULL, 以加载默认的 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-150">MFCMAPI calls  `GetMAPIPath`, passing NULL for the client parameter, to load the default MAPI implementation.</span></span>
    
2.  <span data-ttu-id="3b2f5-151">`GetMAPIPath`调用`GetMapiMsiIds`以读取**MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的值。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-151">`GetMAPIPath` calls  `GetMapiMsiIds` to read the values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**.</span></span>
    
3.  <span data-ttu-id="3b2f5-152">`GetMapiMsiIds`调用`GetMailKey`以打开默认邮件客户端的注册表项。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-152">`GetMapiMsiIds` calls  `GetMailKey` to open the registry key for the default mail client.</span></span> 
    
4.  <span data-ttu-id="3b2f5-153">`GetMapiMsiIds`使用`GetMailKey`返回的注册表句柄查找**MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的值。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-153">`GetMapiMsiIds` uses the registry handle returned by  `GetMailKey` to look up values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**.</span></span>
    
5. <span data-ttu-id="3b2f5-154">**MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的值将返回到`GetMAPIPath`。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-154">The values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**, are returned to  `GetMAPIPath`.</span></span>  <span data-ttu-id="3b2f5-155">`GetMAPIPath`然后将其传递`GetComponentPath`给。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-155">`GetMAPIPath` then passes them to  `GetComponentPath`.</span></span>
    
6.  <span data-ttu-id="3b2f5-156">`GetComponentPath`从系统目录中加载 MAPI 存根库 Mapi32。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-156">`GetComponentPath` loads the MAPI stub library, Mapi32.dll, from the system directory.</span></span> 
    
7.  <span data-ttu-id="3b2f5-157">`GetComponentPath`然后, 从 Mapi32 中检索**FGetComponentPath**函数的地址, 假定 Mapi32 导出**FGetComponentPath**。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-157">`GetComponentPath` then retrieves the address of the **FGetComponentPath** function from Mapi32.dll, assuming that Mapi32.dll exports **FGetComponentPath**.</span></span>
    
8. <span data-ttu-id="3b2f5-158">如果从 Mapi32 获取**FGetComponentPath**的地址失败, `GetComponentPath`则从 Mapistub 检索地址。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-158">If getting the address of **FGetComponentPath** from Mapi32.dll fails,  `GetComponentPath` retrieves the address from Mapistub.dll.</span></span> 
    
9.  <span data-ttu-id="3b2f5-159">`GetComponentPath`然后, 调用**FGetComponentPath**, 获取默认的 MAPI 版本的路径。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-159">`GetComponentPath` then calls **FGetComponentPath**, obtaining the path of the default version of MAPI.</span></span>
    
10.  <span data-ttu-id="3b2f5-160">`GetMAPIPath`然后, 将此路径返回给调用方, 然后加载 mapi 并显式链接到它, 如[链接到 MAPI 函数](how-to-link-to-mapi-functions.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-160">`GetMAPIPath` then returns this path to the caller, which then loads MAPI and explicitly links to it as described in [Link to MAPI Functions](how-to-link-to-mapi-functions.md).</span></span>
    
> [!NOTE] 
> - <span data-ttu-id="3b2f5-161">若要支持适用于英语和非英语区域设置的 MAPI 的`GetMAPIPath`本地化副本, 请阅读**MSIApplicationLCID**和**MSIOfficeLCID**子项的值。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-161">To support localized copies of MAPI for English and non-English locales,  `GetMAPIPath` reads the values for the **MSIApplicationLCID** and **MSIOfficeLCID** subkeys.</span></span>  <span data-ttu-id="3b2f5-162">`GetMAPIPath`然后调用**FGetComponentPath**, 首先将**MSIApplicationLCID**指定为**szQualifier**, 并再次将**MSIOfficeLCID**指定为**szQualifier**。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-162">`GetMAPIPath` then calls **FGetComponentPath**, first specifying **MSIApplicationLCID** as **szQualifier**, and again specifying **MSIOfficeLCID** as **szQualifier**.</span></span> <span data-ttu-id="3b2f5-163">有关支持非英语语言的邮件客户端的注册表项的详细信息, 请参阅[设置 MAPI DLL 的 MSI 密钥](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-163">For more information about registry keys for mail clients that support non-English languages, see [Setting Up the MSI Keys for Your MAPI DLL](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx).</span></span>   
> - <span data-ttu-id="3b2f5-164">如果 MFCMAPI 没有收到使用`GetMAPIPath`mapi 的路径, 它将从系统目录加载 mapi 存根库。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-164">If MFCMAPI does not receive a path for MAPI using  `GetMAPIPath`, it loads the MAPI stub library from the system directory.</span></span>
> - <span data-ttu-id="3b2f5-165">仅当使用 mapi 存根库时, 在[显式将 mapi 调用映射到 mapi dll](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx)时所讨论的**MSMapiApps**注册表值才适用。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-165">The **MSMapiApps** registry value discussed in [Explicitly Mapping MAPI Calls to MAPI DLLs](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx) only applies when the MAPI Stub library is used.</span></span> <span data-ttu-id="3b2f5-166">加载特定的 MAPI 实现或加载默认实现的应用程序不需要设置**MSMapiApps**注册表项。</span><span class="sxs-lookup"><span data-stu-id="3b2f5-166">Applications that load a specific implementation of MAPI or load the default implementation do not have to set the **MSMapiApps** registry key.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="3b2f5-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b2f5-167">See also</span></span>

- [<span data-ttu-id="3b2f5-168">FGetComponentPath</span><span class="sxs-lookup"><span data-stu-id="3b2f5-168">FGetComponentPath</span></span>](fgetcomponentpath.md)
- [<span data-ttu-id="3b2f5-169">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="3b2f5-169">MAPI Programming Overview</span></span>](mapi-programming-overview.md)
- [<span data-ttu-id="3b2f5-170">链接到 MAPI 函数</span><span class="sxs-lookup"><span data-stu-id="3b2f5-170">Link to MAPI Functions</span></span>](how-to-link-to-mapi-functions.md)
- [<span data-ttu-id="3b2f5-171">Mapi32 存根注册表设置</span><span class="sxs-lookup"><span data-stu-id="3b2f5-171">Mapi32.dll Stub Registry Settings</span></span>](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx)
- [<span data-ttu-id="3b2f5-172">为 MAPI DLL 设置 MSI 密钥</span><span class="sxs-lookup"><span data-stu-id="3b2f5-172">Setting Up the MSI Keys for Your MAPI DLL</span></span>](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)
- [<span data-ttu-id="3b2f5-173">将 mapi 调用显式映射到 mapi dll</span><span class="sxs-lookup"><span data-stu-id="3b2f5-173">Explicitly Mapping MAPI Calls to MAPI DLLs</span></span>](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx)

