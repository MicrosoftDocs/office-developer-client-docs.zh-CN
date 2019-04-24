---
title: 安装清单
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9dfb9b6d-2fb4-45bf-a12f-bd10a799ce29
description: 本主题介绍成功安装 Outlook Social Connector (.osc) 提供程序的先决条件, 并且安装将检查提供程序安装程序是否应完成正常工作。
ms.openlocfilehash: 8fec8523e57ad2678d02a0c5cbc1ad57340e5267
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286336"
---
# <a name="installation-checklist"></a><span data-ttu-id="f45bd-103">安装清单</span><span class="sxs-lookup"><span data-stu-id="f45bd-103">Installation checklist</span></span>

<span data-ttu-id="f45bd-104">本主题介绍成功安装 Outlook Social Connector (.osc) 提供程序的先决条件, 并且安装将检查提供程序安装程序是否应完成正常工作。</span><span class="sxs-lookup"><span data-stu-id="f45bd-104">This topic describes prerequisites for successfully installing an Outlook Social Connector (OSC) provider, and the installation checks that your provider installer should complete to work correctly.</span></span>
  
## <a name="installation-overview"></a><span data-ttu-id="f45bd-105">安装概述</span><span class="sxs-lookup"><span data-stu-id="f45bd-105">Installation overview</span></span>

<span data-ttu-id="f45bd-106">仅当存在支持的 Outlook 版本且在客户端计算机上安装并启用了 .osc 时, 用户才应安装 .osc 提供程序。</span><span class="sxs-lookup"><span data-stu-id="f45bd-106">Users should install OSC providers only if a supporting version of Outlook is present and the OSC is installed and enabled on the client computer.</span></span> <span data-ttu-id="f45bd-107">支持的 outlook 版本包括 office outlook 2003、office outlook 2007、Outlook 2010 和 outlook 2013 (安装在客户端计算机上, 或者在客户端计算机上由即点即用的 outlook 2010 提供)。</span><span class="sxs-lookup"><span data-stu-id="f45bd-107">Supporting versions of Outlook are Office Outlook 2003, Office Outlook 2007, Outlook 2010 and Outlook 2013 (installed on the client computer or, in the case of Outlook 2010 and Outlook 2013, delivered by Click-to-Run on the client computer).</span></span> <span data-ttu-id="f45bd-108">若要确保成功安装, 提供程序安装程序应执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f45bd-108">To ensure a successful installation, your provider installer should do the following:</span></span>
  
- <span data-ttu-id="f45bd-109">验证是否存在受支持的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="f45bd-109">Verify whether a supported version of Outlook is present.</span></span>
    
- <span data-ttu-id="f45bd-110">验证是否已安装 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-110">Verify whether the OSC is installed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f45bd-111">即点即用是一种虚拟环境, 在该环境中, outlook 2010 (32 位) 或 outlook 2013 (32-bit) 可以运行。</span><span class="sxs-lookup"><span data-stu-id="f45bd-111">Click-to-Run is a virtual environment in which Outlook 2010 (32-bit) or Outlook 2013 (32-bit) can run.</span></span> <span data-ttu-id="f45bd-112">对于 Outlook 2013, 请验证 VirtualOutlook 项是否存在于 HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook 的 Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="f45bd-112">For Outlook 2013, verify if the VirtualOutlook key exists in HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook of the Windows registry.</span></span> <span data-ttu-id="f45bd-113">有关在客户端计算机上将 outlook 作为即点即用产品进行传递的详细信息, 请参阅[如何验证 outlook 在计算机上是否可用作即点](https://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx)即用产品。</span><span class="sxs-lookup"><span data-stu-id="f45bd-113">For more information about delivering Outlook as a Click-to-Run product on a client computer, see [How to Verify if Outlook is Available on a Computer as a Click-to-Run Product](https://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx).</span></span> 
  
<span data-ttu-id="f45bd-114">但是, 用户必须确保在安装提供程序之前启用了 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-114">The user, however, has to ensure that the OSC is enabled before installing the provider.</span></span>
  
<span data-ttu-id="f45bd-115">第三方 (包括 .osc 提供程序) 无法重新发布 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-115">Third parties, including OSC providers, cannot redistribute the OSC.</span></span> <span data-ttu-id="f45bd-116">但是, 如果未安装 .osc, 则提供程序安装程序可以使用适当的 g 链接在客户端计算机上安装 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-116">However, if the OSC is not installed, the provider installer can use appropriate g-links to install the OSC on the client computer.</span></span> <span data-ttu-id="f45bd-117">g-链接是中https://g.live.com的专门构造的 URL, 可将用户转发到相应的网页以下载 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-117">A g-link is a specially constructed URL on https://g.live.com that forwards a user to a corresponding webpage to download the OSC.</span></span> <span data-ttu-id="f45bd-118">.osc g 链接的格式为https://g.live.com/0CR _lcid_/ _Glink_, 其中_LCID_和_Glink_指定客户端计算机上的 Outlook 的区域设置、版本和位数。</span><span class="sxs-lookup"><span data-stu-id="f45bd-118">An OSC g-link is formatted as https://g.live.com/0CR _LCID_/ _Glink_, where  _LCID_ and  _Glink_ specify the locale, version, and bitness of Outlook on the client computer.</span></span> <span data-ttu-id="f45bd-119">每个 g 链接指向一个可执行文件, 并特定于指定的_LCID_和_Glink_值。</span><span class="sxs-lookup"><span data-stu-id="f45bd-119">Each g-link points to an executable and is specific to the specified  _LCID_ and  _Glink_ values.</span></span> 
  
<span data-ttu-id="f45bd-120">例如, 将最新版本的 .osc for outlook 2003 或 outlook 2007 for LCID 1033 (美国英语) 的 g-链接安装如下:</span><span class="sxs-lookup"><span data-stu-id="f45bd-120">For example, the g-link to install the latest version of the OSC for Outlook 2003 or Outlook 2007 for the LCID 1033 (US English) is as follows:</span></span>
  
https://g.live.com/0CR1033/80
  
<span data-ttu-id="f45bd-121">有关 Outlook 的不同版本和位数以及受支持的区域设置的_LCID_值的详细信息, 请参阅下面的[安装清单](#olosc_InstallationOverview_InstallationChecklist)一节中的 #7 _Glink_ 。</span><span class="sxs-lookup"><span data-stu-id="f45bd-121">For details about  _Glink_ values for different versions and bitness of Outlook, and  _LCID_ values for supported locales, see #7 in the section [Installation Checklist](#olosc_InstallationOverview_InstallationChecklist) below.</span></span> 

<span data-ttu-id="f45bd-122"><a name="olosc_InstallationOverview_InstallationChecklist"> </a></span><span class="sxs-lookup"><span data-stu-id="f45bd-122"></span></span>

## <a name="installation-checklist"></a><span data-ttu-id="f45bd-123">安装清单</span><span class="sxs-lookup"><span data-stu-id="f45bd-123">Installation checklist</span></span>

<span data-ttu-id="f45bd-124">提供程序安装程序包应执行一系列安装检查 (如图1中所示), 以确保提供程序成功安装。</span><span class="sxs-lookup"><span data-stu-id="f45bd-124">The provider setup package should perform a series of installation checks, as shown in Figure 1, to ensure that the provider installs successfully.</span></span>
  
<span data-ttu-id="f45bd-125">**图1。提供程序安装逻辑**</span><span class="sxs-lookup"><span data-stu-id="f45bd-125">**Figure 1. Provider installation logic**</span></span>

![安装清单](media/odc_ol14_ta_OSC_Fig07.gif)
  
<span data-ttu-id="f45bd-127">以下过程介绍了图1中概述的安装检查。</span><span class="sxs-lookup"><span data-stu-id="f45bd-127">The following procedure describes the installation checks outlined in Figure 1.</span></span>
  
1. <span data-ttu-id="f45bd-128">作为先决条件, 请检测 outlook 是否已安装或存在, 如果已安装或存在, 则确定 outlook 版本是否支持 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-128">As a prerequisite, detect whether Outlook is installed or present, and if installed or present, determine whether the version of Outlook supports the OSC.</span></span> <span data-ttu-id="f45bd-129">有关检测已安装的 outlook 版本的详细信息, 请参阅[检查 outlook 的版本](https://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f45bd-129">For more information about detecting the installed version of Outlook, see [Check the Version of Outlook](https://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx).</span></span>
    
   - <span data-ttu-id="f45bd-130">如果安装的 outlook 版本早于 outlook 2003, 则提供程序安装过程将无法完成。</span><span class="sxs-lookup"><span data-stu-id="f45bd-130">If the installed version of Outlook is earlier than Outlook 2003, the provider installation procedure cannot complete.</span></span> <span data-ttu-id="f45bd-131">通知用户在继续安装 .osc 提供程序之前, 先获取受支持的 Outlook 和 .osc 版本。</span><span class="sxs-lookup"><span data-stu-id="f45bd-131">Inform the user to obtain a supported version of Outlook and the OSC before proceeding to install the OSC provider.</span></span>
    
   - <span data-ttu-id="f45bd-132">如果未安装 Outlook, 请继续执行步骤2。</span><span class="sxs-lookup"><span data-stu-id="f45bd-132">If Outlook is not installed, proceed to step 2.</span></span>
    
   - <span data-ttu-id="f45bd-133">如果安装了 outlook 2003 或 outlook 2007, 请继续执行步骤3。</span><span class="sxs-lookup"><span data-stu-id="f45bd-133">If Outlook 2003 or Outlook 2007 is installed, proceed to step 3.</span></span> 
    
   - <span data-ttu-id="f45bd-134">如果安装了 outlook 2010 或 outlook 2013, 请继续执行步骤4。</span><span class="sxs-lookup"><span data-stu-id="f45bd-134">If Outlook 2010 or Outlook 2013 is installed, proceed to step 4.</span></span>
    
2. <span data-ttu-id="f45bd-135">**如果客户端计算机上未安装 Outlook, 请继续执行此步骤:**</span><span class="sxs-lookup"><span data-stu-id="f45bd-135">**Proceed with this step if Outlook is not installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="f45bd-136">检查是否已将 .osc 安装为 Outlook 2010 或 outlook 2013 的即点即用安装的默认组件。</span><span class="sxs-lookup"><span data-stu-id="f45bd-136">Check whether the OSC is installed as a default component of a Click-to-Run installation of Outlook 2010 or Outlook 2013.</span></span> <span data-ttu-id="f45bd-137">检查 Windows `VirtualOutlook`注册表中以下位置中的项:</span><span class="sxs-lookup"><span data-stu-id="f45bd-137">Examine the  `VirtualOutlook` key in the following location in the Windows registry:</span></span> 
      
      - <span data-ttu-id="f45bd-138">对于 Outlook 2010,`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`</span><span class="sxs-lookup"><span data-stu-id="f45bd-138">For Outlook 2010,  `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`</span></span>
      
      - <span data-ttu-id="f45bd-139">对于 Outlook Social Connector 2013,`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`</span><span class="sxs-lookup"><span data-stu-id="f45bd-139">For Outlook Social Connector 2013,  `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`</span></span>
      
      <span data-ttu-id="f45bd-140">`VirtualOutlook`键是一个 REG_SZ 值, 它包含已安装产品的区域设置标记, 如 "en-us"。</span><span class="sxs-lookup"><span data-stu-id="f45bd-140">The  `VirtualOutlook` key is a REG_SZ value that contains the locale tag, such as "en-us", of the installed product.</span></span> 
      
   2. <span data-ttu-id="f45bd-141">如果`VirtualOutlook`该项不存在, 则客户端计算机上不存在 Outlook, 并且提供程序安装过程无法完成。</span><span class="sxs-lookup"><span data-stu-id="f45bd-141">If the  `VirtualOutlook` key does not exist, Outlook is not present on the client computer, and the provider installation procedure cannot complete.</span></span> <span data-ttu-id="f45bd-142">通知用户在继续安装 .osc 提供程序之前, 先获取受支持的 Outlook 和 .osc 版本。</span><span class="sxs-lookup"><span data-stu-id="f45bd-142">Inform the user to obtain a supported version of Outlook and the OSC before proceeding to install the OSC provider.</span></span> 
      
   3. <span data-ttu-id="f45bd-143">如果`VirtualOutlook`该项确实存在, 则通过客户端计算机上的即点即用来传递 Outlook。</span><span class="sxs-lookup"><span data-stu-id="f45bd-143">If the  `VirtualOutlook` key does exist, Outlook was delivered by Click-to-Run on the client computer.</span></span> <span data-ttu-id="f45bd-144">通过检查 Windows 注册表中以下位置中的项, `OSCVersion`继续检查已安装的 .osc 类型库的版本:</span><span class="sxs-lookup"><span data-stu-id="f45bd-144">Proceed to check the installed version of the OSC type library by examining the  `OSCVersion` key in the following location in the Windows registry:</span></span> 
      
      `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCVersion`
      
      <span data-ttu-id="f45bd-145">的值`OSCVersion`是一个字符串, 它指定类型库 Socialprovider 的版本编号 (例如, "1.0"、"1.1" 或 "15")。</span><span class="sxs-lookup"><span data-stu-id="f45bd-145">The value of  `OSCVersion` is a string that specifies the type library version number of Socialprovider.dll (for example, "1.0", "1.1", or "15").</span></span> 
      
   4. <span data-ttu-id="f45bd-146">如果`OSCVersion`是 "1.0"、"1.1" 或 "15", 则安装了适当版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-146">If  `OSCVersion` is "1.0", "1.1" or "15", an appropriate version of OSC is installed.</span></span> <span data-ttu-id="f45bd-147">继续执行步骤6以查找当前的 Outlook 用户界面区域设置, 以准备安装最新版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-147">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span> 
      
   5. <span data-ttu-id="f45bd-148">否则, `OSCVersion`不包含预期值。</span><span class="sxs-lookup"><span data-stu-id="f45bd-148">Otherwise,  `OSCVersion` does not contain an expected value.</span></span> <span data-ttu-id="f45bd-149">继续执行步骤6以查找当前 Outlook 用户界面区域设置, 以准备安装适当版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-149">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span> 
    
3. <span data-ttu-id="f45bd-150">**如果客户端计算机上安装了 outlook 2003 或 outlook 2007, 请继续执行此步骤:**</span><span class="sxs-lookup"><span data-stu-id="f45bd-150">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="f45bd-151">通过编写安装程序自定义操作来验证 .osc 是否已安装, 以测试是否存在以下限定的组件 ID:</span><span class="sxs-lookup"><span data-stu-id="f45bd-151">Verify whether the OSC is installed by writing an installer custom action to test for the existence of the following qualified component ID:</span></span>
      
      `{A3B82DA3-8AD9-4935-AEA8-54B754459483}`
      
      <span data-ttu-id="f45bd-152">限定的组件 ID 是提供单层间接寻址方法的 GUID, 类似于指针。</span><span class="sxs-lookup"><span data-stu-id="f45bd-152">The qualified component ID is a GUID that provides a method of single-level indirection, similar to a pointer.</span></span> <span data-ttu-id="f45bd-153">有关 windows installer 的详细信息, 请参阅[windows installer 文档的路线图](https://docs.microsoft.com/windows/desktop/msi/roadmap-to-windows-installer-documentation)。</span><span class="sxs-lookup"><span data-stu-id="f45bd-153">For more information about Windows Installer, see [Roadmap to Windows Installer Documentation](https://docs.microsoft.com/windows/desktop/msi/roadmap-to-windows-installer-documentation).</span></span>
      
   2. <span data-ttu-id="f45bd-154">如果指定的限定组件存在, 则会安装某个版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-154">If the specified qualified component exists, a version of the OSC is installed.</span></span> <span data-ttu-id="f45bd-155">继续执行步骤5以查找当前的 Outlook 用户界面区域设置, 以准备安装最新版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-155">Proceed to step 5 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span>
      
   3. <span data-ttu-id="f45bd-156">否则, 将不会安装 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-156">Otherwise, the OSC is not installed.</span></span> <span data-ttu-id="f45bd-157">继续执行步骤6以查找当前 Outlook 用户界面区域设置, 以准备安装适当版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-157">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span>
      
4. <span data-ttu-id="f45bd-158">**如果客户端计算机上安装了 outlook 2010 或 outlook 2013, 请继续执行此步骤:**</span><span class="sxs-lookup"><span data-stu-id="f45bd-158">**Proceed with this step if Outlook 2010 or Outlook 2013 is installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="f45bd-159">通过检查 Windows 注册表中以下位置中的`Bitness`项来确定已安装的 Outlook 版本的位数:</span><span class="sxs-lookup"><span data-stu-id="f45bd-159">Determine the bitness of the installed version of Outlook by examining the  `Bitness` key in the following location in the Windows registry:</span></span> 
      
      - <span data-ttu-id="f45bd-160">对于 Outlook 2010, 请查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`</span><span class="sxs-lookup"><span data-stu-id="f45bd-160">For Outlook 2010, look at  `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`</span></span>
      
      - <span data-ttu-id="f45bd-161">对于 Outlook 2013, 请查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`</span><span class="sxs-lookup"><span data-stu-id="f45bd-161">For Outlook 2013, look at  `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`</span></span>
      
      <span data-ttu-id="f45bd-162">对于`Bitness` 32 位 outlook, 此项为 "x86", 对于64位 outlook 为 "x64"。</span><span class="sxs-lookup"><span data-stu-id="f45bd-162">The  `Bitness` key is "x86" for 32-bit Outlook, or "x64" for 64-bit Outlook.</span></span> 
      
   2. <span data-ttu-id="f45bd-163">如果提供程序是托管提供程序, 并且您已将提供程序组件指定为 "**任何 CPU**" 的目标平台, 请继续执行步骤6以查找当前 Outlook 用户界面区域设置, 以准备安装最新版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-163">If your provider is a managed provider, and you compiled the provider component specifying the target platform as **Any CPU**, proceed with step 6 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span> <span data-ttu-id="f45bd-164">提供程序将在32位和64位版本的 .osc 上运行。</span><span class="sxs-lookup"><span data-stu-id="f45bd-164">Your provider will work on both 32-bit and 64-bit versions of the OSC.</span></span>
      
   3. <span data-ttu-id="f45bd-165">如果提供程序是本机 COM 组件, 请检查已安装的 Outlook 版本的位数:</span><span class="sxs-lookup"><span data-stu-id="f45bd-165">If your provider is a native COM component, examine the bitness of the installed version of Outlook:</span></span>
      
      - <span data-ttu-id="f45bd-166">如果安装的 Outlook 版本是32位, 则安装过程将需要安装32位提供程序 (在步骤8中), 然后再确保安装了适当的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-166">If the installed version of Outlook is 32-bit, your installation procedure will have to install a 32-bit provider (in step 8), after ensuring that an appropriate OSC is installed.</span></span>
      
      - <span data-ttu-id="f45bd-167">否则, 已安装的 Outlook 版本为64位, 安装过程将必须安装64位提供程序 (在步骤8中), 然后才能确保安装了适当的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-167">Otherwise, the installed version of Outlook is 64-bit, and your installation procedure will have to install a 64-bit provider (in step 8), after ensuring that an appropriate OSC is installed.</span></span> 
      
   4. <span data-ttu-id="f45bd-168">继续执行步骤6以查找当前 Outlook 用户界面区域设置, 以准备安装适当版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-168">Proceed with step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span>
    
5. <span data-ttu-id="f45bd-169">**如果安装了 outlook 2003 或 outlook 2007, 并且在客户端计算机上安装了 .osc, 请继续执行此步骤:** 检查 Windows 注册表中以下位置的`OSCLcid`键, 以检查当前 Outlook 用户界面区域设置:</span><span class="sxs-lookup"><span data-stu-id="f45bd-169">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed, and the OSC is installed on the client computer:** Check the current Outlook user interface locale by examining the  `OSCLcid` key in the following location in the Windows registry:</span></span> 
    
   `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCLcid`
    
   <span data-ttu-id="f45bd-170">`OSCLcid` key 是一个 DWORD 值, 它指定表示当前 Outlook 用户界面区域设置的 Internet 工程任务组 (IETF) 区域设置标记 (由[[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)定义)。</span><span class="sxs-lookup"><span data-stu-id="f45bd-170">The  `OSCLcid` key is a DWORD value that specifies the Internet Engineering Task Force (IETF) locale tag (defined by [[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt) and [[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)), that represents the current Outlook user interface locale.</span></span> <span data-ttu-id="f45bd-171">继续执行第7步, 以在客户端计算机上安装最新的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-171">Proceed with step 7 to install the latest OSC on the client computer.</span></span>
    
6. <span data-ttu-id="f45bd-172">**如果安装了 outlook 2003 或 outlook 2007, 或者 outlook 2010 或 outlook 2013 存在, 则继续执行此步骤, 但不一定要在客户端计算机上安装最新的 .osc:**</span><span class="sxs-lookup"><span data-stu-id="f45bd-172">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed, or Outlook 2010 or Outlook 2013 is present, but the latest OSC is not necessarily installed on the client computer:**</span></span>
    
   <span data-ttu-id="f45bd-173">使用**LanguageSettings**对象来确定 Outlook 用户界面区域设置的 LCID。</span><span class="sxs-lookup"><span data-stu-id="f45bd-173">Use the **LanguageSettings** object to determine the LCID of the Outlook user interface locale.</span></span> <span data-ttu-id="f45bd-174">下面的 Visual Basic 脚本编写版 (VBScript) 代码段演示如何获取 Outlook 用户界面区域设置的 LCID。</span><span class="sxs-lookup"><span data-stu-id="f45bd-174">The following Visual Basic Scripting Edition (VBScript) code snippet demonstrates how to obtain the LCID of the Outlook user interface locale.</span></span> 
    
   ```vb
    Function GetOutlookUI_LCID()
        ' Declare variables.
        Dim msoLanguageIDUI, olApp
        msoLanguageIDUI = 2
        Set olApp = CreateObject("Outlook.Application")
        ' Return Outlook UI LCID.
        GetOutlookUI_LCID = olApp.LanguageSettings.LanguageID(msoLanguageIDUI)
    End Function
   ```

7. <span data-ttu-id="f45bd-175">**如果安装程序具有已安装的 Outlook 版本的 LCID, 但不一定要在客户端计算机上安装最新的 .osc, 请继续执行此步骤:**</span><span class="sxs-lookup"><span data-stu-id="f45bd-175">**Proceed with this step if the installer has the LCID of the installed version of Outlook, but the latest OSC is not necessarily installed on the client computer:**</span></span>
    
   <span data-ttu-id="f45bd-176">将 g 链接链接到安装包, 以确保客户端计算机上安装了最新版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-176">Chain a g-link into your installation package to ensure that the latest version of the OSC is installed on the client computer.</span></span> <span data-ttu-id="f45bd-177">g 链接格式如下所示:</span><span class="sxs-lookup"><span data-stu-id="f45bd-177">The g-link format is as follows:</span></span>
    
   <span data-ttu-id="f45bd-178">https://g.live.com/0CR_LCID_/  _Glink_</span><span class="sxs-lookup"><span data-stu-id="f45bd-178">https://g.live.com/0CR _LCID_/ _Glink_</span></span>
    
   <span data-ttu-id="f45bd-179">有关支持的_LCID_值, 请参阅下面的表1和表2以获得支持的_Glink_值。</span><span class="sxs-lookup"><span data-stu-id="f45bd-179">Refer to Table 1 below for the supported  _LCID_ values, and Table 2 for the supported  _Glink_ values.</span></span> <span data-ttu-id="f45bd-180">例如, 将最新版本的32位 .osc 安装为32位 Outlook Social Connector 2013 (美国英语) 的 g-链接如下所示:</span><span class="sxs-lookup"><span data-stu-id="f45bd-180">For example, the g-link to install the latest version of the 32-bit OSC for 32-bit Outlook Social Connector 2013 (US English) is as follows:</span></span> 
    
   https://g.live.com/0CR1033/82
    
8. <span data-ttu-id="f45bd-181">安装提供程序。</span><span class="sxs-lookup"><span data-stu-id="f45bd-181">Install the provider.</span></span> <span data-ttu-id="f45bd-182">提供程序安装过程必须在相应的 Windows 注册表位置中注册编程标识符 (ProgID)。</span><span class="sxs-lookup"><span data-stu-id="f45bd-182">The provider installation procedure must register the programmatic identifier (ProgID) in the appropriate Windows registry location.</span></span> <span data-ttu-id="f45bd-183">有关详细信息, 请参阅[注册提供程序](registering-a-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="f45bd-183">For more information, see [Registering a Provider](registering-a-provider.md).</span></span> <span data-ttu-id="f45bd-184">此外, 请确保要安装的提供程序的位数与客户端计算机上存在的 Outlook 版本的位数相同。</span><span class="sxs-lookup"><span data-stu-id="f45bd-184">Also, be sure that the bitness of the provider to be installed is the same as the bitness of the version of Outlook present on the client computer.</span></span> <span data-ttu-id="f45bd-185">例如, 如果存在32位 outlook 2013, 则安装32位提供程序, 如果安装了64位 outlook 2013, 则为64位提供程序。</span><span class="sxs-lookup"><span data-stu-id="f45bd-185">For example, install a 32-bit provider if 32-bit Outlook 2013 is present, and a 64-bit provider if 64-bit Outlook 2013 is installed.</span></span> <span data-ttu-id="f45bd-186">对于 Outlook 2003 或 2007, 仅适用于32位版本的提供程序。</span><span class="sxs-lookup"><span data-stu-id="f45bd-186">For Outlook 2003 or 2007, only the 32-bit version of your provider applies.</span></span> 
    
<span data-ttu-id="f45bd-187">**表 1: 针对 .osc 的十六进制支持的区域设置和对应的 LCID 值**</span><span class="sxs-lookup"><span data-stu-id="f45bd-187">**Table 1: Supported locale and corresponding LCID values in hexadecimal for the OSC**</span></span>
  
|<span data-ttu-id="f45bd-188">**位置**</span><span class="sxs-lookup"><span data-stu-id="f45bd-188">**Locale**</span></span>|<span data-ttu-id="f45bd-189">**LCID**</span><span class="sxs-lookup"><span data-stu-id="f45bd-189">**LCID**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f45bd-190">ar-sa</span><span class="sxs-lookup"><span data-stu-id="f45bd-190">ar-sa</span></span>  <br/> |<span data-ttu-id="f45bd-191">1025</span><span class="sxs-lookup"><span data-stu-id="f45bd-191">1025</span></span>  <br/> |
|<span data-ttu-id="f45bd-192">bg-bg</span><span class="sxs-lookup"><span data-stu-id="f45bd-192">bg-bg</span></span>  <br/> |<span data-ttu-id="f45bd-193">1026</span><span class="sxs-lookup"><span data-stu-id="f45bd-193">1026</span></span>  <br/> |
|<span data-ttu-id="f45bd-194">ca-es</span><span class="sxs-lookup"><span data-stu-id="f45bd-194">ca-es</span></span>  <br/> |<span data-ttu-id="f45bd-195">1027</span><span class="sxs-lookup"><span data-stu-id="f45bd-195">1027</span></span>  <br/> |
|<span data-ttu-id="f45bd-196">cs-cz</span><span class="sxs-lookup"><span data-stu-id="f45bd-196">cs-cz</span></span>  <br/> |<span data-ttu-id="f45bd-197">1029</span><span class="sxs-lookup"><span data-stu-id="f45bd-197">1029</span></span>  <br/> |
|<span data-ttu-id="f45bd-198">da-dk</span><span class="sxs-lookup"><span data-stu-id="f45bd-198">da-dk</span></span>  <br/> |<span data-ttu-id="f45bd-199">1030</span><span class="sxs-lookup"><span data-stu-id="f45bd-199">1030</span></span>  <br/> |
|<span data-ttu-id="f45bd-200">de-de</span><span class="sxs-lookup"><span data-stu-id="f45bd-200">de-de</span></span>  <br/> |<span data-ttu-id="f45bd-201">1031</span><span class="sxs-lookup"><span data-stu-id="f45bd-201">1031</span></span>  <br/> |
|<span data-ttu-id="f45bd-202">el-gr</span><span class="sxs-lookup"><span data-stu-id="f45bd-202">el-gr</span></span>  <br/> |<span data-ttu-id="f45bd-203">1032</span><span class="sxs-lookup"><span data-stu-id="f45bd-203">1032</span></span>  <br/> |
|<span data-ttu-id="f45bd-204">en-us</span><span class="sxs-lookup"><span data-stu-id="f45bd-204">en-us</span></span>  <br/> |<span data-ttu-id="f45bd-205">1033</span><span class="sxs-lookup"><span data-stu-id="f45bd-205">1033</span></span>  <br/> |
|<span data-ttu-id="f45bd-206">es-es</span><span class="sxs-lookup"><span data-stu-id="f45bd-206">es-es</span></span>  <br/> |<span data-ttu-id="f45bd-207">3082</span><span class="sxs-lookup"><span data-stu-id="f45bd-207">3082</span></span>  <br/> |
|<span data-ttu-id="f45bd-208">et-ee</span><span class="sxs-lookup"><span data-stu-id="f45bd-208">et-ee</span></span>  <br/> |<span data-ttu-id="f45bd-209">1061</span><span class="sxs-lookup"><span data-stu-id="f45bd-209">1061</span></span>  <br/> |
|<span data-ttu-id="f45bd-210">eu-es</span><span class="sxs-lookup"><span data-stu-id="f45bd-210">eu-es</span></span>  <br/> |<span data-ttu-id="f45bd-211">1069</span><span class="sxs-lookup"><span data-stu-id="f45bd-211">1069</span></span>  <br/> |
|<span data-ttu-id="f45bd-212">fi-fi</span><span class="sxs-lookup"><span data-stu-id="f45bd-212">fi-fi</span></span>  <br/> |<span data-ttu-id="f45bd-213">1035</span><span class="sxs-lookup"><span data-stu-id="f45bd-213">1035</span></span>  <br/> |
|<span data-ttu-id="f45bd-214">fr-fr</span><span class="sxs-lookup"><span data-stu-id="f45bd-214">fr-fr</span></span>  <br/> |<span data-ttu-id="f45bd-215">1036</span><span class="sxs-lookup"><span data-stu-id="f45bd-215">1036</span></span>  <br/> |
|<span data-ttu-id="f45bd-216">gl-es</span><span class="sxs-lookup"><span data-stu-id="f45bd-216">gl-es</span></span>  <br/> |<span data-ttu-id="f45bd-217">1110</span><span class="sxs-lookup"><span data-stu-id="f45bd-217">1110</span></span>  <br/> |
|<span data-ttu-id="f45bd-218">he-il</span><span class="sxs-lookup"><span data-stu-id="f45bd-218">he-il</span></span>  <br/> |<span data-ttu-id="f45bd-219">1037</span><span class="sxs-lookup"><span data-stu-id="f45bd-219">1037</span></span>  <br/> |
|<span data-ttu-id="f45bd-220">hi-in</span><span class="sxs-lookup"><span data-stu-id="f45bd-220">hi-in</span></span>  <br/> |<span data-ttu-id="f45bd-221">1081</span><span class="sxs-lookup"><span data-stu-id="f45bd-221">1081</span></span>  <br/> |
|<span data-ttu-id="f45bd-222">hr-hr</span><span class="sxs-lookup"><span data-stu-id="f45bd-222">hr-hr</span></span>  <br/> |<span data-ttu-id="f45bd-223">1050</span><span class="sxs-lookup"><span data-stu-id="f45bd-223">1050</span></span>  <br/> |
|<span data-ttu-id="f45bd-224">hu-hu</span><span class="sxs-lookup"><span data-stu-id="f45bd-224">hu-hu</span></span>  <br/> |<span data-ttu-id="f45bd-225">1038</span><span class="sxs-lookup"><span data-stu-id="f45bd-225">1038</span></span>  <br/> |
|<span data-ttu-id="f45bd-226">it-it</span><span class="sxs-lookup"><span data-stu-id="f45bd-226">it-it</span></span>  <br/> |<span data-ttu-id="f45bd-227">1040</span><span class="sxs-lookup"><span data-stu-id="f45bd-227">1040</span></span>  <br/> |
|<span data-ttu-id="f45bd-228">ja-jp</span><span class="sxs-lookup"><span data-stu-id="f45bd-228">ja-jp</span></span>  <br/> |<span data-ttu-id="f45bd-229">1041</span><span class="sxs-lookup"><span data-stu-id="f45bd-229">1041</span></span>  <br/> |
|<span data-ttu-id="f45bd-230">kk-kz</span><span class="sxs-lookup"><span data-stu-id="f45bd-230">kk-kz</span></span>  <br/> |<span data-ttu-id="f45bd-231">1087</span><span class="sxs-lookup"><span data-stu-id="f45bd-231">1087</span></span>  <br/> |
|<span data-ttu-id="f45bd-232">ko-kr</span><span class="sxs-lookup"><span data-stu-id="f45bd-232">ko-kr</span></span>  <br/> |<span data-ttu-id="f45bd-233">1042</span><span class="sxs-lookup"><span data-stu-id="f45bd-233">1042</span></span>  <br/> |
|<span data-ttu-id="f45bd-234">lt-lt</span><span class="sxs-lookup"><span data-stu-id="f45bd-234">lt-lt</span></span>  <br/> |<span data-ttu-id="f45bd-235">1063</span><span class="sxs-lookup"><span data-stu-id="f45bd-235">1063</span></span>  <br/> |
|<span data-ttu-id="f45bd-236">lv-lv</span><span class="sxs-lookup"><span data-stu-id="f45bd-236">lv-lv</span></span>  <br/> |<span data-ttu-id="f45bd-237">1062</span><span class="sxs-lookup"><span data-stu-id="f45bd-237">1062</span></span>  <br/> |
|<span data-ttu-id="f45bd-238">nb-no</span><span class="sxs-lookup"><span data-stu-id="f45bd-238">nb-no</span></span>  <br/> |<span data-ttu-id="f45bd-239">1044</span><span class="sxs-lookup"><span data-stu-id="f45bd-239">1044</span></span>  <br/> |
|<span data-ttu-id="f45bd-240">nl-nl</span><span class="sxs-lookup"><span data-stu-id="f45bd-240">nl-nl</span></span>  <br/> |<span data-ttu-id="f45bd-241">1043</span><span class="sxs-lookup"><span data-stu-id="f45bd-241">1043</span></span>  <br/> |
|<span data-ttu-id="f45bd-242">pl-pl</span><span class="sxs-lookup"><span data-stu-id="f45bd-242">pl-pl</span></span>  <br/> |<span data-ttu-id="f45bd-243">1045</span><span class="sxs-lookup"><span data-stu-id="f45bd-243">1045</span></span>  <br/> |
|<span data-ttu-id="f45bd-244">pt-br</span><span class="sxs-lookup"><span data-stu-id="f45bd-244">pt-br</span></span>  <br/> |<span data-ttu-id="f45bd-245">1046</span><span class="sxs-lookup"><span data-stu-id="f45bd-245">1046</span></span>  <br/> |
|<span data-ttu-id="f45bd-246">pt-pt</span><span class="sxs-lookup"><span data-stu-id="f45bd-246">pt-pt</span></span>  <br/> |<span data-ttu-id="f45bd-247">2070</span><span class="sxs-lookup"><span data-stu-id="f45bd-247">2070</span></span>  <br/> |
|<span data-ttu-id="f45bd-248">ro-ro</span><span class="sxs-lookup"><span data-stu-id="f45bd-248">ro-ro</span></span>  <br/> |<span data-ttu-id="f45bd-249">1048</span><span class="sxs-lookup"><span data-stu-id="f45bd-249">1048</span></span>  <br/> |
|<span data-ttu-id="f45bd-250">ru-ru</span><span class="sxs-lookup"><span data-stu-id="f45bd-250">ru-ru</span></span>  <br/> |<span data-ttu-id="f45bd-251">1049</span><span class="sxs-lookup"><span data-stu-id="f45bd-251">1049</span></span>  <br/> |
|<span data-ttu-id="f45bd-252">sk-sk</span><span class="sxs-lookup"><span data-stu-id="f45bd-252">sk-sk</span></span>  <br/> |<span data-ttu-id="f45bd-253">1051</span><span class="sxs-lookup"><span data-stu-id="f45bd-253">1051</span></span>  <br/> |
|<span data-ttu-id="f45bd-254">sl-si</span><span class="sxs-lookup"><span data-stu-id="f45bd-254">sl-si</span></span>  <br/> |<span data-ttu-id="f45bd-255">1060</span><span class="sxs-lookup"><span data-stu-id="f45bd-255">1060</span></span>  <br/> |
|<span data-ttu-id="f45bd-256">cyrl-cs</span><span class="sxs-lookup"><span data-stu-id="f45bd-256">sr-cyrl-cs</span></span>  <br/> |<span data-ttu-id="f45bd-257">3098</span><span class="sxs-lookup"><span data-stu-id="f45bd-257">3098</span></span>  <br/> |
|<span data-ttu-id="f45bd-258">即将-cs</span><span class="sxs-lookup"><span data-stu-id="f45bd-258">sr-latn-cs</span></span>  <br/> |<span data-ttu-id="f45bd-259">2074</span><span class="sxs-lookup"><span data-stu-id="f45bd-259">2074</span></span>  <br/> |
|<span data-ttu-id="f45bd-260">sv-se</span><span class="sxs-lookup"><span data-stu-id="f45bd-260">sv-se</span></span>  <br/> |<span data-ttu-id="f45bd-261">1053</span><span class="sxs-lookup"><span data-stu-id="f45bd-261">1053</span></span>  <br/> |
|<span data-ttu-id="f45bd-262">th-th</span><span class="sxs-lookup"><span data-stu-id="f45bd-262">th-th</span></span>  <br/> |<span data-ttu-id="f45bd-263">1054</span><span class="sxs-lookup"><span data-stu-id="f45bd-263">1054</span></span>  <br/> |
|<span data-ttu-id="f45bd-264">tr-tr</span><span class="sxs-lookup"><span data-stu-id="f45bd-264">tr-tr</span></span>  <br/> |<span data-ttu-id="f45bd-265">1055</span><span class="sxs-lookup"><span data-stu-id="f45bd-265">1055</span></span>  <br/> |
|<span data-ttu-id="f45bd-266">uk-ua</span><span class="sxs-lookup"><span data-stu-id="f45bd-266">uk-ua</span></span>  <br/> |<span data-ttu-id="f45bd-267">1058</span><span class="sxs-lookup"><span data-stu-id="f45bd-267">1058</span></span>  <br/> |
|<span data-ttu-id="f45bd-268">zh-cn</span><span class="sxs-lookup"><span data-stu-id="f45bd-268">zh-cn</span></span>  <br/> |<span data-ttu-id="f45bd-269">2052</span><span class="sxs-lookup"><span data-stu-id="f45bd-269">2052</span></span>  <br/> |
|<span data-ttu-id="f45bd-270">zh-tw</span><span class="sxs-lookup"><span data-stu-id="f45bd-270">zh-tw</span></span>  <br/> |<span data-ttu-id="f45bd-271">1028</span><span class="sxs-lookup"><span data-stu-id="f45bd-271">1028</span></span>  <br/> |
   
<span data-ttu-id="f45bd-272">**表 2: 受支持的 .osc Glink 值**</span><span class="sxs-lookup"><span data-stu-id="f45bd-272">**Table 2: Supported Glink values for the OSC**</span></span>
  
|<span data-ttu-id="f45bd-273">**Glink 值**</span><span class="sxs-lookup"><span data-stu-id="f45bd-273">**Glink value**</span></span>|<span data-ttu-id="f45bd-274">**Function**</span><span class="sxs-lookup"><span data-stu-id="f45bd-274">**Function**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f45bd-275">80</span><span class="sxs-lookup"><span data-stu-id="f45bd-275">80</span></span>  <br/> |<span data-ttu-id="f45bd-276">安装适用于 outlook 2003 或 outlook 2007 的最新版本的 .osc。</span><span class="sxs-lookup"><span data-stu-id="f45bd-276">Installs the latest version of OSC for Outlook 2003 or Outlook 2007.</span></span>  <br/> |
|<span data-ttu-id="f45bd-277">82</span><span class="sxs-lookup"><span data-stu-id="f45bd-277">82</span></span>  <br/> |<span data-ttu-id="f45bd-278">安装适用于 Outlook 2007、outlook 2010 或 outlook Social Connector 2013 的32位 .osc 的最新修补程序。</span><span class="sxs-lookup"><span data-stu-id="f45bd-278">Installs the latest patch of 32-bit OSC for Outlook 2007, Outlook 2010, or Outlook Social Connector 2013.</span></span>  <br/> |
|<span data-ttu-id="f45bd-279">83</span><span class="sxs-lookup"><span data-stu-id="f45bd-279">83</span></span>  <br/> |<span data-ttu-id="f45bd-280">安装适用于 Outlook 2010 或 outlook Social Connector 2013 的64位 .osc 的最新修补程序。</span><span class="sxs-lookup"><span data-stu-id="f45bd-280">Installs the latest patch of 64-bit OSC for Outlook 2010 or Outlook Social Connector 2013.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f45bd-281">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f45bd-281">See also</span></span>

- [<span data-ttu-id="f45bd-282">注册提供程序</span><span class="sxs-lookup"><span data-stu-id="f45bd-282">Registering a Provider</span></span>](registering-a-provider.md) 
- [<span data-ttu-id="f45bd-283">学习开发提供程序的快速步骤</span><span class="sxs-lookup"><span data-stu-id="f45bd-283">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)
- [<span data-ttu-id="f45bd-284">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="f45bd-284">Deploying a Provider</span></span>](deploying-a-provider.md)

