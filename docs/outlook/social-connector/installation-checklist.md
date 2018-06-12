---
title: 安装清单
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9dfb9b6d-2fb4-45bf-a12f-bd10a799ce29
description: 本主题介绍成功安装 Outlook Social Connector (OSC) 提供程序的先决条件和安装检查提供程序安装程序应完成正常工作。
ms.openlocfilehash: cb8ed24db28c3b0e945c4db4b2daa4a2470d7dd5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779218"
---
# <a name="installation-checklist"></a><span data-ttu-id="94040-103">安装清单</span><span class="sxs-lookup"><span data-stu-id="94040-103">Installation checklist</span></span>

<span data-ttu-id="94040-104">本主题介绍成功安装 Outlook Social Connector (OSC) 提供程序的先决条件和安装检查提供程序安装程序应完成正常工作。</span><span class="sxs-lookup"><span data-stu-id="94040-104">This topic describes prerequisites for successfully installing an Outlook Social Connector (OSC) provider, and the installation checks that your provider installer should complete to work correctly.</span></span>
  
## <a name="installation-overview"></a><span data-ttu-id="94040-105">安装概述</span><span class="sxs-lookup"><span data-stu-id="94040-105">Installation overview</span></span>

<span data-ttu-id="94040-106">用户应安装 OSC 提供程序，才支持版本的 Outlook 存在和 OSC 已安装并启用客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="94040-106">Users should install OSC providers only if a supporting version of Outlook is present and the OSC is installed and enabled on the client computer.</span></span> <span data-ttu-id="94040-107">支持版本的 Outlook 的 Office Outlook 2003、 Office Outlook 2007、 Outlook 2010 和 Outlook 2013 （安装在客户端计算机，或者，对于 Outlook 2010 和 Outlook 2013，由单击即点即用分发客户端计算机上）。</span><span class="sxs-lookup"><span data-stu-id="94040-107">Supporting versions of Outlook are Office Outlook 2003, Office Outlook 2007, Outlook 2010 and Outlook 2013 (installed on the client computer or, in the case of Outlook 2010 and Outlook 2013, delivered by Click-to-Run on the client computer).</span></span> <span data-ttu-id="94040-108">若要确保成功安装，提供程序安装程序应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94040-108">To ensure a successful installation, your provider installer should do the following:</span></span>
  
- <span data-ttu-id="94040-109">验证受支持的版本的 Outlook 是否存在。</span><span class="sxs-lookup"><span data-stu-id="94040-109">Verify whether a supported version of Outlook is present.</span></span>
    
- <span data-ttu-id="94040-110">验证是否已安装 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-110">Verify whether the OSC is installed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="94040-111">单击即点即用是 Outlook 2010 （32 位） 或 Outlook 2013 (32-bit) 可以运行的虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="94040-111">Click-to-Run is a virtual environment in which Outlook 2010 (32-bit) or Outlook 2013 (32-bit) can run.</span></span> <span data-ttu-id="94040-112">Outlook 2013 的验证 HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook Windows 注册表中是否存在 VirtualOutlook 项。</span><span class="sxs-lookup"><span data-stu-id="94040-112">For Outlook 2013, verify if the VirtualOutlook key exists in HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook of the Windows registry.</span></span> <span data-ttu-id="94040-113">有关以客户端计算机上单击即点即用产品形式提供 Outlook 的详细信息，请参阅[如何验证 Outlook 是否以即点即用产品形式的计算机上提供](http://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx)。</span><span class="sxs-lookup"><span data-stu-id="94040-113">For more information about delivering Outlook as a Click-to-Run product on a client computer, see [How to Verify if Outlook is Available on a Computer as a Click-to-Run Product](http://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx).</span></span> 
  
<span data-ttu-id="94040-114">但是，用户必须确保 OSC 提供程序在安装之前已启用。</span><span class="sxs-lookup"><span data-stu-id="94040-114">The user, however, has to ensure that the OSC is enabled before installing the provider.</span></span>
  
<span data-ttu-id="94040-115">第三方，包括 OSC 提供程序不能重新发布 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-115">Third parties, including OSC providers, cannot redistribute the OSC.</span></span> <span data-ttu-id="94040-116">但是，如果未安装 OSC，提供程序安装程序可以使用适当的 g 链接客户端计算机上安装 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-116">However, if the OSC is not installed, the provider installer can use appropriate g-links to install the OSC on the client computer.</span></span> <span data-ttu-id="94040-117">G 链接专门构建的 URL 位于http://g.live.com的转发到相应的网页用户下载 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-117">A g-link is a specially constructed URL on http://g.live.com that forwards a user to a corresponding webpage to download the OSC.</span></span> <span data-ttu-id="94040-118">OSC g 链接的格式设置为http://g.live.com/0CR _LCID_/ _Glink_，其中_LCID_和_Glink_指定区域设置、 版本和 Outlook 客户端计算机上的位数。</span><span class="sxs-lookup"><span data-stu-id="94040-118">An OSC g-link is formatted as http://g.live.com/0CR _LCID_/ _Glink_, where  _LCID_ and  _Glink_ specify the locale, version, and bitness of Outlook on the client computer.</span></span> <span data-ttu-id="94040-119">每个 g 链接指向可执行文件和特定于指定的_LCID_和_Glink_值。</span><span class="sxs-lookup"><span data-stu-id="94040-119">Each g-link points to an executable and is specific to the specified  _LCID_ and  _Glink_ values.</span></span> 
  
<span data-ttu-id="94040-120">例如，g 链接以安装用于 Outlook 2003 OSC 或 LCID 1033 英语 （美国） 的 Outlook 2007 的最新版本的是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="94040-120">For example, the g-link to install the latest version of the OSC for Outlook 2003 or Outlook 2007 for the LCID 1033 (US English) is as follows:</span></span>
  
http://g.live.com/0CR1033/80
  
<span data-ttu-id="94040-121">有关不同版本和位数的 Outlook， _Glink_值和支持的区域设置的_LCID_值的详细信息，请参阅[安装清单](#olosc_InstallationOverview_InstallationChecklist)下面一节中的 #7。</span><span class="sxs-lookup"><span data-stu-id="94040-121">For details about  _Glink_ values for different versions and bitness of Outlook, and  _LCID_ values for supported locales, see #7 in the section [Installation Checklist](#olosc_InstallationOverview_InstallationChecklist) below.</span></span> 

<span data-ttu-id="94040-122"><a name="olosc_InstallationOverview_InstallationChecklist"> </a></span><span class="sxs-lookup"><span data-stu-id="94040-122"></span></span>

## <a name="installation-checklist"></a><span data-ttu-id="94040-123">安装清单</span><span class="sxs-lookup"><span data-stu-id="94040-123">Installation checklist</span></span>

<span data-ttu-id="94040-124">提供程序安装程序包应执行一系列安装检查以确保提供程序成功安装图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="94040-124">The provider setup package should perform a series of installation checks, as shown in Figure 1, to ensure that the provider installs successfully.</span></span>
  
<span data-ttu-id="94040-125">**图 1。提供程序安装逻辑**</span><span class="sxs-lookup"><span data-stu-id="94040-125">**Figure 1. Provider installation logic**</span></span>

![安装清单](media/odc_ol14_ta_OSC_Fig07.gif)
  
<span data-ttu-id="94040-127">以下过程介绍安装检查图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="94040-127">The following procedure describes the installation checks outlined in Figure 1.</span></span>
  
1. <span data-ttu-id="94040-128">作为先决条件，检测是否安装了 Outlook 或存在，并且如果已安装或存在此参数，确定 Outlook 版本是否支持 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-128">As a prerequisite, detect whether Outlook is installed or present, and if installed or present, determine whether the version of Outlook supports the OSC.</span></span> <span data-ttu-id="94040-129">检测已安装的 Outlook 版本的详细信息，请参阅[检查 Outlook 版本](http://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="94040-129">For more information about detecting the installed version of Outlook, see [Check the Version of Outlook](http://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx).</span></span>
    
   - <span data-ttu-id="94040-130">如果安装的 Outlook 版本早于 Outlook 2003，无法完成的提供程序安装过程。</span><span class="sxs-lookup"><span data-stu-id="94040-130">If the installed version of Outlook is earlier than Outlook 2003, the provider installation procedure cannot complete.</span></span> <span data-ttu-id="94040-131">通知用户获取 Outlook 和然后再继续 OSC 安装 OSC 提供程序的受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="94040-131">Inform the user to obtain a supported version of Outlook and the OSC before proceeding to install the OSC provider.</span></span>
    
   - <span data-ttu-id="94040-132">如果未安装 Outlook，继续执行步骤 2。</span><span class="sxs-lookup"><span data-stu-id="94040-132">If Outlook is not installed, proceed to step 2.</span></span>
    
   - <span data-ttu-id="94040-133">如果安装了 Outlook 2003 或 Outlook 2007，继续执行步骤 3。</span><span class="sxs-lookup"><span data-stu-id="94040-133">If Outlook 2003 or Outlook 2007 is installed, proceed to step 3.</span></span> 
    
   - <span data-ttu-id="94040-134">如果安装了 Outlook 2010 或 Outlook 2013，请继续步骤 4。</span><span class="sxs-lookup"><span data-stu-id="94040-134">If Outlook 2010 or Outlook 2013 is installed, proceed to step 4.</span></span>
    
2. <span data-ttu-id="94040-135">**如果客户端计算机上未安装 Outlook，则继续此步骤：**</span><span class="sxs-lookup"><span data-stu-id="94040-135">**Proceed with this step if Outlook is not installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="94040-136">检查是否为默认组件单击即点即用安装 Outlook 2010 或 Outlook 2013 的安装 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-136">Check whether the OSC is installed as a default component of a Click-to-Run installation of Outlook 2010 or Outlook 2013.</span></span> <span data-ttu-id="94040-137">检查`VirtualOutlook`Windows 注册表中的以下位置中的键：</span><span class="sxs-lookup"><span data-stu-id="94040-137">Examine the  `VirtualOutlook` key in the following location in the Windows registry:</span></span> 
      
      - <span data-ttu-id="94040-138">Outlook 2010`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`</span><span class="sxs-lookup"><span data-stu-id="94040-138">For Outlook 2010,  `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`</span></span>
      
      - <span data-ttu-id="94040-139">为 Outlook Social Connector 2013`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`</span><span class="sxs-lookup"><span data-stu-id="94040-139">For Outlook Social Connector 2013,  `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`</span></span>
      
      <span data-ttu-id="94040-140">`VirtualOutlook`项是一个 REG_SZ 值，包含区域设置标记，如"en-我们"，已安装的产品。</span><span class="sxs-lookup"><span data-stu-id="94040-140">The  `VirtualOutlook` key is a REG_SZ value that contains the locale tag, such as "en-us", of the installed product.</span></span> 
      
   2. <span data-ttu-id="94040-141">如果`VirtualOutlook`项不存在，Outlook 不存在的客户端计算机上，并提供程序安装过程无法完成。</span><span class="sxs-lookup"><span data-stu-id="94040-141">If the  `VirtualOutlook` key does not exist, Outlook is not present on the client computer, and the provider installation procedure cannot complete.</span></span> <span data-ttu-id="94040-142">通知用户获取 Outlook 和然后再继续 OSC 安装 OSC 提供程序的受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="94040-142">Inform the user to obtain a supported version of Outlook and the OSC before proceeding to install the OSC provider.</span></span> 
      
   3. <span data-ttu-id="94040-143">如果`VirtualOutlook`密钥是否存在、 Outlook 已由单击即点即用分发客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="94040-143">If the  `VirtualOutlook` key does exist, Outlook was delivered by Click-to-Run on the client computer.</span></span> <span data-ttu-id="94040-144">继续通过检查检查安装的 OSC 类型库的版本`OSCVersion`Windows 注册表中的以下位置中的键：</span><span class="sxs-lookup"><span data-stu-id="94040-144">Proceed to check the installed version of the OSC type library by examining the  `OSCVersion` key in the following location in the Windows registry:</span></span> 
      
      `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCVersion`
      
      <span data-ttu-id="94040-145">值`OSCVersion`是一个字符串，指定 Socialprovider.dll （例如，"1.0"、"1.1"或"15"） 的类型库版本号。</span><span class="sxs-lookup"><span data-stu-id="94040-145">The value of  `OSCVersion` is a string that specifies the type library version number of Socialprovider.dll (for example, "1.0", "1.1", or "15").</span></span> 
      
   4. <span data-ttu-id="94040-146">如果`OSCVersion`"1.0"、"1.1"15"，安装相应版本的 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-146">If  `OSCVersion` is "1.0", "1.1" or "15", an appropriate version of OSC is installed.</span></span> <span data-ttu-id="94040-147">继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装 OSC 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="94040-147">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span> 
      
   5. <span data-ttu-id="94040-148">否则为`OSCVersion`不包含预期值。</span><span class="sxs-lookup"><span data-stu-id="94040-148">Otherwise,  `OSCVersion` does not contain an expected value.</span></span> <span data-ttu-id="94040-149">继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装相应版本 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-149">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span> 
    
3. <span data-ttu-id="94040-150">**如果客户端计算机上安装了 Outlook 2003 或 Outlook 2007，则继续此步骤：**</span><span class="sxs-lookup"><span data-stu-id="94040-150">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="94040-151">验证是否安装了 OSC 通过编写安装程序测试是否存在以下限定的组件 ID 的自定义操作：</span><span class="sxs-lookup"><span data-stu-id="94040-151">Verify whether the OSC is installed by writing an installer custom action to test for the existence of the following qualified component ID:</span></span>
      
      `{A3B82DA3-8AD9-4935-AEA8-54B754459483}`
      
      <span data-ttu-id="94040-152">限定的组件 ID 是一种方法的单级间接寻址，类似于指针的 GUID。</span><span class="sxs-lookup"><span data-stu-id="94040-152">The qualified component ID is a GUID that provides a method of single-level indirection, similar to a pointer.</span></span> <span data-ttu-id="94040-153">有关 Windows Installer 的详细信息，请参阅[Windows Installer 文档路线图](http://msdn.microsoft.com/library/_msi_roadmap_to_windows_installer_documentation.aspx)。</span><span class="sxs-lookup"><span data-stu-id="94040-153">For more information about Windows Installer, see [Roadmap to Windows Installer Documentation](http://msdn.microsoft.com/library/_msi_roadmap_to_windows_installer_documentation.aspx).</span></span>
      
   2. <span data-ttu-id="94040-154">如果存在指定合格的组件，安装 OSC 的版本。</span><span class="sxs-lookup"><span data-stu-id="94040-154">If the specified qualified component exists, a version of the OSC is installed.</span></span> <span data-ttu-id="94040-155">继续执行步骤 5 以查找当前的 Outlook 用户界面区域，准备安装 OSC 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="94040-155">Proceed to step 5 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span>
      
   3. <span data-ttu-id="94040-156">否则，未安装 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-156">Otherwise, the OSC is not installed.</span></span> <span data-ttu-id="94040-157">继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装相应版本 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-157">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span>
      
4. <span data-ttu-id="94040-158">**如果客户端计算机上安装了 Outlook 2010 或 Outlook 2013，继续此步骤：**</span><span class="sxs-lookup"><span data-stu-id="94040-158">**Proceed with this step if Outlook 2010 or Outlook 2013 is installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="94040-159">通过检查确定安装的 Outlook 版本位数`Bitness`Windows 注册表中的以下位置中的键：</span><span class="sxs-lookup"><span data-stu-id="94040-159">Determine the bitness of the installed version of Outlook by examining the  `Bitness` key in the following location in the Windows registry:</span></span> 
      
      - <span data-ttu-id="94040-160">为 Outlook 2010 中，查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`</span><span class="sxs-lookup"><span data-stu-id="94040-160">For Outlook 2010, look at  `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`</span></span>
      
      - <span data-ttu-id="94040-161">为 Outlook 2013 一下`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`</span><span class="sxs-lookup"><span data-stu-id="94040-161">For Outlook 2013, look at  `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`</span></span>
      
      <span data-ttu-id="94040-162">`Bitness`密钥是 32 位 Outlook 或 64 位 outlook 的"x64"的"x86"。</span><span class="sxs-lookup"><span data-stu-id="94040-162">The  `Bitness` key is "x86" for 32-bit Outlook, or "x64" for 64-bit Outlook.</span></span> 
      
   2. <span data-ttu-id="94040-163">如果您的提供商托管提供程序，并且编译为**任何 CPU**指定目标平台的提供程序组件，继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装 OSC 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="94040-163">If your provider is a managed provider, and you compiled the provider component specifying the target platform as **Any CPU**, proceed with step 6 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span> <span data-ttu-id="94040-164">将用于 32 位和 64 位版本的 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="94040-164">Your provider will work on both 32-bit and 64-bit versions of the OSC.</span></span>
      
   3. <span data-ttu-id="94040-165">如果您的提供商是本机 COM 组件，检查安装的 Outlook 版本的位：</span><span class="sxs-lookup"><span data-stu-id="94040-165">If your provider is a native COM component, examine the bitness of the installed version of Outlook:</span></span>
      
      - <span data-ttu-id="94040-166">如果安装的 Outlook 版本，32 位安装过程将需要确保安装了相应 OSC 后安装 32 位 （在步骤 8），提供程序。</span><span class="sxs-lookup"><span data-stu-id="94040-166">If the installed version of Outlook is 32-bit, your installation procedure will have to install a 32-bit provider (in step 8), after ensuring that an appropriate OSC is installed.</span></span>
      
      - <span data-ttu-id="94040-167">否则为安装的 Outlook 版本是 64 位，并且安装过程必须确保安装了相应 OSC 后安装 64 位 （在步骤 8），提供程序。</span><span class="sxs-lookup"><span data-stu-id="94040-167">Otherwise, the installed version of Outlook is 64-bit, and your installation procedure will have to install a 64-bit provider (in step 8), after ensuring that an appropriate OSC is installed.</span></span> 
      
   4. <span data-ttu-id="94040-168">继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装相应版本 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-168">Proceed with step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span>
    
5. <span data-ttu-id="94040-169">**继续此步骤，如果安装了 Outlook 2003 或 Outlook 2007，并且客户端计算机上安装 OSC:** 通过检查检查当前 Outlook 用户界面的区域设置`OSCLcid`Windows 注册表中的以下位置中的键：</span><span class="sxs-lookup"><span data-stu-id="94040-169">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed, and the OSC is installed on the client computer:** Check the current Outlook user interface locale by examining the  `OSCLcid` key in the following location in the Windows registry:</span></span> 
    
   `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCLcid`
    
   <span data-ttu-id="94040-170">`OSCLcid`项是一个 DWORD 值，该值指定 （由[[RFC4646]](http://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](http://www.ietf.org/rfc/rfc4647.txt)定义） 的 Internet 工程任务组 (IETF) 区域设置标记，表示当前 Outlook 用户界面的区域设置。</span><span class="sxs-lookup"><span data-stu-id="94040-170">The  `OSCLcid` key is a DWORD value that specifies the Internet Engineering Task Force (IETF) locale tag (defined by [[RFC4646]](http://www.ietf.org/rfc/rfc4646.txt) and [[RFC4647]](http://www.ietf.org/rfc/rfc4647.txt)), that represents the current Outlook user interface locale.</span></span> <span data-ttu-id="94040-171">继续步骤 7 客户端计算机上安装最新 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-171">Proceed with step 7 to install the latest OSC on the client computer.</span></span>
    
6. <span data-ttu-id="94040-172">**如果安装了 Outlook 2003 或 Outlook 2007，或 Outlook 2010 或 Outlook 2013 已存在此参数，但未最新 OSC 一定客户端计算机上安装，则继续此步骤：**</span><span class="sxs-lookup"><span data-stu-id="94040-172">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed, or Outlook 2010 or Outlook 2013 is present, but the latest OSC is not necessarily installed on the client computer:**</span></span>
    
   <span data-ttu-id="94040-173">使用**LanguageSettings**对象确定 Outlook 用户界面区域设置的 LCID。</span><span class="sxs-lookup"><span data-stu-id="94040-173">Use the **LanguageSettings** object to determine the LCID of the Outlook user interface locale.</span></span> <span data-ttu-id="94040-174">下面的 Visual Basic Scripting Edition (VBScript) 代码段演示如何获取 Outlook 用户界面区域设置的 LCID。</span><span class="sxs-lookup"><span data-stu-id="94040-174">The following Visual Basic Scripting Edition (VBScript) code snippet demonstrates how to obtain the LCID of the Outlook user interface locale.</span></span> 
    
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

7. <span data-ttu-id="94040-175">**如果安装程序已安装的 Outlook 版本的 LCID 但未最新 OSC 一定客户端计算机上安装，则继续此步骤：**</span><span class="sxs-lookup"><span data-stu-id="94040-175">**Proceed with this step if the installer has the LCID of the installed version of Outlook, but the latest OSC is not necessarily installed on the client computer:**</span></span>
    
   <span data-ttu-id="94040-176">链接到您安装的程序包以确保客户端计算机上安装了最新版本的 OSC g 链接。</span><span class="sxs-lookup"><span data-stu-id="94040-176">Chain a g-link into your installation package to ensure that the latest version of the OSC is installed on the client computer.</span></span> <span data-ttu-id="94040-177">G 链接格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="94040-177">The g-link format is as follows:</span></span>
    
   <span data-ttu-id="94040-178">http://g.live.com/0CR_LCID_/  _Glink_</span><span class="sxs-lookup"><span data-stu-id="94040-178">http://g.live.com/0CR _LCID_/ _Glink_</span></span>
    
   <span data-ttu-id="94040-179">请参阅下面的受支持的_LCID_值的表 1 和表 2 的受支持的_Glink_值。</span><span class="sxs-lookup"><span data-stu-id="94040-179">Refer to Table 1 below for the supported  _LCID_ values, and Table 2 for the supported  _Glink_ values.</span></span> <span data-ttu-id="94040-180">例如，g 链接以安装 32 位 Outlook Social Connector 2013 英语 （美国） 的最新版本的 32 位 OSC 如下所示：</span><span class="sxs-lookup"><span data-stu-id="94040-180">For example, the g-link to install the latest version of the 32-bit OSC for 32-bit Outlook Social Connector 2013 (US English) is as follows:</span></span> 
    
   http://g.live.com/0CR1033/82
    
8. <span data-ttu-id="94040-181">安装提供程序。</span><span class="sxs-lookup"><span data-stu-id="94040-181">Install the provider.</span></span> <span data-ttu-id="94040-182">提供程序安装过程必须在相应的 Windows 注册表位置中注册的编程标识符 (ProgID)。</span><span class="sxs-lookup"><span data-stu-id="94040-182">The provider installation procedure must register the programmatic identifier (ProgID) in the appropriate Windows registry location.</span></span> <span data-ttu-id="94040-183">有关详细信息，请参阅[注册提供程序](registering-a-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="94040-183">For more information, see [Registering a Provider](registering-a-provider.md).</span></span> <span data-ttu-id="94040-184">另外，确保要安装的提供程序的位数是相同的客户端计算机上存在的 Outlook 版本的位数。</span><span class="sxs-lookup"><span data-stu-id="94040-184">Also, be sure that the bitness of the provider to be installed is the same as the bitness of the version of Outlook present on the client computer.</span></span> <span data-ttu-id="94040-185">例如，如果安装 64 位 Outlook 2013 安装 32 位提供程序是否存在此参数，32 位 Outlook 2013 和 64 位提供程序。</span><span class="sxs-lookup"><span data-stu-id="94040-185">For example, install a 32-bit provider if 32-bit Outlook 2013 is present, and a 64-bit provider if 64-bit Outlook 2013 is installed.</span></span> <span data-ttu-id="94040-186">对于 Outlook 2003 或 2007年，您的提供商的 32 位版本适用。</span><span class="sxs-lookup"><span data-stu-id="94040-186">For Outlook 2003 or 2007, only the 32-bit version of your provider applies.</span></span> 
    
<span data-ttu-id="94040-187">**表 1： 支持的区域设置和 OSC 的十六进制数中相应的 LCID 值**</span><span class="sxs-lookup"><span data-stu-id="94040-187">**Table 1: Supported locale and corresponding LCID values in hexadecimal for the OSC**</span></span>
  
|<span data-ttu-id="94040-188">**区域设置**</span><span class="sxs-lookup"><span data-stu-id="94040-188">**Locale**</span></span>|<span data-ttu-id="94040-189">**LCID**</span><span class="sxs-lookup"><span data-stu-id="94040-189">**LCID**</span></span>|
|:-----|:-----|
|<span data-ttu-id="94040-190">ar-sa</span><span class="sxs-lookup"><span data-stu-id="94040-190">ar-sa</span></span>  <br/> |<span data-ttu-id="94040-191">1025</span><span class="sxs-lookup"><span data-stu-id="94040-191">1025</span></span>  <br/> |
|<span data-ttu-id="94040-192">bg-bg</span><span class="sxs-lookup"><span data-stu-id="94040-192">bg-bg</span></span>  <br/> |<span data-ttu-id="94040-193">1026</span><span class="sxs-lookup"><span data-stu-id="94040-193">1026</span></span>  <br/> |
|<span data-ttu-id="94040-194">ca es</span><span class="sxs-lookup"><span data-stu-id="94040-194">ca-es</span></span>  <br/> |<span data-ttu-id="94040-195">1027</span><span class="sxs-lookup"><span data-stu-id="94040-195">1027</span></span>  <br/> |
|<span data-ttu-id="94040-196">cs-cz</span><span class="sxs-lookup"><span data-stu-id="94040-196">cs-cz</span></span>  <br/> |<span data-ttu-id="94040-197">1029</span><span class="sxs-lookup"><span data-stu-id="94040-197">1029</span></span>  <br/> |
|<span data-ttu-id="94040-198">da-dk</span><span class="sxs-lookup"><span data-stu-id="94040-198">da-dk</span></span>  <br/> |<span data-ttu-id="94040-199">1030</span><span class="sxs-lookup"><span data-stu-id="94040-199">1030</span></span>  <br/> |
|<span data-ttu-id="94040-200">de-de</span><span class="sxs-lookup"><span data-stu-id="94040-200">de-de</span></span>  <br/> |<span data-ttu-id="94040-201">1031</span><span class="sxs-lookup"><span data-stu-id="94040-201">1031</span></span>  <br/> |
|<span data-ttu-id="94040-202">el-gr</span><span class="sxs-lookup"><span data-stu-id="94040-202">el-gr</span></span>  <br/> |<span data-ttu-id="94040-203">1032</span><span class="sxs-lookup"><span data-stu-id="94040-203">1032</span></span>  <br/> |
|<span data-ttu-id="94040-204">en-us</span><span class="sxs-lookup"><span data-stu-id="94040-204">en-us</span></span>  <br/> |<span data-ttu-id="94040-205">1033</span><span class="sxs-lookup"><span data-stu-id="94040-205">1033</span></span>  <br/> |
|<span data-ttu-id="94040-206">es-es</span><span class="sxs-lookup"><span data-stu-id="94040-206">es-es</span></span>  <br/> |<span data-ttu-id="94040-207">3082</span><span class="sxs-lookup"><span data-stu-id="94040-207">3082</span></span>  <br/> |
|<span data-ttu-id="94040-208">et-ee</span><span class="sxs-lookup"><span data-stu-id="94040-208">et-ee</span></span>  <br/> |<span data-ttu-id="94040-209">1061</span><span class="sxs-lookup"><span data-stu-id="94040-209">1061</span></span>  <br/> |
|<span data-ttu-id="94040-210">欧盟 es</span><span class="sxs-lookup"><span data-stu-id="94040-210">eu-es</span></span>  <br/> |<span data-ttu-id="94040-211">1069</span><span class="sxs-lookup"><span data-stu-id="94040-211">1069</span></span>  <br/> |
|<span data-ttu-id="94040-212">fi-fi</span><span class="sxs-lookup"><span data-stu-id="94040-212">fi-fi</span></span>  <br/> |<span data-ttu-id="94040-213">1035</span><span class="sxs-lookup"><span data-stu-id="94040-213">1035</span></span>  <br/> |
|<span data-ttu-id="94040-214">fr-fr</span><span class="sxs-lookup"><span data-stu-id="94040-214">fr-fr</span></span>  <br/> |<span data-ttu-id="94040-215">1036</span><span class="sxs-lookup"><span data-stu-id="94040-215">1036</span></span>  <br/> |
|<span data-ttu-id="94040-216">总帐 es</span><span class="sxs-lookup"><span data-stu-id="94040-216">gl-es</span></span>  <br/> |<span data-ttu-id="94040-217">1110</span><span class="sxs-lookup"><span data-stu-id="94040-217">1110</span></span>  <br/> |
|<span data-ttu-id="94040-218">he-il</span><span class="sxs-lookup"><span data-stu-id="94040-218">he-il</span></span>  <br/> |<span data-ttu-id="94040-219">1037</span><span class="sxs-lookup"><span data-stu-id="94040-219">1037</span></span>  <br/> |
|<span data-ttu-id="94040-220">hi-in</span><span class="sxs-lookup"><span data-stu-id="94040-220">hi-in</span></span>  <br/> |<span data-ttu-id="94040-221">1081</span><span class="sxs-lookup"><span data-stu-id="94040-221">1081</span></span>  <br/> |
|<span data-ttu-id="94040-222">hr-hr</span><span class="sxs-lookup"><span data-stu-id="94040-222">hr-hr</span></span>  <br/> |<span data-ttu-id="94040-223">1050</span><span class="sxs-lookup"><span data-stu-id="94040-223">1050</span></span>  <br/> |
|<span data-ttu-id="94040-224">hu-hu</span><span class="sxs-lookup"><span data-stu-id="94040-224">hu-hu</span></span>  <br/> |<span data-ttu-id="94040-225">1038</span><span class="sxs-lookup"><span data-stu-id="94040-225">1038</span></span>  <br/> |
|<span data-ttu-id="94040-226">it-it</span><span class="sxs-lookup"><span data-stu-id="94040-226">it-it</span></span>  <br/> |<span data-ttu-id="94040-227">1040</span><span class="sxs-lookup"><span data-stu-id="94040-227">1040</span></span>  <br/> |
|<span data-ttu-id="94040-228">ja-jp</span><span class="sxs-lookup"><span data-stu-id="94040-228">ja-jp</span></span>  <br/> |<span data-ttu-id="94040-229">1041</span><span class="sxs-lookup"><span data-stu-id="94040-229">1041</span></span>  <br/> |
|<span data-ttu-id="94040-230">kk-kz</span><span class="sxs-lookup"><span data-stu-id="94040-230">kk-kz</span></span>  <br/> |<span data-ttu-id="94040-231">1087</span><span class="sxs-lookup"><span data-stu-id="94040-231">1087</span></span>  <br/> |
|<span data-ttu-id="94040-232">ko-kr</span><span class="sxs-lookup"><span data-stu-id="94040-232">ko-kr</span></span>  <br/> |<span data-ttu-id="94040-233">1042</span><span class="sxs-lookup"><span data-stu-id="94040-233">1042</span></span>  <br/> |
|<span data-ttu-id="94040-234">lt-lt</span><span class="sxs-lookup"><span data-stu-id="94040-234">lt-lt</span></span>  <br/> |<span data-ttu-id="94040-235">1063</span><span class="sxs-lookup"><span data-stu-id="94040-235">1063</span></span>  <br/> |
|<span data-ttu-id="94040-236">lv-lv</span><span class="sxs-lookup"><span data-stu-id="94040-236">lv-lv</span></span>  <br/> |<span data-ttu-id="94040-237">1062</span><span class="sxs-lookup"><span data-stu-id="94040-237">1062</span></span>  <br/> |
|<span data-ttu-id="94040-238">nb-no</span><span class="sxs-lookup"><span data-stu-id="94040-238">nb-no</span></span>  <br/> |<span data-ttu-id="94040-239">1044</span><span class="sxs-lookup"><span data-stu-id="94040-239">1044</span></span>  <br/> |
|<span data-ttu-id="94040-240">nl-nl</span><span class="sxs-lookup"><span data-stu-id="94040-240">nl-nl</span></span>  <br/> |<span data-ttu-id="94040-241">1043</span><span class="sxs-lookup"><span data-stu-id="94040-241">1043</span></span>  <br/> |
|<span data-ttu-id="94040-242">pl-pl</span><span class="sxs-lookup"><span data-stu-id="94040-242">pl-pl</span></span>  <br/> |<span data-ttu-id="94040-243">1045</span><span class="sxs-lookup"><span data-stu-id="94040-243">1045</span></span>  <br/> |
|<span data-ttu-id="94040-244">pt-br</span><span class="sxs-lookup"><span data-stu-id="94040-244">pt-br</span></span>  <br/> |<span data-ttu-id="94040-245">1046</span><span class="sxs-lookup"><span data-stu-id="94040-245">1046</span></span>  <br/> |
|<span data-ttu-id="94040-246">pt-pt</span><span class="sxs-lookup"><span data-stu-id="94040-246">pt-pt</span></span>  <br/> |<span data-ttu-id="94040-247">2070</span><span class="sxs-lookup"><span data-stu-id="94040-247">2070</span></span>  <br/> |
|<span data-ttu-id="94040-248">ro-ro</span><span class="sxs-lookup"><span data-stu-id="94040-248">ro-ro</span></span>  <br/> |<span data-ttu-id="94040-249">1048</span><span class="sxs-lookup"><span data-stu-id="94040-249">1048</span></span>  <br/> |
|<span data-ttu-id="94040-250">ru-ru</span><span class="sxs-lookup"><span data-stu-id="94040-250">ru-ru</span></span>  <br/> |<span data-ttu-id="94040-251">1049</span><span class="sxs-lookup"><span data-stu-id="94040-251">1049</span></span>  <br/> |
|<span data-ttu-id="94040-252">sk-sk</span><span class="sxs-lookup"><span data-stu-id="94040-252">sk-sk</span></span>  <br/> |<span data-ttu-id="94040-253">1051</span><span class="sxs-lookup"><span data-stu-id="94040-253">1051</span></span>  <br/> |
|<span data-ttu-id="94040-254">sl-si</span><span class="sxs-lookup"><span data-stu-id="94040-254">sl-si</span></span>  <br/> |<span data-ttu-id="94040-255">1060</span><span class="sxs-lookup"><span data-stu-id="94040-255">1060</span></span>  <br/> |
|<span data-ttu-id="94040-256">sr-符号 cs</span><span class="sxs-lookup"><span data-stu-id="94040-256">sr-cyrl-cs</span></span>  <br/> |<span data-ttu-id="94040-257">3098</span><span class="sxs-lookup"><span data-stu-id="94040-257">3098</span></span>  <br/> |
|<span data-ttu-id="94040-258">sr-latn cs</span><span class="sxs-lookup"><span data-stu-id="94040-258">sr-latn-cs</span></span>  <br/> |<span data-ttu-id="94040-259">2074</span><span class="sxs-lookup"><span data-stu-id="94040-259">2074</span></span>  <br/> |
|<span data-ttu-id="94040-260">sv-se</span><span class="sxs-lookup"><span data-stu-id="94040-260">sv-se</span></span>  <br/> |<span data-ttu-id="94040-261">1053</span><span class="sxs-lookup"><span data-stu-id="94040-261">1053</span></span>  <br/> |
|<span data-ttu-id="94040-262">th-th</span><span class="sxs-lookup"><span data-stu-id="94040-262">th-th</span></span>  <br/> |<span data-ttu-id="94040-263">1054</span><span class="sxs-lookup"><span data-stu-id="94040-263">1054</span></span>  <br/> |
|<span data-ttu-id="94040-264">tr-tr</span><span class="sxs-lookup"><span data-stu-id="94040-264">tr-tr</span></span>  <br/> |<span data-ttu-id="94040-265">1055</span><span class="sxs-lookup"><span data-stu-id="94040-265">1055</span></span>  <br/> |
|<span data-ttu-id="94040-266">uk-ua</span><span class="sxs-lookup"><span data-stu-id="94040-266">uk-ua</span></span>  <br/> |<span data-ttu-id="94040-267">1058</span><span class="sxs-lookup"><span data-stu-id="94040-267">1058</span></span>  <br/> |
|<span data-ttu-id="94040-268">zh-cn</span><span class="sxs-lookup"><span data-stu-id="94040-268">zh-cn</span></span>  <br/> |<span data-ttu-id="94040-269">2052</span><span class="sxs-lookup"><span data-stu-id="94040-269">2052</span></span>  <br/> |
|<span data-ttu-id="94040-270">zh-tw</span><span class="sxs-lookup"><span data-stu-id="94040-270">zh-tw</span></span>  <br/> |<span data-ttu-id="94040-271">1028</span><span class="sxs-lookup"><span data-stu-id="94040-271">1028</span></span>  <br/> |
   
<span data-ttu-id="94040-272">**表 2： 支持 OSC Glink 值**</span><span class="sxs-lookup"><span data-stu-id="94040-272">**Table 2: Supported Glink values for the OSC**</span></span>
  
|<span data-ttu-id="94040-273">**Glink 值**</span><span class="sxs-lookup"><span data-stu-id="94040-273">**Glink value**</span></span>|<span data-ttu-id="94040-274">**函数**</span><span class="sxs-lookup"><span data-stu-id="94040-274">**Function**</span></span>|
|:-----|:-----|
|<span data-ttu-id="94040-275">80</span><span class="sxs-lookup"><span data-stu-id="94040-275">80</span></span>  <br/> |<span data-ttu-id="94040-276">安装最新版本的 Outlook 2003 或 Outlook 2007 的 OSC。</span><span class="sxs-lookup"><span data-stu-id="94040-276">Installs the latest version of OSC for Outlook 2003 or Outlook 2007.</span></span>  <br/> |
|<span data-ttu-id="94040-277">82</span><span class="sxs-lookup"><span data-stu-id="94040-277">82</span></span>  <br/> |<span data-ttu-id="94040-278">安装 Outlook 2007、 Outlook 2010 或 Outlook Social Connector 2013 32 位 OSC 最新修补程序。</span><span class="sxs-lookup"><span data-stu-id="94040-278">Installs the latest patch of 32-bit OSC for Outlook 2007, Outlook 2010, or Outlook Social Connector 2013.</span></span>  <br/> |
|<span data-ttu-id="94040-279">83</span><span class="sxs-lookup"><span data-stu-id="94040-279">83</span></span>  <br/> |<span data-ttu-id="94040-280">安装最新的 Outlook 2010 或 Outlook Social Connector 2013 的 64 位 OSC 修补程序。</span><span class="sxs-lookup"><span data-stu-id="94040-280">Installs the latest patch of 64-bit OSC for Outlook 2010 or Outlook Social Connector 2013.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="94040-281">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94040-281">See also</span></span>

- [<span data-ttu-id="94040-282">注册提供程序</span><span class="sxs-lookup"><span data-stu-id="94040-282">Registering a Provider</span></span>](registering-a-provider.md) 
- [<span data-ttu-id="94040-283">快速学习开发提供程序的步骤</span><span class="sxs-lookup"><span data-stu-id="94040-283">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)
- [<span data-ttu-id="94040-284">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="94040-284">Deploying a Provider</span></span>](deploying-a-provider.md)

