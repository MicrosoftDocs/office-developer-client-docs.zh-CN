---
title: 选择要加载的 MAPI 的特定版本
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 85539a7f-74b6-4267-86ea-00da2c900c34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d0bce7b3a12f259b7ac5f28219c8a92dd2200f07
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775082"
---
# <a name="choose-a-specific-version-of-mapi-to-load"></a><span data-ttu-id="4bd88-103">选择要加载的 MAPI 的特定版本</span><span class="sxs-lookup"><span data-stu-id="4bd88-103">Choose a specific version of MAPI to load</span></span>

<span data-ttu-id="4bd88-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4bd88-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4bd88-105">显式链接到的 MAPI 实现时, 必须认真地选择要加载的实现。</span><span class="sxs-lookup"><span data-stu-id="4bd88-105">When linking explicitly to an implementation of MAPI, you must carefully select which implementation to load.</span></span> 
  
<span data-ttu-id="4bd88-106">有两种方法来显式链接到的 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="4bd88-106">There are two methods to link explicitly to an implementation of MAPI.</span></span> 
  
1. <span data-ttu-id="4bd88-107">您可以加载的 MAPI 存根库，并指定自定义 DLL 以加载并调度 MAPI 呼叫到注册表中。</span><span class="sxs-lookup"><span data-stu-id="4bd88-107">You can load the MAPI stub library, and specify in the registry a custom DLL to load and dispatch MAPI calls to.</span></span>
    
2. <span data-ttu-id="4bd88-108">您可以实现 MAPI 客户端查找算法来查找默认邮件客户端使用 MAPI 的版本和加载它。</span><span class="sxs-lookup"><span data-stu-id="4bd88-108">You can implement the MAPI client lookup algorithm to look up the version of MAPI used by the default mail client and load it.</span></span>
    
<span data-ttu-id="4bd88-109">因为您可以更改要直接应用程序使用 MAPI 任何实现的[Mapi32.dll 存根注册表设置](http://msdn.microsoft.com/en-us/library/ms531218%28EXCHG.10%29.aspx)，我们建议您将应用程序使用的测试与 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="4bd88-109">Because you can change the [Mapi32.dll Stub Registry Settings](http://msdn.microsoft.com/en-us/library/ms531218%28EXCHG.10%29.aspx) to direct your application to use any implementation of MAPI, we recommend that you direct your application to use an implementation of MAPI that you have tested with.</span></span> <span data-ttu-id="4bd88-110">下面介绍显式链接这两种的方法。</span><span class="sxs-lookup"><span data-stu-id="4bd88-110">The following describes both methods of linking explicitly.</span></span> 
  
## <a name="reading-from-the-registry"></a><span data-ttu-id="4bd88-111">注册表中读取</span><span class="sxs-lookup"><span data-stu-id="4bd88-111">Reading from the registry</span></span>

### <a name="to-read-mapi-implementation-information-from-the-registry"></a><span data-ttu-id="4bd88-112">若要从注册表中读取 MAPI 实现信息</span><span class="sxs-lookup"><span data-stu-id="4bd88-112">To read MAPI implementation information from the registry</span></span>

1. <span data-ttu-id="4bd88-113">指示邮件客户端自定义的 DLL 的注册表项位于`HKLM\Software\Clients\Mail`的邮件客户端密钥。</span><span class="sxs-lookup"><span data-stu-id="4bd88-113">The registry keys that indicate a custom DLL for a mail client are located under the  `HKLM\Software\Clients\Mail` key of the mail client.</span></span> 
    
   <span data-ttu-id="4bd88-114">下表介绍这些键：</span><span class="sxs-lookup"><span data-stu-id="4bd88-114">The following table describes these keys:</span></span>
    
   |<span data-ttu-id="4bd88-115">**键**</span><span class="sxs-lookup"><span data-stu-id="4bd88-115">**Key**</span></span>|<span data-ttu-id="4bd88-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="4bd88-116">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4bd88-117">MSIComponentID</span><span class="sxs-lookup"><span data-stu-id="4bd88-117">MSIComponentID</span></span>  <br/> |<span data-ttu-id="4bd88-118">Windows Installer PublishComponent 类别 ID (GUID) 标识导出简单 MAPI 或 MAPI DLL 调用。</span><span class="sxs-lookup"><span data-stu-id="4bd88-118">A Windows Installer PublishComponent category ID (GUID) that identifies the DLL that exports simple MAPI or MAPI calls.</span></span> <span data-ttu-id="4bd88-119">如果设置，此密钥优先于**DLLPath**或**DLLPathEx**键。</span><span class="sxs-lookup"><span data-stu-id="4bd88-119">If set, this key takes precedence over the **DLLPath** or **DLLPathEx** key.</span></span>  <br/> |
   |<span data-ttu-id="4bd88-120">MSIApplicationLCID</span><span class="sxs-lookup"><span data-stu-id="4bd88-120">MSIApplicationLCID</span></span>  <br/> |<span data-ttu-id="4bd88-121">您的应用程序的区域设置标识符 (LCID)。</span><span class="sxs-lookup"><span data-stu-id="4bd88-121">Locale identifier (LCID) for your application.</span></span> <span data-ttu-id="4bd88-122">第一个字符串值标识子键从`HKLM\Software`和后面的字符串值标识该项下的注册表值，包含区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="4bd88-122">The first string value identifies a sub-key from  `HKLM\Software` and subsequent string values identify registry values underneath this key that contain locale information.</span></span>  <br/> |
   |<span data-ttu-id="4bd88-123">MSIOfficeLCID</span><span class="sxs-lookup"><span data-stu-id="4bd88-123">MSIOfficeLCID</span></span>  <br/> |<span data-ttu-id="4bd88-124">Microsoft Office 的 Lcid。</span><span class="sxs-lookup"><span data-stu-id="4bd88-124">LCIDs for Microsoft Office.</span></span> <span data-ttu-id="4bd88-125">第一个字符串值标识子键从`HKLM\Software`和后面的字符串值标识该项下的注册表值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-125">The first string value identifies a sub-key from  `HKLM\Software` and subsequent string values identify registry values underneath this key.</span></span>  <br/> |
   
   <span data-ttu-id="4bd88-126">获取从这些项的信息。</span><span class="sxs-lookup"><span data-stu-id="4bd88-126">Obtain the information from these keys.</span></span>
    
2. <span data-ttu-id="4bd88-127">传递给[FGetComponentPath](fgetcomponentpath.md)函数获取上一步骤中的值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-127">Pass the values that you obtained from the previous step to the [FGetComponentPath](fgetcomponentpath.md) function.</span></span> <span data-ttu-id="4bd88-128">**FGetComponentPath**是由 MAPI 存根库 Mapistub.dll 导出的函数。</span><span class="sxs-lookup"><span data-stu-id="4bd88-128">**FGetComponentPath** is a function that is exported by the MAPI stub library Mapistub.dll.</span></span> <span data-ttu-id="4bd88-129">将返回自定义版本的 MAPI 的路径。</span><span class="sxs-lookup"><span data-stu-id="4bd88-129">It returns the path of the custom version of MAPI.</span></span> 


### <a name="to-load-the-implementation-of-mapi-marked-as-default"></a><span data-ttu-id="4bd88-130">若要加载的 MAPI 实现标记为默认值</span><span class="sxs-lookup"><span data-stu-id="4bd88-130">To load the implementation of MAPI marked as default</span></span>

1. <span data-ttu-id="4bd88-131">读取`HKLM\Software\Clients\Mail::(default)`注册表值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-131">Read the  `HKLM\Software\Clients\Mail::(default)` registry value.</span></span> 
    
2. <span data-ttu-id="4bd88-132">查找指示客户端的信息，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="4bd88-132">Look up the information for the indicated client as described earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4bd88-133">请注意默认邮件客户程序可能不实现扩展 MAPI。</span><span class="sxs-lookup"><span data-stu-id="4bd88-133">Note that the default mail client might not implement Extended MAPI.</span></span> 
  
#### <a name="example"></a><span data-ttu-id="4bd88-134">示例</span><span class="sxs-lookup"><span data-stu-id="4bd88-134">Example</span></span>

<span data-ttu-id="4bd88-135">若要实现的 Outlook 加载 MAPI，查找的注册表项下`HKLM\Software\Clients\Mail\Microsoft Outlook`并将它们传递给**FGetComponentPath**。</span><span class="sxs-lookup"><span data-stu-id="4bd88-135">To load MAPI as implemented by Outlook, look up the registry keys under  `HKLM\Software\Clients\Mail\Microsoft Outlook` and pass them to **FGetComponentPath**.</span></span> <span data-ttu-id="4bd88-136">**FGetComponentPath**将返回 Outlook 的 MAPI 实现的路径。</span><span class="sxs-lookup"><span data-stu-id="4bd88-136">**FGetComponentPath** will return the path for Outlook's implementation of MAPI.</span></span> 
  
<span data-ttu-id="4bd88-137">如果未设置**MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的项，检查**DLLPathEx**注册表值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-137">If the keys **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID** are not set, check the **DLLPathEx** registry value.</span></span> <span data-ttu-id="4bd88-138">如果注册表项设置， **FGetComponentPath**提供的 MAPI 客户端的实现的路径。</span><span class="sxs-lookup"><span data-stu-id="4bd88-138">If the keys are set, **FGetComponentPath** gives the path of the client's implementation of MAPI.</span></span> 
  
## <a name="implementing-the-mapi-client-lookup-algorithm"></a><span data-ttu-id="4bd88-139">实现 MAPI 客户端查找算法</span><span class="sxs-lookup"><span data-stu-id="4bd88-139">Implementing the MAPI Client Lookup algorithm</span></span>

<span data-ttu-id="4bd88-140">下表列出了用于查找 MAPI 的自定义实现的路径从 MFCMAPI 的四个函数：</span><span class="sxs-lookup"><span data-stu-id="4bd88-140">The following table lists the four functions from MFCMAPI that are used to look up the path for a custom implementation of MAPI:</span></span>
  
|<span data-ttu-id="4bd88-141">**函数**</span><span class="sxs-lookup"><span data-stu-id="4bd88-141">**Function**</span></span>|<span data-ttu-id="4bd88-142">**说明**</span><span class="sxs-lookup"><span data-stu-id="4bd88-142">**Description**</span></span>|
|:-----|:-----|
| `GetMAPIPath` <br/> |<span data-ttu-id="4bd88-143">获取 MAPI 库路径。</span><span class="sxs-lookup"><span data-stu-id="4bd88-143">Gets the MAPI library path.</span></span>  <br/> |
| `GetMailKey` <br/> |<span data-ttu-id="4bd88-144">获取 MAPI 邮件注册表项。</span><span class="sxs-lookup"><span data-stu-id="4bd88-144">Gets the MAPI mail registry key.</span></span>  <br/> |
| `GetMapiMsiIds` <br/> |<span data-ttu-id="4bd88-145">获取 Windows Installer 标识符。</span><span class="sxs-lookup"><span data-stu-id="4bd88-145">Gets the Windows Installer identifier.</span></span>  <br/> |
| `GetComponentPath` <br/> |<span data-ttu-id="4bd88-146">获取使用[FGetComponentPath](fgetcomponentpath.md)的组件路径。</span><span class="sxs-lookup"><span data-stu-id="4bd88-146">Gets the component path using [FGetComponentPath](fgetcomponentpath.md).</span></span>  <br/> |
   
<span data-ttu-id="4bd88-147">因为 MFCMAPI 加载 MAPI 的默认实现默认情况下，如果您想要使用的不同实现的 MAPI，您必须明确直接执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4bd88-147">Because MFCMAPI loads the default implementation of MAPI by default, if you want to use a different implementation of MAPI, you must explicitly direct it to do so.</span></span> <span data-ttu-id="4bd88-148">这是通过使用**Session\Load MAPI**例程执行。</span><span class="sxs-lookup"><span data-stu-id="4bd88-148">This is performed by using the **Session\Load MAPI** routine.</span></span> 
  
### <a name="how-these-functions-work"></a><span data-ttu-id="4bd88-149">这些函数的工作方式</span><span class="sxs-lookup"><span data-stu-id="4bd88-149">How these functions work</span></span>

1. <span data-ttu-id="4bd88-150">MFCMAPI 呼叫`GetMAPIPath`、 要加载的默认 MAPI 实现的客户端参数传递 null 值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-150">MFCMAPI calls  `GetMAPIPath`, passing NULL for the client parameter, to load the default MAPI implementation.</span></span>
    
2.  <span data-ttu-id="4bd88-151">`GetMAPIPath`呼叫`GetMapiMsiIds` **MSIComponentID**、 **MSIApplicationLCID**，和**MSIOfficeLCID**读取值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-151">`GetMAPIPath` calls  `GetMapiMsiIds` to read the values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**.</span></span>
    
3.  <span data-ttu-id="4bd88-152">`GetMapiMsiIds`呼叫`GetMailKey`的默认邮件客户端打开注册表项。</span><span class="sxs-lookup"><span data-stu-id="4bd88-152">`GetMapiMsiIds` calls  `GetMailKey` to open the registry key for the default mail client.</span></span> 
    
4.  <span data-ttu-id="4bd88-153">`GetMapiMsiIds`使用返回的注册表句柄`GetMailKey` **MSIComponentID**、 **MSIApplicationLCID**，和**MSIOfficeLCID**查阅值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-153">`GetMapiMsiIds` uses the registry handle returned by  `GetMailKey` to look up values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**.</span></span>
    
5. <span data-ttu-id="4bd88-154">**MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的值返回到`GetMAPIPath`。</span><span class="sxs-lookup"><span data-stu-id="4bd88-154">The values for **MSIComponentID**, **MSIApplicationLCID**, and **MSIOfficeLCID**, are returned to  `GetMAPIPath`.</span></span>  <span data-ttu-id="4bd88-155">`GetMAPIPath`然后将传递给`GetComponentPath`。</span><span class="sxs-lookup"><span data-stu-id="4bd88-155">`GetMAPIPath` then passes them to  `GetComponentPath`.</span></span>
    
6.  <span data-ttu-id="4bd88-156">`GetComponentPath`从系统目录中加载的 MAPI 存根库 Mapi32.dll。</span><span class="sxs-lookup"><span data-stu-id="4bd88-156">`GetComponentPath` loads the MAPI stub library, Mapi32.dll, from the system directory.</span></span> 
    
7.  <span data-ttu-id="4bd88-157">`GetComponentPath`然后从 Mapi32.dll，假定 Mapi32.dll 导出**FGetComponentPath**检索**FGetComponentPath**函数的地址。</span><span class="sxs-lookup"><span data-stu-id="4bd88-157">`GetComponentPath` then retrieves the address of the **FGetComponentPath** function from Mapi32.dll, assuming that Mapi32.dll exports **FGetComponentPath**.</span></span>
    
8. <span data-ttu-id="4bd88-158">如果从 Mapi32.dll 失败，获取**FGetComponentPath**的地址`GetComponentPath`Mapistub.dll 从检索的地址。</span><span class="sxs-lookup"><span data-stu-id="4bd88-158">If getting the address of **FGetComponentPath** from Mapi32.dll fails,  `GetComponentPath` retrieves the address from Mapistub.dll.</span></span> 
    
9.  <span data-ttu-id="4bd88-159">`GetComponentPath`然后调用**FGetComponentPath**，获取 MAPI 的默认版本的路径。</span><span class="sxs-lookup"><span data-stu-id="4bd88-159">`GetComponentPath` then calls **FGetComponentPath**, obtaining the path of the default version of MAPI.</span></span>
    
10.  <span data-ttu-id="4bd88-160">`GetMAPIPath`向呼叫方，然后将加载 MAPI 和显式链接到其[链接到 MAPI 函数](how-to-link-to-mapi-functions.md)中所述，则返回此路径。</span><span class="sxs-lookup"><span data-stu-id="4bd88-160">`GetMAPIPath` then returns this path to the caller, which then loads MAPI and explicitly links to it as described in [Link to MAPI Functions](how-to-link-to-mapi-functions.md).</span></span>
    
> [!NOTE] 
> - <span data-ttu-id="4bd88-161">英语和非英语区域设置支持本地化的份 MAPI`GetMAPIPath`读取**MSIApplicationLCID**和**MSIOfficeLCID**子项的值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-161">To support localized copies of MAPI for English and non-English locales,  `GetMAPIPath` reads the values for the **MSIApplicationLCID** and **MSIOfficeLCID** subkeys.</span></span>  <span data-ttu-id="4bd88-162">`GetMAPIPath`然后调用**FGetComponentPath**，首先为**szQualifier**，指定**MSIApplicationLCID**和再次指定**szQualifier** **MSIOfficeLCID** 。</span><span class="sxs-lookup"><span data-stu-id="4bd88-162">`GetMAPIPath` then calls **FGetComponentPath**, first specifying **MSIApplicationLCID** as **szQualifier**, and again specifying **MSIOfficeLCID** as **szQualifier**.</span></span> <span data-ttu-id="4bd88-163">支持非英语语言的邮件客户端的注册表项的详细信息，请参阅[设置 Up MSI 的快捷键 Your MAPI DLL](http://msdn.microsoft.com/en-us/library/ee909494%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4bd88-163">For more information about registry keys for mail clients that support non-English languages, see [Setting Up the MSI Keys for Your MAPI DLL](http://msdn.microsoft.com/en-us/library/ee909494%28VS.85%29.aspx).</span></span>   
> - <span data-ttu-id="4bd88-164">如果 MFCMAPI 不会收到 MAPI 使用路径`GetMAPIPath`，它从系统目录加载 MAPI 存根库。</span><span class="sxs-lookup"><span data-stu-id="4bd88-164">If MFCMAPI does not receive a path for MAPI using  `GetMAPIPath`, it loads the MAPI stub library from the system directory.</span></span>
> - <span data-ttu-id="4bd88-165">使用 MAPI 存根库，则仅适用于[显式映射 MAPI 调用对 MAPI Dll](http://msdn.microsoft.com/en-us/library/ee909490%28VS.85%29.aspx)中讨论的**MSMapiApps**注册表值。</span><span class="sxs-lookup"><span data-stu-id="4bd88-165">The **MSMapiApps** registry value discussed in [Explicitly Mapping MAPI Calls to MAPI DLLs](http://msdn.microsoft.com/en-us/library/ee909490%28VS.85%29.aspx) only applies when the MAPI Stub library is used.</span></span> <span data-ttu-id="4bd88-166">应用程序加载特定实施的 MAPI 或加载默认实现不必设置**MSMapiApps**注册表项。</span><span class="sxs-lookup"><span data-stu-id="4bd88-166">Applications that load a specific implementation of MAPI or load the default implementation do not have to set the **MSMapiApps** registry key.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="4bd88-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bd88-167">See also</span></span>

- [<span data-ttu-id="4bd88-168">FGetComponentPath</span><span class="sxs-lookup"><span data-stu-id="4bd88-168">FGetComponentPath</span></span>](fgetcomponentpath.md)
- [<span data-ttu-id="4bd88-169">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="4bd88-169">MAPI Programming Overview</span></span>](mapi-programming-overview.md)
- [<span data-ttu-id="4bd88-170">链接到 MAPI 函数</span><span class="sxs-lookup"><span data-stu-id="4bd88-170">Link to MAPI Functions</span></span>](how-to-link-to-mapi-functions.md)
- [<span data-ttu-id="4bd88-171">Mapi32.dll 存根注册表设置</span><span class="sxs-lookup"><span data-stu-id="4bd88-171">Mapi32.dll Stub Registry Settings</span></span>](http://msdn.microsoft.com/en-us/library/ms531218%28EXCHG.10%29.aspx)
- [<span data-ttu-id="4bd88-172">MAPI dll 设置 MSI 键</span><span class="sxs-lookup"><span data-stu-id="4bd88-172">Setting Up the MSI Keys for Your MAPI DLL</span></span>](http://msdn.microsoft.com/en-us/library/ee909494%28VS.85%29.aspx)
- [<span data-ttu-id="4bd88-173">显式映射到 MAPI Dll 的 MAPI 调用</span><span class="sxs-lookup"><span data-stu-id="4bd88-173">Explicitly Mapping MAPI Calls to MAPI DLLs</span></span>](http://msdn.microsoft.com/en-us/library/ee909490%28VS.85%29.aspx)

